---
title: "Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7c454584df4f0eb6b3a9dfe10ee7b887bcdee2ca
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="your-device-is-missing-a-required-certificate"></a>Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden

## <a name="whats-a-certificate"></a>Was ist ein Zertifikat?

Die [Kryptografie](https://technet.microsoft.com/library/cc962030.aspx) ist die Wissenschaft der Verschlüsselung von Informationen. Traditionell wird Kryptografie zur Weitergabe codierter Nachrichten verwendet, um [sicherzustellen, dass die Kommunikation geheim bleibt](https://technet.microsoft.com/library/cc962019.aspx). In ihrer einfachsten Form werden bei der Kryptografie Buchstaben ersetzt oder vertauscht, um eine nicht lesbare, unverständliche oder verborgene Nachricht zu erstellen. Nur jemand mit einem Decodierungsschlüssel bzw. _Zertifikat_ kann die codierte Nachricht wieder in ihre ursprüngliche, lesbare Form umwandeln. Ihr Android-Gerät verwendet Zertifikate für Intune, um sicherzustellen, dass die Kommunikation zwischen Ihrem Gerät und Ihren Organisationsressourcen – z.B. E-Mails oder Dokumenten – während der drahtlosen Übertragung vom einen bis zum anderen Ende sicher und geschützt ist.

## <a name="fixing-certificate-issues"></a>Beheben von Problemen mit Zertifikaten

Wenn Ihr Android-Gerät nicht bei Intune registriert ist und ein bestimmtes Zertifikat fehlt, das vom Support Ihres Unternehmens verlangt wird, können Sie sich nicht bei der Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Zunächst sollten Sie ermitteln, ob auf Ihrem Gerät [ein Zertifikat fehlt, das normalerweise auf dem Gerät vorinstalliert ist](your-device-is-missing-a-preinstalled-certificate-android.md).

Wenn dies nicht funktioniert, fordert der Support Ihres Unternehmens Sie möglicherweise auf, [ein zweites Zertifikat zu installieren, um die Sicherheit zu erhöhen](your-device-is-missing-an-IT-required-certificate-android.md).

Benötigen Sie weitere Unterstützung? Kontaktieren Sie den Support Ihres Unternehmens. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).
