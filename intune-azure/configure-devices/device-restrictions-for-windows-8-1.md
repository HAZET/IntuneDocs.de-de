---
title: "Intune-Einstellungen für Geräteeinschränkungen für Windows 8.1 | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Windows 8.1-Geräten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 0b8700d32e4a9a94dc68edeba34609a76d0e3887


---

# <a name="windows-81-and-later-device-restriction-settings-in-intune-azure-preview"></a>Einstellungen für Geräteeinschränkungen für Windows 8.1 und höher in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Allgemein
-   **Alle Konfigurationen auf Windows 10 anwenden:** Aktiviert Einstellungen in dieser Richtlinie, die zusätzlich zu Windows 8.1-Geräten auf Windows 10-Geräte angewendet werden.
-   **Übermittlung von Diagnosedaten:** Ermöglicht dem Gerät die Übermittlung von Diagnoseinformationen an Microsoft.
-   **Firewall:** Erfordert, dass die Windows-Firewall aktiviert sein muss.
-   **Benutzerkontensteuerung:** Erfordert, dass die Benutzerkontensteuerung (User Account Control, UAC) auf Geräten verwendet werden muss.
## <a name="password"></a>Kennwort
-   **Erforderlicher Kennworttyp:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.
-   **Minimale Kennwortlänge:** Konfiguriert die erforderliche Mindestlänge (in Zeichen) für das Kennwort.
-   **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird:** Setzt das Gerät zurück, wenn diese Anzahl von Anmeldefehlern erreicht ist.
-   **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt die Anzahl von Minuten der Inaktivität an, bevor ein Kennwort zum Entsperren des Geräts erforderlich ist.
-   **Kennwortablauf (Tage):** Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.
-   **Wiederverwendung vorheriger Kennwörter verhindern:** Gibt an, ob der Benutzer zuvor verwendete Kennwörter konfigurieren kann.
-   **Bildcode und PIN:** Aktiviert die Verwendung eines Bildcodes und einer PIN. Mit einem Bildkennwort kann sich der Benutzer mit Gesten auf einem Bild anmelden. Mit einer PIN kann sich der Benutzer mit einem vierstelligen Code schnell anmelden.
-   **Verschlüsselung:** Schreibt vor, dass die Dateien auf den Geräten verschlüsselt werden müssen.<br>Um die Verschlüsselung auf Geräten zu erzwingen, die Windows 8.1 ausführen, installieren Sie das [MDM-Clientupdate für Windows von Dezember 2014](https://support.microsoft.com/en-us/kb/3013816) auf jedem Gerät.
Wenn Sie diese Einstellung für Windows 8.1-Geräte aktivieren, müssen alle Benutzer des Geräts ein Microsoft-Konto haben.
Damit die Verschlüsselung funktioniert, muss das Gerät die Hardwarezertifizierungsanforderungen für [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) erfüllen.
Wenn Sie die Verschlüsselung auf einem Gerät erzwingen, ist der Wiederherstellungsschlüssel nur über das Microsoft-Konto des Benutzers zugänglich, auf das dieser über sein eigenes OneDrive-Konto zugreift. Sie können diesen Schlüssel nicht im Auftrag eines Benutzers wiederherstellen.     



## <a name="browser"></a>Browser
-   **AutoAusfüllen:** Erlaubt Benutzern, die Einstellungen für AutoAusfüllen im Browser zu ändern.
-   **Betrugswarnungen:** Aktiviert oder deaktiviert Warnungen zu potenziell betrügerischen Websites.
-   **SmartScreen:** Aktiviert oder deaktiviert Warnungen zu potenziell betrügerischen Websites.
-   **Javascript:** Erlaubt dem Browser, Skripts auszuführen, z.B. Java-Skripts.
-   **Popups:** Aktiviert oder deaktiviert den Popupblocker des Browsers.
-   **DNT-Kopfzeilen senden:** Sendet einen DNT-Header (Do Not Track, nicht nachverfolgen) an besuchte Websites in Internet Explorer.
-   **Plug-Ins** Erlaubt Benutzern, Internet Explorer Plug-Ins hinzuzufügen.
-   **Eingabe eines einzelnen Worts auf Intranetsite zulassen:** Erlaubt die Verwendung eines einzelnen Worts, um Internet Explorer auf eine Website wie Bing weiterzuleiten.
-   **Automatische Erkennung von Intranetsite:** Hilft bei der Konfiguration der Sicherheit für Intranetsites in Internet Explorer.
-   **Internetsicherheitsebene:** Legt die Internet Explorer-Sicherheitsstufe für Websites im Internet fest.
-   **Intranetsicherheitsebene:** Legt die Internet Explorer-Sicherheitsstufe für Websites im Intranet fest.
-   **Sicherheitsstufe für vertrauenswürdige Sites:** Konfiguriert die Sicherheitsstufe für die Zone vertrauenswürdiger Sites.
-   **Hohe Sicherheit für eingeschränkte Sites:** Konfiguriert die Sicherheitsstufe für Zone eingeschränkter Sites.
-   **Menüzugriff im Unternehmensmodus:** Ermöglicht Benutzern, auf die Menüoptionen für den Unternehmensmodus von Internet Explorer zuzugreifen.
Wenn Sie diese Einstellung ausgewählt haben, können Sie auch einen **Speicherort des Protokollberichts** angeben. Dieser enthält eine URL zu einem Bericht, in dem Websites angezeigt werden, für die Benutzer Zugriff im Unternehmensmodus aktiviert haben.
-   **Speicherort der Websiteliste für den Unternehmensmodus:** Gibt den Speicherort der Liste der Websites an, die den Unternehmensmodus verwenden, wenn er aktiv ist.
## <a name="cellular"></a>Mobilfunk
-   **Datenroaming:** Erlaubt das Datenroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird.
## <a name="cloud-and-storage"></a>Cloud und Speicher
-   **Arbeitsordner-URL:** Legt die URL des Arbeitsordners so fest, damit Dokumente auf verschiedenen Geräten synchronisiert werden können.
-   **Zugriff auf Windows Mail-App ohne Microsoft-Konto:** Ermöglicht den Zugriff auf die Windows Mail-Anwendung ohne Microsoft-Konto.    



<!--HONumber=Feb17_HO1-->

