---
title: "Konfigurieren von benutzerdefinierten Intune-Geräteeinstellungen | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune benutzerdefinierte Einstellungen auf Geräten, die Sie verwalten, konfigurieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: b404df57e94afe7b80dd39163ed72a24d8b05508


---

# <a name="how-to-configure-custom-device-settings"></a>Konfigurieren von benutzerdefinierten Geräteeinstellungen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Verwenden von benutzerdefinierten Einstellungen

Benutzerdefinierte Geräteeinstellungen können nützlich sein, wenn Intune nicht über die Einstellungen verfügt, die Sie konfigurieren möchten, diese aber für andere Geräteprofile verfügbar sind.
Benutzerdefinierte Einstellungen werden für jede Plattform anders konfiguriert. Bei Android- und Windows-Geräten können Sie beispielsweise OMA-URI-Werte (Open Mobile Alliance Uniform Resource Identifier) zum Steuern von Features auf Geräten angeben. Auf Apple-Geräten können Sie eine Datei importieren, die Sie mit [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) erstellt haben.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Profilen mit benutzerdefinierten Einstellungen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-custom-settings"></a>Erstellen eines Geräteprofils mit benutzerdefinierten Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das benutzerdefinierte Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie benutzerdefinierte Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die benutzerdefinierte Geräteeinstellungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android](custom-for-android.md)
    - [Einstellungen für iOS](custom-for-ios.md)
    - [Einstellungen für macOS](custom-for-macos.md)
    - [Einstellungen für Windows Phone 8.1](custom-for-windows-phone-8-1.md)
    - [Einstellungen für Windows 10](custom-for-windows-10.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.




<!--HONumber=Feb17_HO1-->

