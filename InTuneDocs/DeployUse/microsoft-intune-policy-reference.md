---
# required metadata

title: Referenz zu Microsoft Intune-Richtlinien | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Referenz zu Microsoft Intune-Richtlinien

Anhand der Informationen in diesem Thema können Sie entscheiden, welche Microsoft Intune-Richtlinie Sie zum Verwalten Ihrer Geräte benötigen.

> [!TIP]
> Weitere Informationen zum Verwenden von Richtlinien finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..


## Android-Konfigurationsrichtlinien

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Benutzerdefinierte Konfiguration (Android 4 und höher, Samsung KNOX Standard 4.0 und höher)**|Bereitstellen von OMA-URI-Einstellungen, wie z. B. WLAN-Einstellungen, die zum Steuern von Gerätefunktionen dienen. Dies ist hilfreich, wenn die benötigte Einstellung nicht in einer Konfigurationsrichtlinie für mobile Geräte verfügbar ist.<br /><br />Weitere Informationen finden Sie unter [Android-Richtlinieneinstellungen in Microsoft Intune](android-policy-settings-in-microsoft-intune.md)..|
|**E-Mail-Profil (Samsung KNOX Standard 4.0 und höher)**|Erstellen, Bereitstellen und Überwachen von Exchange ActiveSync-E-Mail-Einstellungen auf verwalteten Geräten. Auf diese Weise erhalten Benutzer Zugriff auf Unternehmens-E-Mails auf ihren persönlichen Geräten, ohne dafür ein Setup vornehmen zu müssen.<br /><br />Weitere Informationen finden Sie unter [Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)..|
|**Allgemeine Konfiguration (Android 4 und höher, Samsung KNOX Standard 4.0 und höher)**|Konfigurieren der Sicherheits- und Funktionseinstellungen mobiler Geräte.<br />Angeben kompatibler und nicht kompatibler Apps und Melden ihrer Nutzung.<br />Konfigurieren des Kioskmodus, bei dem auf Geräten alle außer bestimmten Features gesperrten werden, sodass das Gerät z. B. nur eine App ausführen kann oder der Lautstärkeregler deaktiviert wird.<br /><br />Weitere Informationen finden Sie unter [Android-Richtlinieneinstellungen in Microsoft Intune](android-policy-settings-in-microsoft-intune.md)..|
|**PKCS #12-Zertifikatprofil (PFX) (Android 4 und höher)**|Verwenden Sie dieses Profil, um PFX-Einstellungen für Gerätezertifikatanforderungen bereitzustellen.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**SCEP-Zertifikatprofil (Android 4 und höher)**|Konfigurieren eines Simple Certificate Enrollment Protocol-Zertifikats, das mit einem Zertifikat eines vertrauenswürdigen mobilen Geräts zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**Vertrauenswürdiges Zertifikatprofil (Android 4 und höher)**|Konfigurieren eines Zertifikats für ein vertrauenswürdiges mobiles Gerät, das zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**VPN-Profil (Android 4 und höher)**|Konfigurieren und Bereitstellen von Einstellungen, mit denen Benutzer sicheren Zugriff auf ihr Unternehmensnetzwerk von ihrem mobilen Gerät aus erhalten. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer, sich mit der Arbeit zu verbinden.<br /><br />Weitere Informationen finden Sie unter [VPN-Verbindungen in Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**WLAN-Profil (Android 4 und höher)**|Konfigurieren und Bereitstellen von Einstellungen für drahtlose Netzwerke für Benutzer in Ihrer Organisation. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Herstellen einer Verbindung mit dem drahtlosen Netzwerk.<br /><br />Weitere Informationen finden Sie unter [WLAN-Verbindungen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## iOS-Konfigurationsrichtlinien

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Benutzerdefinierte Konfiguration (iOS 7.1 und höher)**|Bereitstellen von Konfigurationsprofilen für iOS-Geräte, die Sie mit dem Apple-Konfigurator-Tool erstellt haben, Dies ist hilfreich, wenn die benötigte Einstellung nicht in einer Konfigurationsrichtlinie für mobile Geräte verfügbar ist.<br /><br />Weitere Informationen finden Sie unter [iOS-Richtlinieneinstellungen in Microsoft Intune](ios-policy-settings-in-microsoft-intune.md)..|
|**E-Mail-Profil (iOS 7.1 und höher)**|Erstellen, Bereitstellen und Überwachen von Exchange ActiveSync-E-Mail-Einstellungen auf verwalteten Geräten. Auf diese Weise erhalten Benutzer Zugriff auf Unternehmens-E-Mails auf ihren persönlichen Geräten, ohne dafür ein Setup vornehmen zu müssen.<br /><br />Weitere Informationen finden Sie unter [Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)..|
|**Allgemeine Konfiguration (iOS 7.1 und höher)**|Konfigurieren der Sicherheits- und Funktionseinstellungen mobiler Geräte.<br />– Angeben kompatibler und nicht kompatibler Apps und Melden ihrer Nutzung.<br />Konfigurieren des Kioskmodus, bei dem auf Geräten alle außer bestimmten Features gesperrten werden, sodass das Gerät z. B. nur eine App ausführen kann oder der Lautstärkeregler deaktiviert wird.<br /><br />Weitere Informationen finden Sie unter [iOS-Richtlinieneinstellungen in Microsoft Intune](ios-policy-settings-in-microsoft-intune.md)..|
|**SCEP-Zertifikatprofil (iOS 7.1 und höher)**|Konfigurieren eines Simple Certificate Enrollment Protocol-Zertifikats, das mit einem Zertifikat eines vertrauenswürdigen mobilen Geräts zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**Vertrauenswürdiges Zertifikatprofil (iOS 7.1 und höher)**|Konfigurieren eines Zertifikats für ein vertrauenswürdiges mobiles Gerät, das zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**VPN-Profil (iOS 7.1 und höher)**|Konfigurieren und Bereitstellen von Einstellungen, mit denen Benutzer sicheren Zugriff auf ihr Unternehmensnetzwerk von ihrem mobilen Gerät aus erhalten. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer, sich mit der Arbeit zu verbinden.<br /><br />Weitere Informationen finden Sie unter [VPN-Verbindungen in Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**WLAN-Profil (iOS 7.1 und höher)**|Konfigurieren und Bereitstellen von Einstellungen für drahtlose Netzwerke für Benutzer in Ihrer Organisation. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Herstellen einer Verbindung mit dem drahtlosen Netzwerk.<br /><br />Weitere Informationen finden Sie unter [WLAN-Verbindungen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|
|**Konfigurationsrichtlinie für mobile Apps (iOS 7.1 und höher)**|Verwenden Sie Konfigurationsrichtlinien für mobile Apps, um automatisch Einstellungen bereitzustellen, die beim Ausführen einer iOS-App durch den Benutzer erforderlich sind.<br /><br />Weitere Informationen finden Sie unter [Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)..|

## Mac OS X-Konfigurationsrichtlinien

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Benutzerdefinierte Konfiguration (Mac OS X 10.9 und höher)**|Bereitstellen von Konfigurationsprofilen für Mac-Computer, die Sie mit dem Apple Configurator-Tool erstellt haben. Dies ist hilfreich, wenn die benötigte Einstellung nicht in einer Konfigurationsrichtlinie für mobile Geräte verfügbar ist.<br /><br />Weitere Informationen finden Sie unter [Mac OS X-Richtlinieneinstellungen in Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md)..|
|**Allgemeine Konfiguration (Mac OS X 10.9 und höher)**|Konfigurieren der Sicherheits- und Funktionseinstellungen mobiler Geräte.<br />Angeben kompatibler und nicht kompatibler Apps und Melden ihrer Nutzung.<br /><br />Weitere Informationen finden Sie unter [Mac OS X-Richtlinieneinstellungen in Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md)..|
|**SCEP-Zertifikatprofil (Mac OS X 10.9 und höher)**|Konfigurieren eines Simple Certificate Enrollment Protocol-Zertifikats, das mit einem Zertifikat eines vertrauenswürdigen mobilen Geräts zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**Vertrauenswürdiges Zertifikatprofil (Mac OS X 10.9 und höher)**|Konfigurieren eines Zertifikats für ein vertrauenswürdiges mobiles Gerät, das zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**VPN-Profil (Mac OS X 10.9 und höher)**|Konfigurieren und Bereitstellen von Einstellungen, mit denen Benutzer sicheren Zugriff auf ihr Unternehmensnetzwerk von ihrem mobilen Gerät aus erhalten. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer, sich mit der Arbeit zu verbinden.<br /><br />Weitere Informationen finden Sie unter [VPN-Verbindungen in Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**WLAN-Profil (Mac OS X 10.9 und höher)**|Konfigurieren und Bereitstellen von Einstellungen für drahtlose Netzwerke für Benutzer in Ihrer Organisation. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Herstellen einer Verbindung mit dem drahtlosen Netzwerk.<br /><br />Weitere Informationen finden Sie unter [WLAN-Verbindungen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Windows-Konfigurationsrichtlinien
Gilt nur für Windows Phone und registrierte Windows-Geräte.

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Benutzerdefinierte Konfiguration (Windows 10 Desktop und Mobile und höher)**|Bereitstellen von OMA-URI-Einstellungen, die zum Steuern von Gerätefunktionen verwendet werden können. Dies ist hilfreich, wenn die benötigte Einstellung nicht in einer Konfigurationsrichtlinie für mobile Geräte verfügbar ist.<br />    Weitere Informationen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md)..|
|**Benutzerdefinierte Konfiguration (Windows Phone 8.1 und höher)**|Bereitstellen von OMA-URI-Einstellungen, die zum Steuern von Gerätefunktionen verwendet werden können. Dies ist hilfreich, wenn die benötigte Einstellung nicht in einer Konfigurationsrichtlinie für mobile Geräte verfügbar ist.<br /><br />Weitere Informationen finden Sie unter [Windows Phone 8.1-Richtlinieneinstellungen in Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md)..|
|**Upgraderichtlinie für die Edition (Windows 10 Desktop und höher)**<br><br>**Upgraderichtlinie für die Edition (Windows 10 Holographic und höher)**|Konfigurieren und Bereitstellen von Richtlinien mit Lizenz- oder Product Key-Informationen zum Aktualisieren von Windows 10-Geräten auf eine neuere Version.<br><br>Weitere Informationen finden Sie unter [Einstellungen für Editionupgraderichtlinien in Microsoft Intune](edition-upgrade-policy-settings-in-microsoft-intune.md)..|  
|**E-Mail-Profil (Windows Phone 8 und höher)**<br /><br />**E-Mail-Profil (Windows 10 Desktop und Windows 10 Mobile oder höher)**|Erstellen, Bereitstellen und Überwachen von Exchange ActiveSync-E-Mail-Einstellungen auf verwalteten Geräten. Auf diese Weise erhalten Benutzer Zugriff auf Unternehmens-E-Mails auf ihren persönlichen Geräten, ohne dafür ein Setup vornehmen zu müssen.<br /><br />Weitere Informationen finden Sie unter [Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)..|
|**Allgemeine Konfiguration (Windows 10 Desktop und Mobile und höher)**|Konfigurieren der Sicherheits- und Funktionseinstellungen für registrierte mobile Geräte unter Windows 10 Desktop und Mobile.<br /><br />Weitere Informationen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md)..|
|**Allgemeine Konfiguration (Windows 10 Team und höher)**|Konfigurieren Sie die Gerätesicherheit und die Funktionseinstellungen für registrierte Windows 10 Team-Geräte (z. B. ein Surface Hub-Gerät).<br /><br />Weitere Informationen finden Sie unter [Einstellungen für Windows Team-Konfigurationsrichtlinien in Microsoft Intune](windows-team-configuration-policy-settings-in-microsoft-intune.md)..|
|**Allgemeine Konfiguration (Windows 8.1 und höher)**|Konfigurieren der Sicherheit- und Funktionseinstellungen mobiler Geräte für registrierte Windows-Geräte.<br /><br />Weitere Informationen finden Sie unter [Windows-Richtlinieneinstellungen in Microsoft Intune](windows-configuration-policy-settings-in-microsoft-intune.md)..|
|**Allgemeine Konfiguration (Windows Phone 8.1 und höher)**|Konfigurieren der Sicherheits- und Funktionseinstellungen mobiler Geräte.<br />Angeben von Apps, die Benutzer verwenden bzw. nicht verwenden können, um zu verhindern, dass nicht kompatible Apps installiert oder verwendet werden.<br /><br />Weitere Informationen finden Sie unter [Windows Phone 8.1-Richtlinieneinstellungen in Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md)..|
|**PKCS #12-Zertifikatprofil (PFX) (Windows 10 Desktop und Mobile und höher)**|Verwenden Sie dieses Profil, um PFX-Einstellungen für Gerätezertifikatanforderungen bereitzustellen.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**SCEP-Zertifikatprofil (Windows 8.1 und höher)**<br /><br />**SCEP-Zertifikatprofil (Windows Phone 8.1 und höher)**|Konfigurieren eines Simple Certificate Enrollment Protocol-Zertifikats, das mit einem Zertifikat eines vertrauenswürdigen mobilen Geräts zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md)..|
|**Vertrauenswürdiges Zertifikatprofil (Windows 8.1 und höher)**<br /><br />**Vertrauenswürdiges Zertifikatprofil (Windows Phone 8.1 und höher)**|Konfigurieren eines Zertifikats für ein vertrauenswürdiges mobiles Gerät, das zum Authentifizieren von mobilen Geräten verwendet werden kann, damit diese Zugriff auf Netzwerkressourcen wie z. B. die von WLAN- und VPN-Profilen konfigurierten erhalten.<br /><br />Weitere Informationen finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md).).|
|**VPN-Profil (Windows 10 Desktop und Mobile und höher)**<br /><br />**VPN-Profil (Windows 8.1 und höher)**<br /><br />**VPN-Profil (Windows Phone 8.1 und höher)**|Konfigurieren und Bereitstellen von Einstellungen, mit denen Benutzer sicheren Zugriff auf ihr Unternehmensnetzwerk von ihrem mobilen Gerät aus erhalten. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer, sich mit der Arbeit zu verbinden.<br /><br />Weitere Informationen finden Sie unter [VPN-Verbindungen in Microsoft Intune.md](vpn-connections-in-microsoft-intune.md).|
|**Importieren von WLAN-Konfigurationen**|Importieren und Bereitstellen von Windows Wi-Fi-Konfigurationen, die Sie zuvor in eine Datei exportiert haben.<br /><br />Weitere Informationen finden Sie unter [WLAN-Verbindungen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Softwarerichtlinien

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Richtlinie für Managed Browser (Android 4 und höher)**<br /><br />**Richtlinie für Managed Browser (iOS 7.1 und höher)**|Angeben der Websites, auf die Benutzer zugreifen bzw. nicht zugreifen können, wenn sie die Managed Browser-App verwenden.<br /><br />Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels für Managed Browser-Richtlinien mit Microsoft Intune](manage-internet-access-using-managed-browser-policies.md)..|
|**Richtlinie zur mobilen Anwendungsverwaltung (Android 4 und höher)**<br /><br />**Richtlinie zur Verwaltung von mobilen Anwendungen (iOS 7.1 und höher)**|Ändern der Funktionalität von bereitgestellten Apps, um sie an die Konformitäts- und Sicherheitsrichtlinien Ihres Unternehmens anzupassen. Sie können z. B. Ausschneide-, Kopier- und Einfügevorgänge innerhalb einer eingeschränkten App einschränken oder eine App so konfigurieren, dass alle Weblinks innerhalb des Managed Browser geöffnet werden.<br /><br />Weitere Informationen finden Sie unter [Konfigurieren und Bereitstellen von Verwaltungsrichtlinien für mobile Anwendungen in der Microsoft Intune-Konsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).|

