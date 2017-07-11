---
title: Umgehung der iOS-Aktivierungssperre mit Intune
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie mithilfe von Intune die iOS-Aktivierungssperre umgehen, um auf gesperrte Geräte zuzugreifen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b92949efca2e4dac5836755e2f32b0527d4762d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2017
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Umgehen der Aktivierungssperre auf überwachten iOS-Geräten mit Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune kann Sie bei der Verwaltung der iOS-Aktivierungssperre unterstützen, einer Funktion der Mein iPhone suchen-App für Geräte mit iOS 8.0 und höher. Die Aktivierungssperre wird automatisch aktiviert, wenn ein Benutzer die App „Mein iPhone suchen“ auf einem Gerät öffnet. Nach der Aktivierung müssen die Apple-ID und das Kennwort des Benutzers eingegeben werden, bevor folgende Vorgänge möglich sind:

- Deaktivieren von „Mein iPhone suchen“
- Löschen des Geräts
- Reaktivieren des Geräts

## <a name="how-activation-lock-affects-you"></a>Auswirkungen der Aktivierungssperre

Obwohl die Aktivierungssperre zum Schutz von iOS-Geräten beiträgt und die Chancen einer Wiederherstellung bei Verlust oder Diebstahl des Geräts erhöht, kann diese Funktion Sie als IT-Administrator vor eine Reihe von Herausforderungen stellen. Beispiel:

- Ein Benutzer richtet die Aktivierungssperre auf einem Gerät ein. Anschließend verlässt der Benutzer das Unternehmen und gibt das Gerät zurück. Ohne die Apple-ID und das Kennwort des Benutzers gibt es keine Möglichkeit, das Gerät zu reaktivieren.
- Sie benötigen einen Bericht über alle Geräte, bei denen die Aktivierungssperre aktiviert ist.
- Während einer Geräteaktualisierung in Ihrem Unternehmen möchten Sie einige Geräte einer anderen Abteilung zuweisen. Es können nur Geräte neu zugewiesen werden, bei denen die Aktivierungssperre nicht aktiviert ist.

Apple hat zur Behebung dieser Probleme eine Umgehung der Aktivierungssperre in iOS 7.1 eingeführt. Auf diese Weise können Sie die Aktivierungssperre von überwachten Geräten ohne Apple-ID und Kennwort des Benutzers entfernen. Überwachte Geräte können einen gerätespezifischen Umgehungscode für die Aktivierungssperre generieren, der auf dem Aktivierungsserver von Apple gespeichert wird.

>[!TIP]
>Im überwachten Modus für iOS-Geräte können Sie mit dem Apple Configurator ein Gerät sperren, um die Funktionen auf bestimmte geschäftliche Zwecke zu beschränken. Der überwachte Modus ist in der Regel nur für firmeneigene Geräte vorgesehen.

Auf der [Website von Apple](https://support.apple.com/HT201365) erfahren Sie mehr über die Aktivierungssperre.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Unterstützung von Intune beim Verwalten der Aktivierungssperre
Intune kann den Status der Aktivierungssperre von überwachten Geräten anfordern, die iOS 8.0 und höher ausführen. Ausschließlich für überwachte Geräte kann Intune den Umgehungscode der Aktivierungssperre abrufen und ihn direkt auf das Gerät anwenden. Wenn das Gerät zurückgesetzt wurde, können Sie direkt auf das Gerät zugreifen, indem Sie einen leeren Benutzernamen und den Code als Kennwort verwenden.

**Folgende Geschäftsvorteile ergeben sich:**

- Der Benutzer erhält die Sicherheitsvorteile der App „Mein iPhone suchen“.
- Sie können es den Benutzern ermöglichen, ihre Arbeit zu erledigen, in dem Wissen, dass Sie das Gerät außer Kraft setzen oder entsperren können, wenn es einem neuen Zweck zugewiesen werden soll.

## <a name="before-you-start"></a>Vorbereitung
Bevor Sie die Aktivierungssperre auf Geräten umgehen können, müssen Sie sie zuerst aktivieren. Dazu gehen Sie folgendermaßen vor:

1. Konfigurieren Sie ein Intune-Profil für die Einschränkung von Geräten für iOS. Verwenden Sie dafür die Informationen unter [So konfigurieren Sie Einstellungen für Geräteeinschränkungen](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. Aktivieren Sie die **Kiosk**-Einstellung **Aktivierungssperre**.
3. Speichern Sie das Profil, und weisen Sie es den Geräten zu, auf denen Sie die Umgehung der Aktivierungssperre verwalten möchten.


## <a name="how-to-use-activation-lock-bypass"></a>Verwenden der Umgehung der Aktivierungssperre

>[!IMPORTANT]
>Nachdem die Aktivierungssperre auf einem Gerät umgangen wurde, wird automatisch eine neue Aktivierungssperre angewendet, wenn die App „Mein iPhone suchen“ geöffnet wird. Aus diesem Grund **muss das Gerät physisch verfügbar sein, bevor Sie dieses Verfahren ausführen**.

Die Intune-Remotegeräteaktion **Aktivierungssperre umgehen** entfernt die Aktivierungssperre auf einem iOS-Gerät, ohne dass die Apple-ID und das Kennwort des Benutzers angegeben werden muss. Nachdem Sie die Aktivierungssperre umgangen haben, aktiviert das Gerät die Aktivierungssperre erneut, wenn die App „Mein iPhone suchen“ gestartet wird. Umgehen Sie die Aktivierungssperre nur, wenn Sie physischen Zugriff auf das Gerät haben.

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein überwachtes iOS-Gerät aus, und wählen Sie dann die Remotegeräteaktion **Aktivierungssperre umgehen**.

Sie können den Status der Entsperranforderung in der Workload **Geräte verwalten** auf der Detailseite für das Gerät überprüfen.