---
title: Che cos'è Call Quality Dashboard (Call Quality Dashboard)?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su Call Quality Dashboard (Call Quality Dashboard) e su come usarlo per visualizzare i report sulla qualità delle riunioni e delle chiamate in Microsoft teams.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088244"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Che cos'è Call Quality Dashboard (Call Quality Dashboard)?

Microsoft Call Quality Dashboard (Call Quality Dashboard)- [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) -Mostra la qualità delle chiamate e delle riunioni a **livello di organizzazione**per Microsoft teams, Skype for business online e Skype for Business Server 2019. 

  
La versione più recente di Call Quality dashboard include un [feed di dati in tempo reale (NRT)](CQD-data-and-reports.md), che indica che i record di chiamata sono disponibili in Call Quality dashboard entro 30 minuti dalla fine di una chiamata.

Ovunque Call Quality dashboard includa [dati di identificazione dell'utente finale (EUII)](CQD-data-and-reports.md#euii-data), viene gestito allo stesso modo di EUII in [Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

Call Quality dashboard è progettato per aiutare gli amministratori del team, gli amministratori di Skype for business e i tecnici di rete a monitorare la qualità delle chiamate e delle riunioni a livello di organizzazione. Userai Call Quality dashboard per **ottimizzare la rete** per migliorare la qualità delle prestazioni. Quando devi esaminare le informazioni di chiamata e riunione per un **utente specifico**, USA i dati di Call Quality dashboard in combinazione con le [analisi delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)per utente.

Usando Call Quality dashboard, ad esempio, puoi determinare che la qualità di chiamata scadente di un utente (che hai osservato usando l'analisi delle chiamate per utente) è dovuta a un problema di rete che interessa anche molti altri utenti. Call Quality dashboard acquisisce sia l'esperienza di chiamata individuale che la qualità complessiva delle chiamate effettuate tramite teams o Skype for business. Con Call Quality dashboard, i modelli generali possono diventare evidenti, in modo che gli ingegneri di rete possano effettuare valutazioni informate sulla qualità delle chiamate. Call Quality dashboard fornisce report sulle metriche di qualità delle chiamate che consentono di comprendere la qualità complessiva delle chiamate, i flussi client-server, i flussi client-client e la qualità della voce [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Screenshot del dashboard qualità chiamata.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In Call Quality dashboard invitiamo a caricare le informazioni sulla creazione e sull'endpoint, che consente di usare report con funzionalità avanzate per analizzare la qualità e l'affidabilità delle chiamate all'interno di un edificio dell'utente. I dati possono essere valutati per determinare se il problema è isolato da un singolo utente o influisce su un segmento più grande di utenti. Per attivare visualizzazioni specifiche di un edificio o di un endpoint in Call Quality dashboard, un amministratore deve [caricare le informazioni sulla compilazione o sull'endpoint](CQD-upload-tenant-building-data.md) nella pagina di **caricamento dei dati del tenant** di Call Quality dashboard.

![Screenshot dei report di posizione avanzata di Call Quality dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Non perdere l'articolo [Gestisci la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md) , che offre indicazioni approfondite per l'amministratore del team o il tecnico del supporto responsabile della gestione della qualità dei servizi in teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versione precedente di Call Quality Dashboard (CQD.lync.com)

La versione corrente di Call Quality Dashboard ( https://CQD.Teams.microsoft.com) sostituisce la versione precedente di Call Quality Dashboard ( https://CQD.lync.com) . È comunque possibile usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for business), ma dal 1 ° luglio 2020 USA i dati di Call Quality dashboard. Teams.microsoft.com. Disattiveremo presto l'accesso a CQD.lync.com, quindi devi trasferirti in Call Quality dashboard. Teams.microsoft.com se non è già stato fatto.

> [!IMPORTANT]
> A partire dal 1 ° luglio 2020, non è più possibile visualizzare o modificare l'edificio o i dati di query dal vecchio Call Quality Dashboard (CQD.lync.com). Se non sono già stati migrati questi dati da CQD.lync.com e ne è ancora necessario, registrare un ticket di supporto.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di Call Quality dashboard

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.

Leggere [usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md) per altre informazioni.



## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

[Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e della creazione](CQD-upload-tenant-building-data.md)

[Dati e report di Call Quality dashboard](CQD-data-and-reports.md)

[Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in Call Quality dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md)


[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)