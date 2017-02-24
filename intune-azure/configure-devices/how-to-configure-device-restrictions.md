---
title: "Konfigurieren von Intune-Einstellungen für Geräteeinschränkungen | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune Einstellungen und Features auf Geräten, die Sie verwalten, konfigurieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 67e3481f9cf01bd1b298cfb26f25d1a3205e0f29
ms.openlocfilehash: 0c22d8a85d90139b3ac17c54668890d5b4c0afe6


---

# <a name="how-to-configure-device-restriction-settings-in-intune-azure-preview"></a>Konfigurieren von Einstellungen für Geräteeinschränkungen in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mit Geräteeinschränkungen können Sie eine Vielzahl von Einstellungen und Features für eine ganze Reihe von Kategorien steuern, einschließlich Sicherheit, Browser, Hardware und Einstellungen zur Datenfreigabe. Sie könnten beispielsweise ein Geräteeinschränkungsprofil erstellen, das verhindert, dass Benutzer von iOS-Geräten auf die Kamera des Geräts zugreifen.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Geräteeinschränkungsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Erstellen von Geräteprofilen mit Einstellungen für Geräteeinschränkungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie benutzerdefinierte Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die Einstellungen für Geräteeinschränkungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 und höher**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Geräteeinschränkungen** aus. Wenn Sie ein Geräteeinschränkungsprofil für Windows 10 Team-Geräte wie etwa ein Surface Hub erstellen möchten, wählen Sie **Geräteeinschränkungen (Windows 10 Team)** aus.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android](device-restrictions-for-android.md)
    - [Einstellungen für iOS](device-restrictions-for-ios.md)
    - [Einstellungen für macOS](device-restrictions-for-macos.md)
    - [Einstellungen für Windows Phone 8.1](device-restrictions-for-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-for-windows-8-1.md)
    - [Einstellungen für Windows 10](device-restrictions-for-windows-10.md)
    - [Einstellungen für Windows 10 Team](device-restrictions-for-windows-10-team.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.

## <a name="example-of-device-restriction-settings"></a>Beispiel für die Einstellungen für Geräteeinschränkungen

In diesem grundlegenden Beispiel erstellen Sie eine Richtlinie für Geräteeinschränkungen, die die Verwendung der integrierten Kamera-App auf Android-Geräten sperrt.

![Deaktivieren der Kamera auf Android-Geräten](./media/disable-android-camera.png)




<!--HONumber=Feb17_HO1-->

