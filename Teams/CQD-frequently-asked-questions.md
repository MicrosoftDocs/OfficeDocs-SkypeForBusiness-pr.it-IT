---
title: Domande frequenti su Call Quality Dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Leggere le domande frequenti e le risposte su Microsoft Teams Call Quality Dashboard (CQD).
ms.openlocfilehash: 3b527b32e194b531be5003c5f8b180a00976cf8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111532"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Domande frequenti su Call Quality Dashboard (CQD)

## <a name="frequently-asked-questions"></a>Domande frequenti

[Perché CQD contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno un'esperienza scarsa?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Perché viene visualizzata una differenza fino a 0,2% nei valori relativi al conteggio delle chiamate e degli utenti sulle misure e su come ottenere volumi più accurati? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Perché i dati CQD di Skype for Business sono diversi dai dati CQD di Teams? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Perché non è possibile visualizzare EUII in CQD?](#why-cant-i-see-euii-in-cqd)

[Perché le informazioni di Skype for Business vengono visualizzate in CQD quando sono filtrate solo per Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Perché i report personalizzati restituiscono un massimo di 10.000 righe quando si sa che dovrebbero essere presenti altre voci?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Perché CQD contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno un'esperienza scarsa?

Vedere le regole utilizzate da CQD per la [classificazione dei flussi.](stream-classification-in-call-quality-dashboard.md)
 
Per i flussi audio, uno qualsiasi dei 5 classificatori, che vengono calcolati per la media in base alla lunghezza della chiamata, potrebbe essere compreso nei parametri "buoni". Non significa che gli utenti non hanno esperienza di qualcosa che ha contribuito a un'uscita audio, statica o glitch. 

Per determinare se si è verificato un problema di rete, esaminare il delta tra i valori medi per la sessione e i valori massimi. I valori massimi sono i valori massimi rilevati e riportati durante la sessione.
 
Ecco un esempio di come risolvere questa situazione. Supponiamo di prendere una traccia di rete durante una chiamata e che nei primi 20 minuti non ci siano pacchetti persi, ma poi si ha una distanza di 1,5 secondi di pacchetti e quindi buona per il resto della chiamata. La media sarà <10% (0,1) Perdita di pacchetti anche in un'analisi RTP di Wireshark Trace. Qual è stata la perdita massima di pacchetti? 1,5 secondi in un periodo di 5 secondi sarebbe del 30% (0,3). Si è verificata entro i cinque secondi periodi di campionamento (forse o potrebbe essere suddivisa nel periodo di campionamento)?
 
Se le metriche di rete hanno un aspetto positivo nelle medie e nei valori massimi, esaminare altri dati di telemetria: 
- Controllare il rapporto di eventi CPU insufficienti per verificare se le risorse della CPU rilevate disponibili erano insufficienti e hanno causato una qualità scarsa. 
- Il dispositivo audio era in modalità Half Duplex per impedire il feedback dovuto ai microfoni che si avvicinano agli altoparlanti? 
- Controllare il rapporto di eventi AEC Half Duplex del dispositivo. L'anomalia del dispositivo o il glitch del microfono hanno introdotto rumore o stato statico a causa di un'uscita audio USB quando è collegata a un hub o a un'docking station:  
- Controllare le proporzioni degli eventi Glitch del dispositivo e Del microfono. Il dispositivo funzionava correttamente?  
- Controllare le proporzioni degli eventi di acquisizione e rendering del dispositivo non funzionante.


Per altre informazioni sulle dimensioni e le misure disponibili nella telemetria di CQD, vedere Dimensioni [e misure disponibili in Call Quality Dashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Per i rumori di fondo, controllare il rapporto degli eventi di disattivazione dell'audio per vedere per quanto tempo i partecipanti sono stati disattivati.
 
Creare report dettagliati in CQD e filtrare in base all'ID riunione per esaminare tutti gli utenti e i flussi in una riunione e aggiungere i campi a cui si è interessati. Un utente che segnala il problema potrebbe non essere quello che ha avuto il problema. Stanno solo segnalando l'esperienza.
 
La telemetria non chiama necessariamente il problema, ma può aiutare a capire meglio dove cercare e informare le decisioni. Si tratta di aggiornamenti di rete, dispositivo, driver o firmware, utilizzo o utente?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Perché viene visualizzata una differenza fino a 0,2% nei valori relativi al conteggio delle chiamate e degli utenti sulle misure e su come ottenere volumi più accurati? 
Per calcolare il conteggio delle chiamate e le misure di conteggio degli utenti, viene eseguita un'operazione countif distinta rispetto alla chiamata o agli identificatori utente nel set di dati. Nei set di dati di grandi dimensioni si verifica un errore fino a 0,2% inerente all'operazione countif distinta. Per ottenere il volume più accurato, è consigliabile affidarsi alle misure di conteggio dei flussi perché non si basano su questa operazione countif distinta. L'applicazione di filtri per ridurre il volume di dati può ridurre l'errore, ma non eliminare questa fonte di errore in chiamate distinte e conteggi degli utenti. Vedere Dimensioni [e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) per le misure in cui sono state influenzate le misure.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Perché i dati CQD di Skype for Business sono diversi dai dati CQD di Teams? 


> [!IMPORTANT]
> A partire dal 1° luglio 2020, il CQD (CQD.lync.com) precedente usa i dati dell'ultimo CQD (CQD). Teams.microsoft.com). I dati CQD meno recenti non sono più disponibili e non è possibile esportare i dati dell'edificio o del report. Puoi comunque usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for Business), ma presto dissegni l'accesso a CQD.lync.com, quindi dovresti passare a CQD. Teams.microsoft.com se non è già stato fatto.


Se stai provando a confrontare i dati tra il CQD precedente del portale legacy di Skype for Business (cqd.lync.com) e l'ultimo CQD dell'interfaccia di amministrazione di Teams (cqd.teams.microsoft.com), noterai rapidamente che i dati non corrispondono. Questo perché i report CQD più recenti su molti scenari di chiamata aggiuntivi. Se si usano ancora report dal CQD precedente, usare questo articolo per interpretare questi report: [Call Quality Dashboard per Skype for Business Server.](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Perché non è possibile visualizzare EUII in CQD?

Questi ruoli di amministratore possono accedere a CQD, ma non possono visualizzare EUII (informazioni identificabili dall'utente finale):
- Lettore report di Microsoft 365
- Specialista del supporto tecnico di Teams Communications

Per altre informazioni sui ruoli che possono accedere a CQD, incluso EUII, vedere Assegnare ruoli per l'accesso a [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Perché le informazioni di Skype for Business vengono visualizzate in CQD quando sono filtrate solo per Teams?

Quando si filtra teams solo nei report CQD (isTeams = 1), si filtrano tutte le chiamate in cui il primo *endpoint* è Teams. Se il *secondo endpoint* è Skype for Business, queste informazioni verranno visualizzate nel report CQD.

CQDv2 e CQDv3 avranno sempre conteggi totali diversi, perché CQDv3 avrà nuovi scenari che CQDv2 non avrà. Ecco perché il confronto dei numeri totali di riepilogo o aggregati senza filtri avrà queste differenze previste.  

A seconda dello scenario dei clienti, CQDv3 includerà le chiamate locali SFB 2019 (se SFB 2019 viene usato con un connettore dati), chiamate Skype Bot (AA, CVI, VDI), eventi live e chiamate PSTN. Scenari/funzionalità disponibili per i clienti, ma i relativi dati non sono in CQD V2.

Ad esempio, è previsto che i clienti e gli utenti vedano 200.000 flussi audio, con 5.000 errori nel report di riepilogo CQD V2; rispetto a 300.000 flussi audio con 5500 errori (provenienti da chiamate in locale 2019, chiamate CVI, chiamate PSTN e così via) in CQD V3.

Per determinare se sono presenti differenze impreviste, è necessario esaminare varie suddivisioni dei dati complessivi.  Confrontare con intento.  L'affondo dei dati in base alla coppia di categorie agente utente è uno dei primi elementi consigliati.  *First Product* e *Second Product* sono anche buoni filtri dei dati.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Perché i report personalizzati restituiscono un massimo di 10.000 righe quando si sa che dovrebbero essere presenti altre voci?

CQD è progettato per le query di dati riepilogate e non è progettato per l'esportazione dei dati. Se possibile, è consigliabile ristrutturare i report per evitare che venga superato il limite di 10.000 righe. Iniziare esaminando gli indicatori KPI usando dimensioni di cardinalità più ampie e inferiori, ad esempio Mese, Anno, Data, Area geografica, Paese e così via. Da qui è possibile eseguire il drill-down in dimensioni di cardinalità sempre più elevate. L'Helpdesk e i Location-Enhanced report forniscono entrambi esempi di questo flusso di lavoro di drill-down.

## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione dei flussi in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)