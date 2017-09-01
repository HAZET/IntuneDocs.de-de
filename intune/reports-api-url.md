---
title: Endpunkt der Intune Data Warehouse-API | Microsoft-Dokumentation
description: Das Referenzthema beschreibt die API-URL-Struktur.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Endpunkt der Intune Data Warehouse-API

Sie können die Intune-Data Warehouse-API mit einem Konto mit bestimmten rollenbasierten Zugriffssteuerungen und Azure AD-Anmeldeinformationen verwenden. Anschließend autorisieren Sie Ihren REST-Client mithilfe von OAuth 2.0 für Azure AD. Schließlich erstellen Sie eine aussagekräftige URL, um eine Data Warehouse-Ressource aufzurufen.

## <a name="azure-ad-and-intune-credential-requirements"></a>Anforderungen an die Anmeldeinformationen für Azure AD und Intune

Authentifizierung und Autorisierung basieren auf Azure AD-Anmeldeinformationen und rollenbasierter Zugriffssteuerung über Intune (RBAC). Alle globalen Administratoren und Intune-Serviceadministratoren für Ihren Mandanten haben standardmäßig Zugriff auf die API. Verwenden Sie Intune-Rollen, um den Zugriff für mehr Benutzer bereitzustellen, indem Sie Ihnen Zugriff auf die **Reporting resource** (Berichtsressource) gewähren.

Anforderungen für den Zugriff auf die API sind:

  -  Intune-Lizenz muss dem Benutzer zugewiesen sein
  -  Benutzer muss eine der folgenden Rollen innehaben:
      -  Globaler Azure AD-Administrator
      -  Intune-Dienstadministrator
      -  Benutzer mit rollenbasiertem Zugriff auf die Ressource **Reports** (Berichte)

## <a name="authorization"></a>Autorisierung

Azure Active Directory (Azure AD) bietet Ihnen über OAuth 2.0 die Möglichkeit, den Zugriff auf Webanwendungen und Web-APIs in Ihrem Azure AD-Mandanten zu autorisieren. Dieses Handbuch ist sprachenunabhängig und beschreibt, wie HTTP-Nachrichten gesendet und empfangen werden können, ohne irgendeine unserer Open Source-Bibliotheken zu verwenden. Der Codefluss zur Autorisierung mit OAuth 2.0 wird in [section 4.1 (Abschnitt 4.1)](https://tools.ietf.org/html/rfc6749#section-4.1) der OAuth 2.0-Spezifikation beschrieben.

Weitere Informationen finden Sie unter [Authorize access to web applications using OAuth 2.0 and Azure Active Directory (Autorisieren des Zugriffs zu Webanwendungen mithilfe von OAuth 2.0 und Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>API-URL-Struktur

Die Endpunkte der Data Warehouse-API lesen die Entitäten für jeden Satz. Die API unterstützt ein **GET** HTTP-Verb und eine Teilmenge der Abfrageoptionen.

Die URL für Intune verwendet das folgende Format:  
https://fef. {***Speicherort***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/ {***Entitätssammlung***}? api-Version = {***-API-Version***}

Die URL enthält die folgenden Elemente:

| Element | Beispiel | Beschreibung |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Die Basis-URL kann im Blatt „Data Warehouse API“ im Azure Portal gefunden werden. |
| Entitätssammlung | Daten | Der Name der OData-Entitätssammlung. Weitere Informationen zu Sammlungen und Entitäten im Datenmodell finden Sie unter [Data Model (Datenmodell)](reports-ref-data-model.md). |
| api-version | Beta | Die Version ist die Version der API, auf die zugegriffen wird. Weitere Informationen finden Sie unter [Version](#API-version-information). |


## <a name="api-version-information"></a>Information zur API-Version

Die aktuelle Version der API ist `beta`. 

## <a name="odata-query-options"></a>OData-Abfrageoptionen

Die aktuelle Version unterstützt die folgenden OData-Abfrageparameter: `$skip, $top, $filter, $orderby`.