## Allgemeine Einstellungen für mobile Geräte

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Exchange ActiveSync-Richtlinie**|Konfigurieren von Sicherheits- und Funktionseinstellungen mobiler Geräte für Geräte, die von Exchange ActiveSync verwaltet werden.<br /><br />Weitere Informationen finden Sie unter [Einstellungen für Exchange ActiveSync-Richtlinien in Microsoft Intune](exchange-activesync-policy-settings-in-microsoft-intune.md)..|
|**Sicherheitsrichtlinie für mobiles Gerät**|<ul><li>Konfiguriert die Einstellungen für mobile Geräte (alle Plattformen), einschließlich:<br /><br /><ul><li>Sicherheit</li><li>Verschlüsselung</li><li>System</li><li>E-Mail</li><li>Anwendungen</li></ul></li></ul> **Wichtig:** Microsoft Intune bietet jetzt getrennte **Konfigurationsrichtlinien** für jede Geräteplattform, wobei diese Richtlinien die neuesten Einstellungen berücksichtigen, die Sie verwenden können. Sie können die Sicherheitsrichtlinie für mobile Geräte weiter nutzen, wobei alle vorhandenen Bereitstellungen weiterhin funktionieren. Sie sollten allerdings die Migration zu den neuen Konfigurationsrichtlinien so bald wie möglich planen.<br />Weitere Informationen finden Sie unter [Sicherheitsrichtlinieneinstellungen für mobile Geräte in Microsoft Intune](mobile-device-security-policy-settings-in-microsoft-intune.md)..|

