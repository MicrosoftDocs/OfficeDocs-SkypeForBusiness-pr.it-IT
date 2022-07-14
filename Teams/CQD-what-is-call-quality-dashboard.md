---
title: Che cos'è Call Quality Dashboard (CQD)?
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su Call Quality Dashboard (CQD) e su come usarlo per visualizzare i report sulla qualità delle riunioni e delle chiamate in Microsoft Teams.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790071"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Che cos'è Call Quality Dashboard (CQD)?

Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) mostra la qualità delle chiamate e delle riunioni, a **livello di organizzazione**, per Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

  
L'ultima versione di Call Quality Dashboard include un [feed di dati quasi in tempo reale,](CQD-data-and-reports.md) il che significa che i record delle chiamate sono disponibili in Call Quality Dashboard entro 30 minuti dalla fine di una chiamata.

Ogni volta che call quality dashboard include [dati identificativi dell'utente finale (EUII),](CQD-data-and-reports.md#euii-data) questi vengono gestiti allo stesso modo [dell'EUII in microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

Call Quality Dashboard è progettato per aiutare gli amministratori di Teams, gli amministratori Skype for Business e i tecnici di rete a monitorare la qualità delle chiamate e delle riunioni a livello di organizzazione. Userai Call Quality Dashboard per **ottimizzare la rete** per migliorare la qualità delle prestazioni. Quando è necessario esaminare le informazioni relative a chiamate e riunioni per un **utente specifico**, usare Call Quality Dashboard insieme all'analisi [delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md) per utente.

Ad esempio, usando Call Quality Dashboard, è possibile determinare che la scarsa qualità delle chiamate di un utente (osservata con l'analisi delle chiamate per utente) è dovuta a un problema di rete che interessa anche molti altri utenti. Call Quality Dashboard acquisisce sia l'esperienza di chiamata individuale che la qualità complessiva delle chiamate effettuate con Teams o Skype for Business. Con CQD, possono emergere modelli generali, in modo che gli ingegneri di rete possano effettuare valutazioni informate della qualità delle chiamate. Call Quality Dashboard fornisce report delle metriche di qualità delle chiamate che forniscono informazioni sulla qualità complessiva delle chiamate, sui flussi server-client, sui flussi client-client e [sul contratto](https://go.microsoft.com/fwlink/p/?linkid=846252) di servizio sulla qualità vocale. 
  
![Screenshot di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

In Call Quality Dashboard è consigliabile caricare informazioni sull'edificio e sull'endpoint, che consentono di usare i report di Location-Enhanced per analizzare la qualità e l'affidabilità delle chiamate all'interno dell'edificio di un utente. I dati possono essere valutati per determinare se il problema è isolato per un singolo utente o influisce su un segmento di utenti più ampio. Per abilitare la creazione o la visualizzazione specifica dell'endpoint in Call Quality Dashboard, un amministratore deve [caricare le informazioni sull'edificio o sull'endpoint](CQD-upload-tenant-building-data.md) nella pagina **Caricamento dati tenant** CQD.

![Screenshot dei report di Location-Enhanced di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Non perderti l'articolo [Sulla qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md) , che offre indicazioni approfondite per l'amministratore di Teams o il tecnico del supporto responsabile della gestione della qualità del servizio in Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Usare Power BI per analizzare i dati di Call Quality Dashboard

Novità di gennaio 2020: [Scaricare i modelli di query di Power BI per Call Quality Dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality Dashboard.

Per altre informazioni, vedere [Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md) .



## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati di tenant e building](CQD-upload-tenant-building-data.md)

[Call Quality Dashboard - Dati e report](CQD-data-and-reports.md)

[Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)


[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
