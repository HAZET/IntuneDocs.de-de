---
title: "Abmelden eines Benutzers eines iOS-Geräts mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie den aktuellen Benutzer eines iOS-Geräts mit Intune abmelden."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e59eee3660f56fdd967237563e69324b8307e3a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Abmelden des aktuellen Benutzers eines mit Intune verwalteten iOS-Geräts


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Die Aktion **Aktiven Benutzer abmelden** meldet den aktuellen Benutzer auf einem freigegebenen iPad-Gerät ab, das für die Verwaltung der iOS Classroom-App mit einem [iOS-Bildungsprofil](education-settings-configure-ios.md) konfiguriert ist. 

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone – Nicht unterstützt
- iOS – Unterstützt auf iOS 9.3 und höher (nur freigegebene iPad-Geräte)
- macOS – Nicht unterstützt
- Android – Nicht unterstützt

## <a name="how-to-logout-the-current-user"></a>So melden Sie den aktuellen Benutzer ab

1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4.  Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5.  Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät und dann den Geräteremotevorgang **Aktiven Benutzer abmelden** aus.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
