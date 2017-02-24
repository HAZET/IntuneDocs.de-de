---
title: "Einstellungen für App-Schutzrichtlinien für Android | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): In diesem Thema werden die Einstellungen für App Schutzrichtlinien für Android-Geräte beschrieben."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 6720c163e712e9d27319b16b0e1515e9e7f13ee8


---

# <a name="android-app-protection-policy-settings"></a>Einstellungen für App-Schutzrichtlinien für Android
Die in diesem Thema beschriebenen Richtlinieneinstellungen können im Azure-Portal auf dem Blatt **Einstellungen** für eine Schutzrichtlinie [konfiguriert](app-protection-policies.md) werden.
Es gibt zwei Kategorien von Richtlinieneinstellungen: Datenverlagerungs- und Zugriffseinstellungen. In diesem Thema bezieht sich der Begriff *richtlinienverwaltete Apps* auf Apps, die mit App-Schutzrichtlinien konfiguriert sind.

##  <a name="data-relocation-settings"></a>Einstellungen für die Datenverlagerung

| Einstellung | Verwendung | Standardwert(e) |
|------|------|------|
| **Android-Sicherungen verhindern** | Wählen Sie **Ja**, um zu verhindern, dass diese App Geschäfts-, Schul- oder Unidaten im [Android-Sicherungsdienst](https://developer.android.com/google/backup/index.html) sichert. Wählen Sie **Nein**, um der App zu erlauben, Geschäfts-, Schul- oder Unidaten zu sichern.| Ja |
| **App Übertragung von Daten an andere Apps erlauben** | Geben Sie an, welche Apps Daten von dieser App empfangen können: <ul><li> **Richtlinienverwaltete Apps**: Datenübertragung nur an andere richtlinienverwaltete Apps zulassen</li> <li>**Alle Apps**: Datenübertragung an beliebige Apps zulassen </li> <li>**Keine**: Keine Datenübertragung an beliebige Apps zulassen, auch nicht an andere richtlinienverwaltete Apps.</li></ul> | Alle Apps |
| **App Empfang von Daten aus anderen Apps erlauben** | Geben Sie an, welche Apps Daten an diese App übertragen können: <ul><li>**Richtlinienverwaltete Apps**: Datenübertragung nur von anderen richtlinienverwalteten Apps zulassen</li><li>**Alle Apps**: Datenübertragung von beliebigen Apps zulassen</li><li>**Keine**: Keine Datenübertragung von beliebigen Apps zulassen, auch nicht von anderen richtlinienverwalteten Apps | Alle Apps |
| **„Speichern unter“ verhindern** | Wählen Sie **Ja** aus, um die Verwendung der Option „Speichern unter“ in dieser App zu deaktivieren. Wählen Sie **Nein** aus, wenn die Verwendung von „Speichern unter“ zulässig sein soll. | Nein |
| **Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps** | Geben Sie an, wann Ausschneide-, Kopier- und Einfügeaktionen in dieser App erlaubt sind. Wählen Sie aus: <ul><li>**Blockiert**: Ausschneide-, Kopier- und Einfügeaktionen zwischen dieser App und anderen Apps nicht zulassen.</li><li>**Richtlinienverwaltete Apps**: Nur Ausschneide-, Kopier- und Einfügeaktionen zwischen dieser App und anderen richtlinienverwalteten Apps zulassen.</li><li>**Richtlinienverwaltete Apps mit Einfügen**: Ausschneiden oder Kopieren zwischen dieser App und anderen richtlinienverwalteten Apps zulassen. Einfügen von Daten aus beliebigen Apps in diese App zulassen.</li><li>**Jede App**: Keine Einschränkungen für das Ausschneiden, Kopieren und Einfügen in und aus dieser App. | Jede App |
|**Anzeige von Webinhalten auf den Managed Browser beschränken** | Wählen Sie **Ja**, um zu erzwingen, dass Weblinks in der App in der Managed Browser-App geöffnet werden. <br><br> Auf Geräten, die nicht bei Intune registriert sind, können Weblinks in richtlinienverwalteten Apps nur in der Managed Browser-App geöffnet werden. <br><br> Wenn Sie Intune zum Verwalten Ihrer Geräte verwenden, lesen Sie [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-internet-access-using-managed-browser-policies). | Nein |
| **App-Daten verschlüsseln** | Wählen Sie **Ja**, um die Verschlüsselung von Geschäfts-, Schul- oder Unidaten in dieser App zu aktivieren. Intune verwendet ein OpenSSL-Verschlüsselungsschema sowie das Android Keystore-System, um App-Daten sicher zu verschlüsseln. Daten werden während der Datei-E/A-Tasks synchron verschlüsselt. Inhalt im Gerätespeicher wird immer verschlüsselt. <br><br> Die Verschlüsselungsmethode ist **nicht** FIPS 140-2-zertifiziert.  | Ja |
| **Kontaktsynchronisierung deaktivieren** | Wählen Sie **Ja**, um zu verhindern, dass die App Daten in der nativen App „Kontakte“ auf dem Gerät speichert. Wenn Sie **Nein** wählen, darf die App Daten in der nativen App „Kontakte“ auf dem Gerät speichern. <br><br>Bei Ausführung eines selektiven Zurücksetzens zum Entfernen von Geschäfts-, Schul- oder Unidaten aus der App werden Kontakte entfernt, die direkt aus der App in die native App „Kontakte“ synchronisiert wurden. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die Microsoft Outlook-App. | Nein |
| **Drucken deaktivieren** | Wählen Sie **Ja**, um zu verhindern, dass die App Geschäfts-, Schul- oder Unidaten druckt. | Nein |


  >[!NOTE]
  >Die Verschlüsselungsmethode für die Einstellung **App-Daten verschlüsseln** ist **nicht** FIPS 140-2-zertifiziert.




##  <a name="access-settings"></a>Zugriffseinstellungen

| Einstellung | Verwendung | Standardwert(e) |
|------|------|------|
| **PIN für Zugriff anfordern** | Wählen Sie **Ja**, um zum Verwenden dieser App eine PIN anzufordern. Benutzer werden beim ersten Ausführen der App in einem Geschäfts-, Schul- oder Unikontext aufgefordert, diese PIN einzurichten. Standardwert = **Ja**<br><br> Konfigurieren Sie die folgenden Einstellungen für die PIN: <ul><li>**Anzahl der Versuche vor dem Zurücksetzen der PIN**: Geben Sie die Anzahl der Versuche an, die der Benutzer zum erfolgreichen Eingeben seiner PIN hat, ehe diese zurückgesetzt werden muss. Standardwert = **5**.</li><li> **Einfache PIN zulassen:** Wählen Sie **Ja**, um Benutzern das Verwenden einfacher PIN-Sequenzen wie z.B. 1234 oder 1111 zu erlauben. Wählen Sie **Nein**, um zu verhindern, dass einfache Sequenzen verwendet werden. Standardwert = **Ja** </li><li> **PIN-Länge:** Geben Sie die Mindestanzahl von Ziffern in einer PIN-Sequenz an. Standardwert = **4** </li><li> **Fingerabdruck anstelle von PIN zulassen (Android 6.0+):** Wählen Sie **Ja**, um Benutzern für den Zugriff auf die App das Verwenden der [Authentifizierung per Fingerabdruck](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) anstelle einer PIN zu erlauben. Standardwert = **Ja**<br><br> Auf Android-Geräten können Sie es Benutzern ermöglichen, ihre Identität durch Verwendung der [Android-Fingerabdruckauthentifizierung](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) anstatt mit einer PIN nachzuweisen. Wenn der Benutzer versucht, diese App mit seinem Geschäfts-, Schul- oder Unikonto zu nutzen, wird er aufgefordert, seine Identität per Fingerabdruck und nicht durch Eingabe einer PIN zu bestätigen. </li></ul>| PIN anfordern: Ja <br><br> Versuche zum Zurücksetzen der PIN: 5 <br><br> Einfache PIN zulassen: Ja <br><br> PIN-Länge: 4 <br><br> Fingerabdruckentsperrung zulassen: Ja |
| **Unternehmensanmeldeinformationen für Zugriff erforderlich** | Wählen Sie **Ja**, um anzufordern, dass sich der Benutzer für den Zugriff auf die App mit seinem Geschäfts-, Schul- oder Unikonto anmeldet, anstatt eine PIN einzugeben. Wenn Sie diese Einstellung auf **Ja** festlegen, sind PIN oder Fingerabdruckidentifizierung damit hinfällig.  | Nein |
| **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren** |  Wählen Sie **Ja** aus, um die Ausführung dieser App auf per Jailbreak oder Rootzugriff manipulierten Geräten zu verhindern. Der Benutzer kann diese App weiterhin für private Zwecke verwenden, muss jedoch für den Zugriff auf Geschäfts-, Schul- oder Unidaten ein anderes Gerät verwenden. | Ja |
| **Überprüfen der Zugriffsanforderungen nach (Minuten)** | Konfigurieren Sie die folgenden Einstellungen: <ul><li>**Timeout:** Geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen der App erneut überprüft werden. Standardwert = **30** Minuten.</li><li>**Offline-Toleranzperiode**: Wenn das Gerät offline ist, geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen für die App erneut geprüft werden. Standardwert = **720** Minuten (12 Stunden).</li></ul>| Timeout: 30 <br><br> Offline: 720 |
| **Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden** | Geschäfts-, Schul- oder Unidaten in dieser App können zurückgesetzt werden, wenn ein Gerät über einen bestimmten Zeitraum hinaus offline war. Legen Sie die Anzahl der Tage fest, die ein Gerät offline sein kann, ehe die Geschäfts-, Schul- oder Unidaten vom Gerät entfernt werden. <br><br> | 90 Tage |
| **Bildschirmaufnahme und Android-Assistent blockieren (Android 6.0+)** | Wählen Sie **Ja** aus, um die Bildschirmaufnahme und den **Android-Assistenten** des Geräts zu blockieren, wenn diese App verwendet wird. Bei der Auswahl von **Ja** wird auch das Vorschaubild für den App-Schnellzugriff unscharf, wenn diese App mit einem Geschäfts-, Schul- oder Unikonto verwendet wird. | Nein |



<!--HONumber=Feb17_HO1-->

