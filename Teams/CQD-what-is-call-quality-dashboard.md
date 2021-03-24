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
description: Informazioni su Call Quality Dashboard (CQD) e su come usarlo per visualizzare i report sulla qualità delle riunioni e delle chiamate in Microsoft Teams.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094940"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Che cos'è Call Quality Dashboard (CQD)?

Microsoft Call Quality Dashboard (CQD) - mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019.  

  
L'ultima versione di CQD include un feed di dati quasi in tempo reale [(NRT),](CQD-data-and-reports.md)il che significa che i record delle chiamate sono disponibili in CQD entro 30 minuti dalla fine di una chiamata.

Dove CQD include dati di informazioni identificabili per l'utente finale [(EUII),](CQD-data-and-reports.md#euii-data)viene gestito allo stesso modo di [EUII in Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

CQD è progettato per aiutare gli amministratori di Teams, gli amministratori di Skype for Business e i tecnici di rete a monitorare la qualità delle chiamate e delle riunioni a livello di organizzazione. Si userà CQD per ottimizzare la **rete per** migliorare la qualità delle prestazioni. Quando è necessario esaminare le informazioni di chiamata e riunione per un utente **specifico,** usare i dati CQD insieme all'analisi [delle chiamate per utente.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Ad esempio, usando CQD, è possibile determinare che la scarsa qualità delle chiamate di un utente (osservata con l'analisi delle chiamate per utente) è dovuta a un problema di rete che interessa anche molti altri utenti. CQD acquisisce sia l'esperienza delle singole chiamate che la qualità generale delle chiamate effettuate con Teams o Skype for Business. Con CQD, i modelli complessivi possono diventare evidenti, quindi i tecnici di rete possono effettuare valutazioni informate sulla qualità delle chiamate. CQD fornisce report sulle metriche sulla qualità delle chiamate che forniscono informazioni approfondite sulla qualità complessiva delle chiamate, i flussi server-client, i flussi client-client e il contratto di servizio sulla [qualità vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Screenshot di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In CQD ti consigliamo di caricare informazioni sull'edificio e sull'endpoint, che ti consentono di usare i report di Location-Enhanced per analizzare la qualità e l'affidabilità delle chiamate all'interno dell'edificio di un utente. I dati possono essere valutati per determinare se il problema è isolato per un singolo utente o interessa un segmento più ampio di utenti. Per attivare le visualizzazioni specifiche dell'edificio o [dell'endpoint](CQD-upload-tenant-building-data.md) in CQD, un amministratore deve caricare le informazioni sull'edificio o sull'endpoint nella pagina di caricamento dei dati del **tenant** CQD.

![Screenshot dei report Location-Enhanced di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Non perderti [](quality-of-experience-review-guide.md) l'articolo Gestire la qualità delle chiamate e delle riunioni, che offre indicazioni approfondite per l'amministratore o il tecnico del supporto tecnico di Teams responsabile della gestione della qualità del servizio in Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versione precedente di CQD (CQD.lync.com)

La versione corrente di CQD ( https://CQD.Teams.microsoft.com) sostituisce la versione precedente di CQD ( https://CQD.lync.com) . Puoi comunque usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for Business), ma a partire dal 1° luglio 2020, usa i dati di CQD. Teams.microsoft.com. A breve l'accesso a CQD.lync.com verrà disattivato, quindi è consigliabile passare a CQD. Teams.microsoft.com se non è già stato fatto.

> [!IMPORTANT]
> A partire dal 1° luglio 2020, non è più possibile visualizzare o modificare i dati dell'edificio o della query dal vecchio CQD (CQD.lync.com). Se non è ancora stata eseguita la migrazione di questi dati da CQD.lync.com e se ne ha ancora bisogno, registrare un ticket di supporto.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati CQD

Novità di gennaio 2020: [Scaricare i modelli di query di Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati CQD.

Leggere [Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md) per altre informazioni.



## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Configurare call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione dei flussi in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)


[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)