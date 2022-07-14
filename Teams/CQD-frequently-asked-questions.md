---
title: Call Quality Dashboard (CQD) Domande frequenti
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Leggi le domande frequenti e le risposte su Call Quality Dashboard (CQD) di Microsoft Teams.
ms.openlocfilehash: 862967138321b1855f2fdc5b0c8b6ce6caca887f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789391"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Call Quality Dashboard (CQD) Domande frequenti

## <a name="frequently-asked-questions"></a>Domande frequenti

[Perché Call Quality Dashboard contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno avuto un'esperienza scadente?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Perché vedo fino allo 0,2% di differenza nei valori di chiamata e conteggio utenti sulle misure e come ottenere volumi più accurati? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Perché non è possibile visualizzare EUII in CQD?](#why-cant-i-see-euii-in-cqd)

[Sto provando a usare Call Quality Dashboard per i report sul tipo di utilizzo e trovo che alcuni dei dati sono incompleti. Perché?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Perché vengono visualizzate Skype for Business informazioni in Call Quality Dashboard quando si filtra solo per Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Perché i report personalizzati restituiscono un massimo di 10.000 righe solo quando è necessario aggiungere più voci?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Perché Wi-Fi connessioni VPN vengono visualizzate come cablate anziché come Wi-Fi?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Ho attivato la registrazione basata sui criteri in Teams e ora le chiamate peer-to-peer vengono contrassegnate come Conferenze: cosa è successo?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Perché Call Quality Dashboard contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno avuto un'esperienza scadente?

Vedere le regole utilizzate da Call Quality Dashboard per la [classificazione dei flussi](stream-classification-in-call-quality-dashboard.md).
 
Per i flussi audio, uno qualsiasi dei cinque classificatori (calcolati per la media in base alla lunghezza della chiamata) potrebbe essere tutti all'interno di parametri "buoni". Ciò non significa che gli utenti non abbiano avuto problemi con l'uscita audio, statica o glitch. 

Per determinare se si è verificato un problema di rete, esaminare il delta tra i valori medi per la sessione e i valori max. I valori massimi sono il valore massimo rilevato e riportato durante la sessione.
 
Ecco un esempio di come risolvere questo problema. Si supponga di eseguire una traccia di rete durante una chiamata e che i primi 20 minuti non ci siano pacchetti persi, ma che si abbia uno spazio di 1,5 secondi di pacchetti e quindi un valore valido per il resto della chiamata. La media sarà <perdita di pacchetti del 10% (0,1) anche in un'analisi RTP di traccia Wireshark. Qual è stata la perdita massima dei pacchetti? 1,5 secondi in un periodo di 5 secondi sarebbero 30% (0,3). Ciò si è verificato nel periodo di campionamento di 5 secondi (forse o potrebbe essere suddiviso nel periodo di campionamento)?
 
Se le metriche di rete hanno un aspetto corretto nelle medie e nei valori massimi, cerca altri dati di telemetria: 
- Controlla il rapporto di evento insufficiente della CPU per vedere se le risorse CPU rilevate erano insufficienti e causavano la scarsa qualità. 
- Il dispositivo audio era in modalità Half Duplex per impedire il feedback a causa di microfoni troppo vicini agli altoparlanti? 
- Controlla il Device Half Duplex AEC Event Ratio. Glitch da un dispositivo, ad esempio un microfono, l'introduzione di rumore o statici a causa di rilasci audio USB quando sono collegati a un hub o a un alloggiamento di espansione?  
- Controlla i rapporti degli eventi glitch del dispositivo e del microfono. Il dispositivo funzionava correttamente?  
- Controlla i rapporti di evento del dispositivo di acquisizione e rendering non funzionanti.


Per ulteriori informazioni sulle dimensioni e le misure disponibili nella telemetria CQD, leggi [Dimensioni e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

Per il rumore di sottofondo, controlla il rapporto tra gli eventi per vedere la durata dell'audio dei partecipanti.
 
Creare report dettagliati in Call Quality Dashboard e filtrare in base all'ID riunione per esaminare tutti gli utenti e i flussi di una riunione e aggiungere i campi a cui si è interessati. Un utente che segnala il problema potrebbe non essere quello che lo stava riscontrando. Stanno solo segnalando l'esperienza.
 
La telemetria non segnala necessariamente il problema, ma consente di capire meglio dove cercare e informare le decisioni. Si tratta di aggiornamenti della rete, del dispositivo, del driver o del firmware, dell'utilizzo o dell'utente?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Perché vedo fino allo 0,2% di differenza nei valori di chiamata e conteggio utenti sulle misure e come ottenere volumi più accurati? 

Per calcolare il numero di chiamate e le misure di conteggio utenti, viene eseguita un'operazione distinct countif sulla chiamata o gli identificatori utente nel set di dati. Nei set di dati di grandi dimensioni si verifica un errore fino allo 0,2% intrinseco all'operazione countif distinta. Per un volume più preciso, è consigliabile usare le misure per il conteggio dei flussi, in quanto non si basano su questa operazione countif distinta. L'applicazione di filtri per ridurre il volume di dati può ridurre l'errore, ma potrebbe non eliminare questa origine di errore nei conteggi distinti di chiamate e utenti. Fare riferimento a [Dimensioni e misure disponibili nel Dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md) per le quali sono interessate le misure.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Perché non è possibile visualizzare EUII in CQD?

Questi ruoli di amministratore possono accedere a Call Quality Dashboard, ma non possono visualizzare euii (informazioni identificabili per l'utente finale):

- Lettore di report di Microsoft 365
- Specialista del supporto tecnico per le comunicazioni di Teams

Per altre informazioni sui ruoli che possono accedere a Call Quality Dashboard, incluso EUII, vedere [Assegnare ruoli per l'accesso a Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Sto provando a usare Call Quality Dashboard per i report sul tipo di utilizzo e trovo che alcuni dei dati sono incompleti. Perché?

Gli strumenti di gestione della qualità delle chiamate, come Call Analytics, CallRecord API Graph e Analisi in tempo reale, si basano sulla telemetria diagnostica. Le informazioni visualizzate negli strumenti di gestione della qualità delle chiamate di Teams sono complete solo quanto i dati di telemetria ricevuti dai clienti che partecipano a una chiamata. Esistono diversi motivi per cui potrebbe non ricevere la telemetria completa, ad esempio interruzioni di rete o [configurazioni non corrette del firewall o del proxy](/microsoft-365/enterprise/urls-and-ip-address-ranges). Stiamo continuando a lavorare per migliorare l'affidabilità e la resilienza con cui i client di Teams forniscono telemetria al servizio.

Tenendo presente questo aspetto, non supportiamo l'uso di strumenti di gestione della qualità delle chiamate per la creazione di report sull'utilizzo. Non sono progettati per supportare né sono destinati a questi tipi di scenari di creazione di report e molte statistiche di utilizzo non lo sono e non saranno disponibili all'interno di questi strumenti. Teams Amministrazione Center offre una serie di [report sull'utilizzo](teams-analytics-and-reports/teams-reporting-reference.md) e un [report presenze alle riunioni](teams-analytics-and-reports/meeting-attendance-report.md) è disponibile direttamente dal client teams.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Perché vengono visualizzate Skype for Business informazioni in Call Quality Dashboard quando si filtra solo per Teams?

Quando si filtra per Teams solo nei report di Call Quality Dashboard (isTeams = 1), si filtrano per tutte le chiamate in cui il *primo endpoint* è Teams. Se il *secondo endpoint* è Skype for Business, tali informazioni verranno visualizzate nel report di Call Quality Dashboard. A seconda degli scenari dei clienti, Call Quality Dashboard può includere chiamate Skype for Business Server 2019 quando è configurato [Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector). Possono anche includere chiamate Bot Skype (AA, CVI, VDI), eventi live e chiamate PSTN.

È possibile rimuovere Skype for Business informazioni dalle query filtrando in base a dimensioni come *First User Agent Category* e *Second User Agent Category*. È anche possibile usare *la coppia di categorie agente utente* , che combina le dimensioni Primo e Secondo in un singolo filtro.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Perché i report personalizzati restituiscono un massimo di 10.000 righe solo quando è necessario aggiungere più voci?

Call Quality Dashboard è progettato per le query di dati riepilogate e non è progettato per l'esportazione dei dati. Se possibile, è consigliabile ristrutturarle per evitare il superamento del limite di 10.000 righe. Per iniziare, esaminare gli indicatori KPI usando dimensioni più ampie e con una cardinalità inferiore, ad esempio Mese, Anno, Data, Area geografica, Paese e così via. Da qui è possibile eseguire il drill-down per visualizzare dimensioni di cardinalità sempre più elevate. Il supporto tecnico e i report di Location-Enhanced offrono entrambi esempi validi di questo flusso di lavoro di drill-down.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Perché Wi-Fi connessioni VPN vengono visualizzate come cablate anziché come Wi-Fi?

Si tratta di un comportamento previsto. Il fornitore di VPN ha creato una scheda Ethernet virtuale che viene trattata come una connessione cablata. Poiché non è etichettato correttamente, il sistema operativo non sa che si tratta di una connessione Wi-Fi e la segnala come cablata.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Ho attivato la registrazione basata sui criteri in Teams e ora le chiamate peer-to-peer vengono contrassegnate come Conferenze: cosa è successo?

Si tratta di un comportamento previsto quando è abilitata la registrazione basata su criteri in Microsoft Teams. La registrazione basata su criteri usa un bot registratore di Teams distribuito in Microsoft Azure per acquisire i contenuti delle riunioni ai fini della conformità. Nella gestione della qualità delle chiamate, "peer-to-peer" è una descrizione del flusso del traffico multimediale, non dell'interazione tra gli utenti. Poiché un bot registratore è a sua volta parte della chiamata, la chiamata non è più peer-to-peer, ma una chiamata a più parti. Le chiamate multi-party vengono classificate come conferenze da Microsoft Teams, quindi verranno indicate come tali quando si visualizzano queste chiamate in Call Quality Dashboard e in altri strumenti per la qualità delle chiamate.

## <a name="related-articles"></a>Articoli correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati di tenant e building](CQD-upload-tenant-building-data.md)

[Call Quality Dashboard - Dati e report](CQD-data-and-reports.md)

[Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
