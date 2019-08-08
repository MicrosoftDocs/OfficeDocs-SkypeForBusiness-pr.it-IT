---
title: Analisi delle chiamate e Dashboard Qualità della chiamata
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Informazioni su Call Analytics e Call Quality dashboard e su come usarli per monitorare e risolvere i problemi di qualità delle chiamate.
ms.openlocfilehash: 1130e901ca8c7103c9dd73990c4c0af47898203d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237518"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Analisi delle chiamate e Dashboard Qualità della chiamata

Microsoft teams e Skype for business offrono due modi per monitorare e risolvere i problemi di qualità delle chiamate: analisi delle chiamate e Call Quality Dashboard (Call Quality Dashboard). Questo articolo li descrive entrambi e indica quando usare l'uno o l'altro.

Call Analytics e CQD funzionano parallelamente l'uno all'altro e possono essere usati come programmi indipendenti oppure insieme. Ad esempio, supponiamo che uno specialista del supporto delle comunicazioni determini che hanno bisogno di ulteriore assistenza per risolvere un problema di chiamata. Lo specialista del supporto delle comunicazioni passa la chiamata a un tecnico del supporto delle comunicazioni, che ha accesso ad altre informazioni in Call Analytics rispetto allo specialista del supporto per le comunicazioni. A sua volta, l'ingegnere del supporto delle comunicazioni può avvisare un ingegnere di rete di un problema. Il Network Engineer può verificare Call Quality dashboard per vedere se un problema complessivo relativo al sito potrebbe essere una causa che contribuisce a risolvere i problemi di chiamata.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Che cos'è Call Analytics e quando è consigliabile usarlo?

**L'analisi delle chiamate è ora disponibile nell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com).** Per visualizzare tutte le informazioni sulle chiamate e i dati per un utente, usare la scheda **cronologia chiamate** . A questo scopo, è possibile cercare l'utente dal dashboard nella pagina del profilo dell'utente o trovare l'utente dagli **utenti** nella barra di spostamento sinistra.

Chiamata analitica Mostra informazioni dettagliate sui dispositivi, le reti e la connettività correlati alle chiamate e alle riunioni specifiche per ogni utente in un account Microsoft teams o Skype for business. Perché l'utente ha una chiamata scadente questo pomeriggio? Usando l'analisi delle chiamate, un amministratore di Office 365 o un agente addestrato dell'helpdesk può analizzare il dispositivo, la rete, la connettività e altri fattori correlati alla chiamata per risolvere i problemi di qualità delle chiamate e di connessione in Microsoft teams e Skype for business.

Per visualizzare queste informazioni per un utente nell'interfaccia di amministrazione di Microsoft teams, fare clic sulla scheda **cronologia chiamate** per l'utente nella pagina dei dettagli dell'utente, mostrando tutte le chiamate e le riunioni a cui l'utente ha partecipato per gli ultimi 30 giorni.

