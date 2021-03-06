---
title: Integrieren der Netzwerkzugriffssteuerung mit Intune
titlesuffix: Azure portal
description: Integrieren der Netzwerkzugriffssteuerung (NAC) mit Intune
keywords: 
author: bruceperlerMS
ms.author: bruceper
manager: dougeby
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4673a6c6d0b83c7f31eecc919bcaa0e952f373a0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integrieren der Netzwerkzugriffssteuerung (NAC) mit Intune

Intune arbeitet mit Partnern der Netzwerkzugriffssteuerung zusammen, um Organisationen beim Schützen von Unternehmensdaten zu helfen, wenn Geräte versuchen, auf lokale Ressourcen zuzugreifen.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Wie helfen Lösungen von Intune und NAC beim Schutz der Ressourcen Ihrer Organisation?

Die Aufgabe von NAC-Lösungen besteht darin, den Registrierungs- und Kompatibilitätsstatus des Geräts mit Intune zu überprüfen, um Entscheidungen bezüglich der Zugriffssteuerung zu treffen. Wenn das Gerät nicht registriert ist oder registriert ist, aber nicht den Intune-Gerätekompatibilitätsrichtlinien entspricht, sollte das Gerät für die Registrierung und/oder eine Kompatibilitätsprüfung an Intune weitergeleitet werden.

### <a name="example"></a>Beispiel

Wenn das Gerät registriert und mit Intune kompatibel ist, sollte die NAC-Lösung dem Gerät den Zugriff auf Unternehmensressourcen erlauben. Benutzern kann beispielsweise der Zugriff auf das Unternehmens-WLAN oder VPN-Ressourcen gewährt oder verweigert werden.

## <a name="feature-behaviors"></a>Featureverhalten

Geräte, die aktiv mit Intune synchronisieren, können nicht vom Zustand **Konform** / **Nicht konform** in **Nicht synchronisiert** (oder **Unbekannt**) wechseln. Der Zustand **Unbekannt** ist für neu registrierte Geräte reserviert, die noch nicht im Hinblick auf ihre Konformität ausgewertet wurden.

Bei Geräten, die für den Zugriff auf Ressourcen blockiert sind, sollte der blockierende Dienst alle Benutzer auf das [Verwaltungsportal](https://portal.manage.microsoft.com) umleiten, um festzustellen, warum das Gerät blockiert ist.  Wenn die Benutzer diese Seite besuchen, werden ihre Geräte erneut synchron im Hinblick auf Konformität ausgewertet.

## <a name="nac-and-conditional-access"></a>NAC und bedingter Zugriff

NAC nutzt bei Entscheidungen bezüglich der Zugriffssteuerung den bedingten Zugriff. Weitere Informationen finden Sie unter [Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Funktionsweise der NAC-Integration

Im Folgenden erhalten Sie einen Überblick darüber, wie die NAC-Integration funktioniert, wenn sie in Intune integriert ist. In den ersten drei Schritten 1-3 wird der Onboardingprozess erklärt. Nachdem die NAC-Lösung in Intune integriert wurde, beschreiben die Schritte 4-9 den laufenden Betrieb.

![Wie NAC und Intune zusammenarbeiten](./media/ca-intune-common-ways-2.png)

1. Registrieren Sie die Lösung des NAC-Partners mit Azure Active Directory (AAD), und gewähren Sie delegierte Berechtigungen an die Intune-NAC-API.
2. Konfigurieren Sie die Lösung des NAC-Partners mit den geeigneten Einstellungen, darunter die URL für die Intune-Ermittlung.
3. Konfigurieren Sie die Lösung des NAC-Partners für die Zertifikatauthentifizierung.
4. Der Benutzer stellt eine Verbindung zum WLAN-Zugriffspunkt her oder fordert eine VPN-Verbindung an.
5. Die Lösung des NAC-Partners leitet die Geräteinformationen an Intune weiter und fragt Intune nach dem Registrierungs- und Kompatibilitätsstatus des Geräts.
6. Wenn das Gerät nicht kompatibel oder nicht registriert ist, weist die Lösung des NAC-Partners den Benutzer an, das Gerät zu registrieren oder kompatibel zu machen.
7. Das Gerät versucht, seinen Konformitäts- und/oder Registrierungszustand erneut zu überprüfen.
8. Wenn das Gerät registriert wurde und kompatibel ist, erhält die Lösung des NAC-Partners von Intune eine Statusmeldung.
9. Die Verbindung konnte erfolgreich hergestellt werden, und das Gerät erhält Zugriff auf Unternehmensressourcen.

## <a name="next-steps"></a>Nächste Schritte

- [Integrieren von Cisco ISE mit Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Integrieren von Citrix NetScaler mit Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Integrieren von HPE Aruba ClearPass mit Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
