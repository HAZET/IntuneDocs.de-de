---
title: "Verwalten von Apps aus dem Windows Store für Unternehmen | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Apps aus dem Windows Store für Unternehmen in Intune synchronisieren und dann zuweisen und nachverfolgen können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a57ac0e6cb29dbfc87bb09c04bb372228a1d72be
ms.openlocfilehash: 2acb58a8fc71ae7f2e0bce127e709a678faa27cb

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business"></a>Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Im [Windows Store für Unternehmen](https://www.microsoft.com/business-store) können Sie Apps für Ihre Organisation suchen und einzeln oder im Rahmen eines Volumenprogramms erwerben. Indem Sie den Store mit Microsoft Intune verbinden, können Sie im Rahmen von Volumenprogrammen erworbene Apps über das Intune-Portal verwalten. Beispiel:
* Sie können die Liste der Apps, die Sie im Speicher erworben haben, mit Intune synchronisieren.
* Synchronisierte Apps werden in der Intune-Verwaltungskonsole angezeigt und können wie alle anderen Apps zugewiesen werden.
* Sie können in der Intune-Verwaltungskonsole die Anzahl der verfügbaren und der verwendeten Lizenzen nachverfolgen.
* Intune blockiert die Bereitstellung und Installation von Apps, wenn nicht genügend Lizenzen vorhanden sind.

## <a name="before-you-start"></a>Vorbereitung
Überprüfen Sie die folgenden Informationen, bevor Sie beginnen, Apps aus dem Windows Store für Unternehmen zu synchronisieren und bereitzustellen:
* Sie müssen Intune als Autorität zur Verwaltung mobiler Geräte für Ihre Organisation konfigurieren.
* Sie müssen im Windows Store für Unternehmen über ein registriertes Konto verfügen.
* Sobald ein Konto für den Windows Store für Unternehmen Intune zugeordnet wurde, können Sie dieses zugeordnete Konto nicht mehr ändern.
* Apps, die im Store erworben wurden, können Intune nicht manuell hinzugefügt oder daraus gelöscht werden. Sie können nur mit dem Windows Store für Unternehmen synchronisiert werden.
* Intune synchronisiert nur online lizenzierte Apps, die Sie aus dem Windows Store für Unternehmen erworben haben.
* Geräte müssen mit Active Directory Domain Services oder einem Arbeitsbereich verknüpft sein, damit diese Funktion verwendet werden kann.
* Registrierte Geräte müssen die Version 1511 oder höher von Windows 10 verwenden.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Verknüpfen Ihres Kontos für den Windows Store für Unternehmen mit Intune
Bevor Sie die Synchronisierung in der Intune-Konsole aktivieren, müssen Sie Ihr Konto für den Windows Store für Unternehmen so konfigurieren, dass Intune als Verwaltungstool verwendet wird:
1. Stellen Sie sicher, dass Sie sich beim Windows Store für Unternehmen und bei Intune mit demselben Mandantenkonto anmelden.
2. Wählen Sie im Windows Store für Unternehmen **Einstellungen** > **Verwaltungstools** aus.
3. Wählen Sie auf der Seite „Verwaltungstools“ die Option **Verwaltungstool hinzufügen** und dann **Microsoft Intune** aus.

> [!NOTE]
> Wenn Sie mehr als ein Verwaltungstool zum Bereitstellen von Windows Store für Unternehmen-Apps verwenden, konnten Sie vorher nur eine App dem Windows Store für Unternehmen zuordnen. Nun können Sie mehrere Verwaltungstools dem Store zuordnen, z.B. Intune und Configuration Manager.

Sie können nun fortfahren und die Synchronisierung in der Intune-Konsole einrichten.

## <a name="configure-synchronization"></a>Konfigurieren der Synchronisierung

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
1. Wählen Sie auf dem Blatt **Mobile Apps** die Option **Setup** > **Windows Store für Unternehmen** aus.
2. Klicken Sie auf **Aktivieren**.
3. Klicken Sie auf den Link zur Registrierung für den Windows Store für Unternehmen, falls Sie dies noch nicht getan haben, und weisen Sie Ihr Konto wie oben beschrieben zu.
5. Wählen Sie in der Dropdownliste **Sprache** die Sprache aus, in der Apps aus dem Windows Store für Unternehmen im Intune-Portal angezeigt werden. Die Installation der Apps erfolgt unabhängig von der Anzeigesprache in der Sprache des Endbenutzers, sofern verfügbar.
6. Klicken Sie auf **Synchronisieren**, um die im Windows Store erworbenen Apps in Intune abzurufen.

## <a name="synchronize-apps"></a>Synchronisieren von Apps

1. Wählen Sie in der Workload **Apps verwalten** die Option **Setup** > **Windows Store für Unternehmen** aus.
2. Klicken Sie auf **Synchronisieren**, um die im Windows Store erworbenen Apps in Intune abzurufen.

## <a name="assign-apps"></a>Zuweisen von Apps

Sie weisen Apps aus dem Store auf die gleiche Weise wie andere Intune-Apps zu. Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](deploy-apps.md). Anstelle der Zuweisung von Apps auf der Seite **Alle Apps** weisen Sie diese über die Seite **Lizenzierte Apps** zu.

Wenn Sie eine App aus dem Windows Store für Unternehmen zuweisen, wird von jedem Benutzer, der die App installiert, eine Lizenz verwendet. Wenn alle verfügbaren Lizenzen für eine bereitgestellte App verwendet werden, können keine weiteren Kopien bereitgestellt werden. Sie müssen eine der folgenden Aktionen ausführen:
* Deinstallieren Sie die App auf einigen Geräten.
* Beschränken Sie die aktuelle Bereitstellung auf die Anzahl von Benutzern, für die Sie über Lizenzen verfügen.
* Erwerben Sie zusätzliche Kopien der App im Windows Store für Unternehmen.

> [!Important]
> Bereitgestellte Apps sind nur für den Benutzer verfügbar, der das Gerät ursprünglich registriert hat. Andere Benutzer können nicht auf die App zugreifen.



<!--HONumber=Feb17_HO1-->

