---
title: Che cos'è Call Quality Dashboard (CQD)?
ms.author: serdars
author: SerdarSoysal
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
description: Informazioni su Call Quality Dashboard (CQD) e su come usarlo per visualizzare report sulla qualità delle riunioni e delle chiamate in Microsoft Teams.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583485"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Che cos'è Call Quality Dashboard (CQD)?

Microsoft Call Quality Dashboard (CQD) - mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019.  

  
L'ultima versione di CQD include un feed di dati [near-real-time (NRT),](CQD-data-and-reports.md)il che significa che i record di chiamata sono disponibili in Call Entro 30 minuti dalla fine della chiamata.

Quando CQD include dati di identificazione dell'utente finale [(EUII),](CQD-data-and-reports.md#euii-data)viene gestito allo stesso modo dell'UEI [in tutto Microsoft 365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

CQD è progettato per aiutare gli amministratori di Teams, gli amministratori di Skype for Business e i tecnici di rete a monitorare la qualità delle chiamate e delle riunioni a livello di organizzazione. Userai CQD per ottimizzare la **rete per** ottimizzare la qualità delle prestazioni. Quando devi esaminare le informazioni relative **a** chiamate e riunioni per un utente specifico, usa I dati di Call Call In combinazione con l'analisi delle chiamate per [utente.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Ad esempio, utilizzando Call Quality, è possibile stabilire che la qualità scarsa delle chiamate di un utente (osservata mediante l'analisi delle chiamate per utente) è causata da un problema di rete che interessa anche molti altri utenti. CQD acquisisce sia l'esperienza singola delle chiamate che la qualità complessiva delle chiamate effettuate con Teams o Skype for Business. Con CQD possono diventare visibili modelli generali, in modo che i tecnici di rete possano effettuare valutazioni informate della qualità delle chiamate. CQD fornisce rapporti sulle metriche di chiamata che ti forniscono informazioni approfondite sulla qualità complessiva delle chiamate, i flussi server-client, i flussi client-client e l'SLA sulla [qualità vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Screenshot di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In CQD consigliamo di caricare informazioni sull'edificio e sull'endpoint, che consentono di usare i report di Location-Enhanced per analizzare la qualità e l'affidabilità delle chiamate all'interno dell'edificio di un utente. I dati possono essere valutati per determinare se il problema è isolato da un singolo utente o interessa un segmento più ampio di utenti. Per attivare la creazione di visualizzazioni specifiche dell'endpoint o dell'edificio in CQD, un amministratore deve caricare le informazioni sull'edificio o [sull'endpoint](CQD-upload-tenant-building-data.md) nella pagina di caricamento dei dati del **tenant di** CQD.

![Screenshot dei report di qualità Location-Enhanced chiamata di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Non perderti l'articolo [Gestisci](quality-of-experience-review-guide.md) qualità delle chiamate e delle riunioni, che offre indicazioni approfondite per l'amministratore di Teams o l'ingegnere del supporto responsabile della gestione della qualità del servizio in Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versione precedente di CQD (CQD.lync.com)

La versione corrente di CQD ( https://CQD.Teams.microsoft.com) sostituisce la versione precedente di CQD ( https://CQD.lync.com) . È ancora possibile utilizzare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for Business), ma dal 1° luglio 2020 viene utilizzato il dato di CQD. Teams.microsoft.com. A breve verrà disattivato l'accesso CQD.lync.com, quindi è consigliabile passare a CQD. Teams.microsoft.com se non è già stato fatto.

> [!IMPORTANT]
> A partire dal 1° luglio 2020, non sarà più possibile visualizzare o modificare i dati dell'edificio o della query dal vecchio CQD (CQD.lync.com). Se la migrazione dei dati da CQD.lync.com è ancora necessaria, registrare un ticket di supporto.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di CQD

Novità di gennaio 2020: scaricare i modelli di query di [Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di CQD.

Leggere [Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md) per ottenere altre informazioni.



## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report di CQD](CQD-data-and-reports.md)

[Usare Call Quality Quality Call per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md)


[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)