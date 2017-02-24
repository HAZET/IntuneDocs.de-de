---
title: Erste Schritte mit Gruppen in der Vorschau von Intune im Azure-Portal | Microsoft Docs
description: Erfahren Sie Neuigkeiten mit Gruppen in der Vorschau von Intune im Azure-Portal.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Erste Schritte mit Gruppen

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Wir haben Ihr Feedback berücksichtigt und einige Änderungen für das Arbeiten mit Gruppen in Microsoft Intune vorgenommen.
Wenn Sie Intune über das Azure-Portal verwenden, wurden Ihre Intune-Gruppen zu Azure Active Directory-Sicherheitsgruppen migriert.

Der Vorteil für Sie ist, dass Sie jetzt in allen Ihren Enterprise Mobility + Security- und Azure AD-Apps dieselbe Gruppenumgebung verwenden. Darüber hinaus werden können Sie PowerShell und die Graph-API zum Erweitern und Anpassen dieser neuen Funktionalität nutzen.

Azure AD-Sicherheitsgruppen unterstützen alle Arten von Intune-Bereitstellungen für Benutzer und Geräte. Darüber hinaus können Sie dynamische Azure AD-Gruppen verwenden, die basierend auf den von Ihnen angegebenen Attributen automatisch aktualisiert werden. Sie können z.B. eine Gruppe von Geräten erstellen, auf denen iOS 9 ausgeführt wird. Sobald ein neues Gerät mit iOS 9 registriert wird, wird es automatisch der dynamischen Gruppe hinzugefügt.

## <a name="what-is-not-available"></a>Was ist nicht verfügbar?

Einige der Funktionen von Intune-Gruppen, die Sie eventuell zuvor verwendet haben, sind nicht in Azure AD verfügbar:

- Die Intune-Gruppen **Nicht gruppierte Benutzer** und **Nicht gruppierte Geräte** sind nicht mehr verfügbar.
- Die Option zum **Ausschließen bestimmter Mitglieder** aus einer Gruppe ist im Azure-Portal nicht vorhanden. Sie können jedoch eine Azure Active Directory-Sicherheitsgruppe mit erweiterter Regeln verwenden, um dieses Verhalten zu replizieren. So könnten Sie beispielsweise die erweiterte Regel `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")` erstellen, die alle Mitarbeiter der Abteilung „Vertrieb“ in einer Sicherheitsgruppe enthält, mit Ausnahme der Personen, deren Position das Wort „Assistent“ aufweist.
- Die Gruppe **Alle mit Exchange ActiveSync verwalteten Geräte**, die in der Intune-Konsole integriert ist, wurde nicht zu Azure AD migriert. Allerdings können Sie im Azure-Portal weiter auf Informationen zu mit Exchange ActiveSync verwalteten Geräten zugreifen.


## <a name="how-to-get-started"></a>Erste Schritte

- Lesen Sie die folgenden Azure AD-Themen, um mehr über Azure AD-Sicherheitsgruppen und ihre Funktionsweise zu erfahren:
    -  [Verwalten des Zugriffs auf Ressourcen mit Azure Active Directory-Gruppen](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)
    -  [Verwalten von Gruppen in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)
    -  [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)
-  Stellen Sie sicher, dass Administratoren, die Gruppen erstellen müssen, der Azure AD-Rolle **Intune-Dienstadministrator** hinzugefügt werden. Beachten Sie, dass die Azure AD-Rolle „Dienstadministrator“ nicht die Berechtigung **Gruppe verwalten** hat.
-  Wenn Sie Gruppen mit der Option **Bestimmte Mitglieder ausschließen** verwendet haben, prüfen Sie, ob Sie diese Gruppe so ändern können, dass keine Ausschlüsse erforderlich sind, oder ob Sie in Ihrer Azure AD-Abfrage erweiterte Regeln nutzen können, um dasselbe Ergebnis zu erzielen.


## <a name="what-happened-to-intune-groups"></a>Was ist mit Intune-Gruppen geschehen?

| Gruppen in Intune|Gruppen in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statische Benutzergruppe|Statische Azure AD-Sicherheitsgruppe|
|Dynamische Benutzergruppe|Statische Azure AD-Sicherheitsgruppen mit einer Hierarchie von Azure AD-Sicherheitsgruppen|
|Statische Gerätegruppe|Statische Azure AD-Sicherheitsgruppe|
|Dynamische Gerätegruppe|Dynamische Azure AD-Sicherheitsgruppe|
|Eine Gruppe mit einer Einschlussbedingung|Statische Azure AD-Sicherheitsgruppe mit statischen oder dynamischen Mitgliedern nach Verwenden der Bedingung „Einschließen“ in Intune|
|Eine Gruppe mit einer Ausschlussbedingung|Nicht migriert|
|Die integrierten Gruppen **Alle Benutzer**, **Nicht gruppierte Benutzer**, **Alle Geräte**, **Nicht gruppierte Geräte**, **Alle Computer**, **Alle mobilen Geräte**, **Alle mit MDM verwalteten Geräte** und **Alle mit EAS verwalteten Geräte**|Azure AD-Sicherheitsgruppen|

In Intune müssen alle Gruppen eine übergeordnete Gruppe haben. Gruppen können nur Mitglieder aus der übergeordneten Gruppe enthalten. In Azure AD können untergeordnete Gruppen Mitglieder enthalten, die die übergeordnete Gruppe nicht aufweist.

Attribute sind Geräteeigenschaften, die bei der Definition von Gruppen verwendet werden können. In der folgenden Tabelle wird beschrieben, wie diese Kriterien zu Azure AD-Sicherheitsgruppen migriert werden.

| Attribut in Intune|Attribut in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|OE-Attribut (Organisationseinheit) für Gerätegruppen|OE-Attribut für dynamische Gruppen.|
|Domänennamenattribut für Gerätegruppen|Domänennamenattribut für dynamische Gruppen.|
|Sicherheitsgruppe als Attribut für Benutzergruppen|In dynamischen Azure AD-Abfragen können Gruppen nicht als Attribute verwendet werden. Dynamische Gruppen dürfen nur benutzer- oder gerätespezifische Attribute enthalten.|
|Manager-Attribut für Benutzergruppen|Erweiterte Regel für das *Manager*-Attribut in dynamischen Gruppen|
|Alle Benutzer der übergeordneten Benutzergruppe|Statische Gruppe, die diese Gruppe als Mitglied enthält|
|Alle mobilen Geräte der übergeordneten Gerätegruppe|Statische Gruppe, die diese Gruppe als Mitglied enthält|
|Alle von Intune verwalteten mobilen Geräte|Verwaltungstypattribut mit dem Wert „MDM“ für dynamische Gruppen|
|Verschachtelte Gruppen in statischen Gruppen |Verschachtelte Gruppen in statischen Gruppen|
|Verschachtelte Gruppen in dynamischen Gruppen|Dynamische Gruppe mit einer Schachtelungsebene|

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Was geschieht mit Richtlinien und Apps, die Sie bereitgestellt haben?

Richtlinien und Apps werden Gruppen wie bisher weiter bereitgestellt. Allerdings verwalten Sie diese Gruppen jetzt im Azure-Portal statt in der klassischen Intune-Konsole.



<!--HONumber=Feb17_HO1-->

