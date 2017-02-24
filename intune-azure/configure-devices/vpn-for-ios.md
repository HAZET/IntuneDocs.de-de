---
title: "Intune-VPN-Einstellungen für iOS-Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf iOS-Geräten verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: 23322313bfedb089f2665f53795996a26efe40e0


---

# <a name="vpn-settings-for-ios-devices-in-intune-azure-preview"></a>VPN-Einstellungen für iOS-Geräte in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.

## <a name="base-vpn-settings"></a>Grundlegende VPN-Einstellungen


**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein. Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.
- **IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen. Beispiele: **192.168.1.1**, **vpn.contoso.com**.
- **Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:
    - **Zertifikate:** Wählen Sie unter **Authentifizierungszertifikat** ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus. Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](how-to-configure-certificates.md).
    - **Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.
- **Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPsec)**
    - **Citrix**
    - **Benutzerdefiniertes VPN**
- **Tunneling teilen** - **Aktivieren** oder **deaktivieren** Sie diese Option, mit der Geräte anhand des Datenverkehrs selbst entscheiden können, welche Verbindung verwendet werden soll. Beispiel: Ein Benutzer in einem Hotel verwendet die VPN-Verbindung zum Zugreifen auf Arbeitsdateien, jedoch das Standardnetzwerk des Hotels für normales Webbrowsen.


## <a name="custom-vpn-settings"></a>Benutzerdefinierte VPN-Einstellungen

Wenn Sie **Benutzerdefiniertes VPN** als Verbindungstyp ausgewählt haben, konfigurieren Sie diese weiteren Einstellungen:

- **VPN-Bezeichner:** Dies ist ein Bezeichner für die verwendete VPN-App und wird von Ihrem VPN-Anbieter bereitgestellt.
- **Geben Sie Schlüssel-Wert-Paare für die benutzerdefinierten VPN-Attribute ein:** Fügen Sie **Schlüssel** und **Werte** zum Anpassen der VPN-Verbindung hinzu, oder importieren Sie sie. Auch diese Werte werden in der Regel von Ihrem VPN-Anbieter bereitgestellt.

## <a name="apps-per-app-vpn-settings"></a>App-Einstellungen (VPN für App)

- **VPN für App:** Aktivieren Sie diese Option, wenn Sie über URLs verfügen möchten, über die im Safari-Browser die VPN-Verbindung aktiviert werden kann. Für diese Konfiguration müssen Sie in den grundlegenden VPN-Einstellungen **Zertifikate** als Authentifizierungsmethode ausgewählt haben.
- **Hiermit geben Sie URLs zum Aktivieren der VPN-Verbindung bei Verwendung des Safari-Browsers an:** Klicken Sie hierauf, um Website-URLs hinzuzufügen. Wenn diese URLs aufgerufen werden, wird die VPN-Verbindung aktiviert.

- **Bedarfsgesteuerte Regeln:** Hier können Sie bedingte Regeln konfigurieren, die steuern, wann die VPN-Verbindung initiiert wird. Beispielsweise können Sie eine Bedingung erstellen, in der die VPN-Verbindung nur verwendet wird, wenn ein Gerät nicht mit einem Ihrer Unternehmens-WLAN-Netzwerke verbunden ist. Alternativ können Sie eine Bedingung erstellen, in der die VPN-Verbindung nicht initiiert wird, wenn ein Gerät nicht auf eine angegebene DNS-Suchdomäne zugreifen kann.

    - **SSIDs oder DNS-Suchdomänen:** Wählen Sie aus, ob diese Bedingung **SSIDs** des Drahtlosnetzwerks oder **DNS-Suchdomänen** verwenden soll. Wählen Sie „Hinzufügen“ aus, um SSIDs oder Suchdomänen zu konfigurieren.
    - **URL-Zeichenfolgentest:** Geben Sie optional eine URL an, die von der Regel als Test verwendet wird. Wenn das Gerät, auf dem dieses Profil installiert wird, auf diese URL ohne Umleitung zugreifen kann, wird die VPN-Verbindung initiiert, und das Gerät stellt eine Verbindung mit der Ziel-URL her. Der URL-Zeichenfolgentest-Standort wird dem Benutzer nicht angezeigt. Ein Beispiel für einen URL-Zeichenfolgentest ist die Adresse eines Überwachungswebservers, der die Gerätekompatibilität prüft, bevor die VPN-Verbindung hergestellt wird. Eine andere Möglichkeit besteht darin, mit der URL zu testen, ob das VPN eine Verbindung mit einem Standort herstellen kann, bevor das Gerät über das VPN mit der Ziel-URL verbunden wird.
    - **Domänenaktion:** Wählen Sie eine der folgenden Optionen aus:
        - Bei Bedarf verbinden 
        - Nie verbinden 
    - **Aktion:** Wählen Sie eine der folgenden Optionen aus:
        - Verbinden 
        - Verbindung auswerten 
        - Ignorieren 
        - Trennen 


## <a name="proxy-settings"></a>Proxyeinstellungen

- **Automatisches Konfigurationsskript:** Verwenden Sie eine Datei zum Konfigurieren des Proxyservers. Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.
- **Adresse:** Geben Sie die Adresse des Proxyservers (als IP-Adresse) ein.
- **Portnummer:** Geben Sie die Portnummer ein, die dem Proxyserver zugeordnet ist.



<!--HONumber=Feb17_HO2-->