## Bedingter Zugriff und Kompatibilitätsrichtlinien

### Bedingter Zugriff

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Exchange Online-Richtlinie**<br /><br />**Lokale Exchange-Richtlinie**|Verwalten des Zugriffs auf Microsoft Exchange-E-Mail auf Geräten, die nicht von Intune verwaltet werden oder nicht mit einer von Ihnen erstellten Richtlinie kompatibel sind.<br /><br />Weitere Informationen finden Sie unter [Beschränken des E-Mail-Zugriffs auf Exchange Online und neue Exchange Online Dedicated-Umgebungen mit Intune](restrict-access-to-exchange-online-with-microsoft-intune.md)..|
|**SharePoint Online-Richtlinie**|Verwalten des Zugriffs auf SharePoint Online auf Geräten, die nicht von Intune verwaltet werden oder nicht mit einer von Ihnen erstellten Richtlinie kompatibel sind.<br /><br />Weitere Informationen finden Sie unter [Beschränken des Zugriffs auf SharePoint Online mit Microsoft Intune](restrict-access-to-sharepoint-online-with-microsoft-intune.md)..|
|**Skype for Business**|Verwalten des Zugriffs auf Skype for Business auf Geräten, die nicht von Intune verwaltet werden oder nicht mit einer von Ihnen erstellten Richtlinie kompatibel sind.<br /><br />Weitere Informationen finden Sie unter [Beschränken des Zugriffs auf Skype for Business mit Microsoft Intune](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)..|
> [!NOTE]
> Sie stellen Benutzern und Geräten keine bedingten Zugriffsrichtlinien bereit. Stattdessen konfigurieren Sie die benötigte Richtlinie, und wenden Sie sie auf alle Gruppen an, für die die Richtlinie gelten soll.

