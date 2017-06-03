---
title: "Überprüfen Ihrer App-Schutzrichtlinien"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): In diesen Themen wird beschrieben, wie Sie testen und überprüfen können, ob Ihre App-Schutzrichtlinie ordnungsgemäß eingerichtet wurde und wie erwartet funktioniert."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 26e191965eff482cf97b920e028cdf60d1881d32
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-validate-your-app-protection-policy-setup"></a>Überprüfen der Einrichtung von App-Schutzrichtlinien

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


Dieses Thema enthält Informationen zum Suchen nach Problemen nach der Einrichtung der App-Schutzrichtlinie. Diese Anleitung gilt für App-Schutzrichtlinien in der **Vorschau** des Azure-Portals.

### <a name="checking-for-symptoms"></a>Suchen nach Symptomen
Benutzer melden so gut wie keine Probleme, da der App-Schutz ein Tool zum Schutz von Daten ist. Liegt ein Problem mit der Konfiguration des App-Schutzes vor, erhält der Benutzer uneingeschränkten Zugriff, wie es auch ohne App-Schutz der Fall wäre, und er würde nicht bemerken, dass es ein Problem gibt. Aus diesem Grund wird empfohlen, dass Sie Ihre App-Schutzkonfiguration überprüfen, indem Sie Ihre App-Schutzrichtlinien mit einer kleinen Gruppe von Benutzern steuern, die bewusst die Einschränkungen des App-Schutzes testen können.


### <a name="what-to-check"></a>Was soll überprüft werden?

Wenn der Test zeigt, dass das Verhalten Ihrer App-Schutzrichtlinie nicht wie erwartet ist, empfiehlt es sich, folgende Punkte zu überprüfen:

- Sind die Benutzer für den App-Schutz lizenziert?
- Sind die Benutzer für Office 365 lizenziert?
- Welchen Status haben die App-Schutz-Apps der einzelnen Benutzers? Die möglichen Statuswerte für die apps sind **Eingecheckt** und **Nicht eingecheckt**.

#### <a name="user-app-protection-status"></a>Schutzstatus der Benutzer-App
1. Wählen Sie im Azure-Portal **Apps verwalten** > **Überwachen** >  **Benutzerstatus des App-Schutzes** > **Benutzer** aus.

2. Wählen Sie einen Benutzer aus der Liste aus, oder suchen Sie einen Benutzer und wählen Sie Ihn aus. Wählen Sie anschließend **Benutzer auswählen** aus. Am oberen Rand der Spalte **App-Berichterstellung** sehen Sie, ob der Benutzer für den App-Schutz lizenziert ist. Nachfolgend sehen Sie, ob der Benutzer für Office 365 und den App-Status aller Geräte des Benutzers lizenziert ist.



### <a name="what-to-do"></a>Aktion
Hier sind die Aktionen, die basierend auf den Benutzerstatus durchgeführt werden müssen:

- Wenn der Benutzer nicht für den App-Schutz lizenziert ist, weisen Sie dem Benutzer eine Intune-Lizenz zu.
- Wenn der Benutzer nicht für Office 365 lizenziert ist, rufen Sie eine Lizenz für den Benutzer ab.
- Wenn die App des Benutzer als **Nicht eingecheckt** aufgelistet ist, überprüfen Sie, ob Sie die App-Schutzrichtlinie für diese App ordnungsgemäß konfiguriert haben.
- Stellen Sie sicher, dass diese Bedingungen auf alle Benutzer angewendet werden, für die die App-Schutzrichtlinien gelten sollen.

### <a name="see-also"></a>Weitere Informationen:

[Was sind Intune-App-Schutzrichtlinien?](app-protection-policies.md)
