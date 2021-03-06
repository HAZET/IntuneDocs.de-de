---
title: "Überwachungsprotokolle für Intune-Aktivitäten"
description: "Erfahren Sie, wie Sie Überwachungsprotokolle, die Intune-Aktivitäten erfassen, überprüfen können."
keywords: 
author: dougeby
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: b2f6f6f4829e53d60cc259be220de89cf3f8d97d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="audit-logs-for-intune-activities"></a>Überwachungsprotokolle für Intune-Aktivitäten
Überwachungsprotokolle stellen Ihnen einen Datensatz von Aktivitäten zur Verfügung, die eine Änderung in Microsoft Intune bewirken. Sie können Aktionen oder Remotetasks erstellen, aktualisieren (bearbeiten), löschen und zuweisen sowie überprüfbare Überwachungsereignisse generieren. Sie können Überwachungsprotokolle für die meisten Intune-Workloads überprüfen. 

## <a name="who-can-access-the-data"></a>Wer kann auf die Daten zugreifen?
Benutzer mit den folgenden Berechtigungen können Überwachungsprotokolle überprüfen:
- Globaler Administrator
- Intune-Dienstadministrator
- Administratoren, denen eine Intune-Rolle mit den Berechtigungen **Überwachungsdaten** - **Lesen** zugewiesen wurde

## <a name="audit-logs-for-intune-workloads"></a>Überwachungsprotokolle für Intune-Workloads
Sie können für jede Intune-Workload Überwachungsprotokolle in der Überwachungsgruppe einsehen.  
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Workload, für die Sie Überwachungsprotokolle überprüfen möchten.
4. Wählen Sie für die Workload in der Gruppe **Überwachung** die Option **Überwachungsprotokolle**.

## <a name="review-audit-events"></a>Überprüfen von Überwachungsereignissen
![Überwachungsprotokolle](./media/monitor-audit-logs.png "Audit logs")

Ein Überwachungsprotokoll verfügt über eine Standardlistenansicht, in der die folgenden Elemente angezeigt werden:    

- Datum und Uhrzeit des Auftretens
- Initiiert von (Akteur)
- Aktivität
- Ziel(e)
- Category
- Status

Wenn Sie auf ein Element in der Listenansicht klicken, erhalten Sie alle verfügbaren Details zu diesem Element.

![Überwachungsprotokolle](./media/monitor-audit-log-detail.png "Audit logs")

> [!Note]    
> Der Abschnitt **Initiiert von (Akteur)** in den Details des Überwachungsprotokolls enthält Informationen darüber, wer die Aktivität ausgeführt hat und von wo aus sie ausgeführt wurde. Wenn Sie beispielsweise im Azure-Portal in Intune die Aktivität ausführen, wird unter **Anwendung** immer **Microsoft Intune-Portalerweiterung** und unter **Anwendungs-ID** immer dieselbe GUID aufgeführt. 
>    
> Im Abschnitt **Ziel(e)** können mehrere Ziele und die geänderten Eigenschaften aufgeführt werden.  


## <a name="filter-audit-events"></a>Filtern von Überwachungsereignissen
Jede Workload verfügt über ein Menüelement, das die Kategorie der mit diesem Blatt verknüpften Überwachungsereignisse vorfiltert. Mit einer separaten Filteroption können Sie zu verschiedenen Kategorien wechseln und Details zu Ereignisaktionen innerhalb dieser Kategorie anzeigen. Sie können nach dem UPN suchen (z.B. nach dem Benutzer, der die Aktion ausgeführt hat). Ein Datumsbereichsfilter bietet die Optionen „24 Stunden“, „7 Tage“ oder „30 Tage“ an. Standardmäßig werden die letzten 30 Tage der Überwachungsereignisse angezeigt.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Abrufen von Überwachungsereignissen mithilfe der Graph-API
Einzelheiten darüber, wie Sie mithilfe der Graph-API Überwachungsereignissen von bis zu einem Jahr abrufen, finden Sie unter [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).