### Kompatibilitätsrichtlinien

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Kompatibilitätsrichtlinien**|Definieren des Grads der Kompatibilität für Geräte und Melden nicht kompatibler Geräte. Diese Richtlinien werden mit bedingtem Zugriff verwendet, um Geräte einfacher zu bestimmen, die für Dienste gesperrt werden sollen.<br /><br />Weitere Informationen finden Sie unter [Gerätekompatibilitätsrichtlinien in Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)..|

## Windows-PC-Verwaltung

|Name der Richtlinie|Zweck|
|---------------|------------------------|
|**Microsoft Intune-Agent-Einstellungen**|Konfigurieren des Intune-PC-Clients auf Computern samt Einstellungen für u. a.:<br /><br />– Endpoint Protection<br />– Softwareupdates<br />– Zeitplan für die Richtlinienprüfung<br /><br />Dieser Richtlinientyp kann nur für Gruppen von Geräten bereitgestellt werden.<br /><br />Neue und aktualisierte Richtlinien werden von Intune-Clients entsprechend der Einstellung **Häufigkeit der Suche nach Updates und Anwendungen** heruntergeladen, die standardmäßig einen Wert von 8 Stunden hat. Allerdings können Sie jederzeit eine Aktualisierung der Richtlinie auf Computern erzwingen.<br /><br />Weitere Informationen finden Sie unter [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)..|
|**Microsoft Intune Center-Einstellungen**|Konfigurieren von Details im Microsoft Intune Center auf verwalteten Computern.<br /><br />Dieser Richtlinientyp kann nur für Gruppen von Geräten bereitgestellt werden.<br /><br />Weitere Informationen finden Sie unter [Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)..|
|**Einstellungen der Windows Firewall**|Hiermit werden die Windows-Firewall-Einstellungen und Ausnahmen für die allgemeine Netzwerkkommunikation auf Computern einschließlich der folgenden Elemente konfiguriert:<br /><br />– BranchCache<br />– Remoteunterstützung<br />– Gemeinsame Nutzung von Medien<br /><br />Dieser Richtlinientyp kann nur für Gruppen von Geräten bereitgestellt werden.<br /><br />Weitere Informationen finden Sie unter [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)..|

### Weitere Informationen

[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->

