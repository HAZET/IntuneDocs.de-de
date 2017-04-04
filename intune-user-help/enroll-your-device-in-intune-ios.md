---
title: "Registrieren Ihres iOS-Geräts bei Intune | Microsoft-Dokumentation"
description: "Beschreibt, wie Sie ein iOS-Gerät bei Intune registrieren."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: af3313e6ba5cbf9184aaaa9b197f7a3b2b9d4c3e
ms.lasthandoff: 03/13/2017


---


# <a name="enroll-your-ios-device-in-intune"></a>Registrieren Ihres iOS-Geräts bei Intune

Wenn Ihr Unternehmen oder Ihre Schule Microsoft Intune verwendet, können Sie Ihr iOS-Gerät registrieren, um Zugriff auf Unternehmens-E-Mails, Dateien und weitere Ressourcen zu erhalten. Wenn Sie Ihre Geräte registrieren, kann Ihre IT-Abteilung diese Geschäfts-, Schul- oder Uniressourcen verwalten, schützen und Ihnen gleichzeitig die Möglichkeit bieten, Ihr bevorzugtes Gerät zu verwenden, um Ihre Arbeit erledigen. Weitere Informationen zur Registrierung finden Sie unter [Was geschieht, wenn Sie die Unternehmensportal-App installieren und Ihr Gerät bei Intune registrieren?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

> [!NOTE]
> Wenn Sie versuchen, ein macOS-Gerät – z.B. ein MacBook Pro oder einen iMac – zu registrieren, [folgen Sie stattdessen diesen Anweisungen](enroll-your-device-in-intune-macos.md).

**Vorbereitung:**

- Stellen Sie sicher, dass Sie die Registrierung auch abschließen, wenn Sie mit dieser Anleitung beginnen. Wird der Prozess für einen längeren Zeitraum unterbrochen, müssen Sie in der Regel von vorn beginnen.
- Sollte die Registrierung nicht erfolgreich sein, kehren Sie zur Unternehmensportal-App zurück, und versuchen Sie es erneut.
- Stellen Sie sicher, dass Ihr WLAN funktioniert. Andernfalls schlägt die Registrierung fehl.
- Wenn Sie Safari auf Ihrem Gerät blockieren, müssen Sie die Blockierung aufheben. Sie benötigen Safari für die Registrierung.


**So registrieren Sie Ihr iOS-Gerät:**

1.  Führen Sie die Schritte in [Installieren und Anmelden bei der Intune-Unternehmensportal-App](install-and-sign-in-to-the-intune-company-portal-app-ios.md) aus.

2. Tippen Sie auf der Seite **Unternehmenszugriff einrichten** auf **Beginnen**.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. Lesen Sie auf dem Bildschirm **Gründe für das Registrieren Ihres Geräts**, welche Möglichkeiten Sie haben, wenn Sie Ihr Gerät registrieren, und tippen Sie dann auf **Weiter**.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

> [!NOTE]
> Die gelben Dreiecke bedeuten nicht, dass bereits ein Fehler vorliegt. Sie geben lediglich an, dass für den Registrierungsprozess noch Schritte ausgeführt werden müssen.

4. Prüfen Sie in einer Liste, was Ihr IT-Administrator auf Ihrem registrierten Gerät einsehen kann und was nicht, und tippen Sie dann auf **Weiter**.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  Lesen Sie im Bildschirm **Was ist der nächste Schritt?**, was während der Registrierung passiert, und tippen Sie dann auf **Registrieren**.

     ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  Tippen Sie auf dem Bildschirm **Profil installieren** auf **Installieren**, und geben Sie bei Aufforderung Ihre Kennung ein.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  Tippen Sie auf **Installieren**.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  Tippen Sie auf **Installieren**, um anzugeben, dass Sie die Warnung gelesen haben.

       ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  Tippen Sie auf **Vertrauen**.

       ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  Wenn auf dem Bildschirm angezeigt wird, dass die Installation des Profils abgeschlossen ist, tippen Sie auf **Fertig**.

     ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    Auf dem Bildschirm wird die Meldung „Gerät wird registriert“ angezeigt.

11.  Wenn Sie in einer Meldung gefragt werden, ob Sie die Seite im Unternehmensportal öffnen möchten, tippen Sie auf **Öffnen**.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. Tippen Sie auf dem Bildschirm **Unternehmenszugriff einrichten** auf **Weiter**. Wenn Ihr IT-Administrator zusätzliche Sicherheitsanforderungen eingerichtet hat, z.B. die Notwendigkeit eines Kennworts, folgen Sie den Anweisungen auf dem Bildschirm, bis alle Kompatibilitätsanforderungen erfüllt sind und Sie zum Bildschirm „Unternehmenszugriff einrichten“ zurückkehren. Tippen Sie dann auf **Weiter**.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. Tippen Sie auf **Fertig**.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Ihr Gerät ist jetzt bei Intune registriert, und Sie gelangen wieder zur Unternehmensportal-App.

> [!Note]
> Wenn Ihre Organisation Telecom Expense Management-Software verwendet, müssen Sie ein paar zusätzliche Schritte ausführen, bevor das Gerät vollständig registriert ist. [Hier](enroll-your-device-with-telecom-expense-management-ios.md) erfahren Sie mehr.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).