![Screenshot di tutti i dati utente di analisi.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Per ottenere altre informazioni su una determinata sessione, incluse le statistiche dettagliate su media e networking, fare clic su una sessione per visualizzare i dettagli.

![Screenshot dei dati della sessione utente di analisi delle chiamate.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Se si vuole che gli utenti non amministratori, ad esempio gli agenti dell'helpdesk di un fornitore esterno, usino l'analisi delle chiamate, è possibile assegnare le autorizzazioni in modo che possano usare le analisi delle chiamate, ma non possono accedere al resto dell'interfaccia di amministrazione di Microsoft teams: 
  
- Gli **agenti dell'helpdesk con le comunicazioni supportano le autorizzazioni specialistiche**: gli agenti vedono un insieme limitato di dati e informazioni personali in Call Analytics. Possono risolvere i problemi relativi alle chiamate, ma le riunioni vengono risolti con un tecnico del supporto delle comunicazioni.
    
- **Agenti dell'helpdesk con autorizzazioni di supporto tecnico comunicazioni**: gli agenti visualizzano tutti i dati disponibili in Call Analytics e risolvono le chiamate e le riunioni. hanno accesso completo ai registri chiamate e alle informazioni del cliente.

> [!NOTE]
> Il ruolo di supporto delle comunicazioni è equivalente al ruolo di assistenza di livello 1 del portale di anteprima e il ruolo di supporto tecnico comunicazioni è equivalente al ruolo di supporto di Tier 2 dal portale di anteprima.

Per altre informazioni sui ruoli di supporto tecnico per le comunicazioni e per le comunicazioni, vedere [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md).

> [!IMPORTANT]
> Le autorizzazioni dell'agente helpdesk e il caricamento della topologia di rete sono disponibili nell'interfaccia di amministrazione di Microsoft teams. Gli specialisti del supporto delle comunicazioni e i tecnici del supporto delle comunicazioni possono usare questo portale per accedere a analisi delle chiamate e al dashboard qualità chiamata.
    
Per i dettagli sull'installazione di Call Analytics, vedi [Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md). Per altre informazioni su come gli agenti dell'helpdesk possono collaborare con le analisi delle chiamate, vedere [usare l'analisi delle chiamate per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Che cos'è Call Quality Dashboard e quando è consigliabile usarlo?
  
Mentre l'analisi delle chiamate è progettata per aiutare gli amministratori e gli agenti dell'helpdesk a risolvere i problemi di qualità delle chiamate, il dashboard qualità chiamata (Call Quality Dashboard) è progettato per aiutare gli amministratori del team, gli amministratori di Skype for business e gli ingegneri di rete a ottimizzare la rete. Call Quality dashboard sposta lo stato attiva da utenti specifici e analizza invece le informazioni aggregate per un intero team o per l'organizzazione di Skype for business. Per altre informazioni, Vedi [caratteristiche del dashboard qualità chiamata per Teams e Skype for business online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Forse la qualità di chiamata scadente dell'utente è dovuta a un problema di rete che interessa anche molti altri utenti. L'esperienza di chiamata individuale non è visibile in Call Quality dashboard, ma viene acquisita la qualità complessiva delle chiamate effettuate con Microsoft teams o Skype for business. Con CQD possono emergere degli schemi generali, che permettono ai tecnici di rete di fare una valutazione informata sulla qualità delle chiamate. Call Quality dashboard fornisce report sulle metriche di qualità delle chiamate che consentono di approfondire la qualità complessiva delle chiamate, i flussi client-server, i flussi client-client e la qualità della voce [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Screenshot del dashboard qualità chiamata.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Con l'aiuto dei report basati sulla posizione di Call Quality dashboard, è possibile valutare la qualità e l'affidabilità delle chiamate all'interno della struttura dell'utente per determinare se il problema è isolato da un singolo utente o influisce su un segmento più grande di utenti.

![Screenshot dei report di posizione avanzata di Call Quality dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> Per abilitare visualizzazioni specifiche di un edificio o di un endpoint in Call Quality dashboard, un amministratore deve [caricare le informazioni sulla compilazione o sull'endpoint](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) nella pagina di caricamento dei dati del tenant di Call Quality dashboard. 

Se si vuole che gli utenti non amministratori, ad esempio gli agenti dell'helpdesk, usino il dashboard qualità chiamata, è possibile assegnare a tale utente il ruolo di **supporto tecnico comunicazioni team**, **specialista supporto comunicazioni team**o **lettore report** . Gli utenti con i ruoli seguenti possono accedere a dashboard qualità chiamata:

- Amministratore globale
- Lettore globale
- Amministratore di Skype for business
- Amministratore del servizio Teams
- Amministratore delle comunicazioni di Teams
- Ingegnere di supporto per Communications Teams
- Specialista supporto comunicazioni Teams
- Lettore di report

> [!NOTE]
> Le comunicazioni di teams Engineer, specialista del supporto delle comunicazioni di teams e i ruoli del lettore di report non possono modificare i file nella pagina di caricamento dei dati del tenant di Call Quality dashboard né attivare Call Quality dashboard per un tenant.

Per altre informazioni su questi ruoli, vedere [informazioni sui ruoli di amministratore di Office 365](/office365/admin/add-users/about-admin-roles).

Per altre informazioni su Call Quality dashboard, vedere [attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online](turning-on-and-using-call-quality-dashboard.md) e [dimensioni e misure disponibili in Call Quality dashboard per Microsoft teams e Skype for business online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Video: panoramica sulla qualità delle chiamate](https://aka.ms/teams-quality)

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online](turning-on-and-using-call-quality-dashboard.md)
