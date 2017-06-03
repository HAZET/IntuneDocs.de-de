---
title: "Konfigurieren der Intune-Einstellungen für Bildungseinrichtungen für Windows 10"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune Einstellungen für Bildungseinrichtungen für Windows 10 auf Geräten konfigurieren, die Sie verwalten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3acb45ccc9e67fb410a9511f138d1558a49fadf9
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Konfigurieren von Einstellungen für Bildungseinrichtungen für Windows 10 in Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Mit Education-Profilen können Sie Details für die Konfiguration der Windows Take a Test-App einschließlich Kontodetails und die Test-URL angeben. Wenn Sie diese Konfiguration vornehmen, öffnet sich die Take a Test-App mit dem angegebenen Test, und auf dem Gerät können keine anderen Apps ausgeführt werden, bevor der Test abgeschlossen ist.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Geräteeinschränkungsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Erstellen eines Geräteprofils mit Education-Profileinstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 10 und höher** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Education-Profil** aus. 
7. Wählen Sie „Einstellungen“ > „Konfigurieren“ aus, und konfigurieren Sie auf dem Blatt **Prüfung** Folgendes:
    - **Kontobenutzername** – Geben Sie den Benutzernamen des Kontos ein, das mit Take a Test verwendet wird. Dies kann ein Domänenkonto, ein Azure Active Directory (AAD)-Konto oder ein lokales Computerkonto sein.
    - **Bewertungs-URL** – Geben Sie die URL des Tests an, den Benutzer ausführen sollen. Weitere Informationen finden Sie in der Take a Test-Dokumentation.
    - **Bildschirmaufnahme** – Geben Sie an, ob sie die Bildschirmaktivität aufnehmen möchten, während Benutzer einen Test ausführen.
    - **Textvorschlag** – Lassen Sie Textvorschläge zu oder blockieren sie diese, während Benutzer einen Test ausführen.
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.



