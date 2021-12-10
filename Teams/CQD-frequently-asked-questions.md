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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Leggere le domande frequenti (FAQ) e le risposte su Microsoft Teams Call Quality Dashboard (CQD).
ms.openlocfilehash: 81c6478147e0959ca97b67ee0f01632478c0eb38
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401900"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Domande frequenti su Call Quality Dashboard (CQD)

## <a name="frequently-asked-questions"></a>Domande frequenti

[Perché CQD contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno un'esperienza scarsa?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Perché viene visualizzata una differenza fino a 0,2% nei valori di chiamata e di conteggio degli utenti per le misure e come ottenere volumi più accurati? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Perché non è possibile visualizzare EUII in CQD?](#why-cant-i-see-euii-in-cqd)

[Sto provando a usare CQD per i report di tipo utilizzo e trovo che alcuni dati sono incompleti, perché?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Perché le informazioni Skype for Business vengono visualizzate in CQD quando si filtrano solo Teams dati?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Perché i report personalizzati restituiscono un massimo di 10.000 righe quando si sa che dovrebbero essere presenti altre voci?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Perché le Wi-Fi VPN vengono mostrate come Cablate anziché Wi-Fi?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Ho attivato registrazione basata su criteri in Teams e ora le chiamate peer-to-peer vengono contrassegnate come conferenze: cosa è successo?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Perché CQD contrassegna una chiamata come "Buona" se uno o più partecipanti alla riunione hanno un'esperienza scarsa?

Vedere le regole utilizzate da CQD per la [classificazione dei flussi.](stream-classification-in-call-quality-dashboard.md)
 
Per i flussi audio, uno dei cinque classificatori, calcolati per la media in base alla lunghezza della chiamata, potrebbe essere compreso tra i parametri "buoni". Non significa che gli utenti non hanno esperienza di qualcosa che ha contribuito a un'uscita audio, statica o glitch. 

Per determinare se si è verificato un problema di rete, esaminare il delta tra i valori medi per la sessione e i valori massimi. I valori massimi sono i valori massimi rilevati e riportati durante la sessione.
 
Ecco un esempio di come risolvere questa situazione. Supponiamo di prendere una traccia di rete durante una chiamata e che nei primi 20 minuti non ci siano pacchetti persi, ma poi si ha una distanza di 1,5 secondi di pacchetti e quindi buona per il resto della chiamata. La media sarà <10% (0,1) Perdita di pacchetti anche in un'analisi RTP di Wireshark Trace. Qual è stata la perdita massima di pacchetti? 1,5 secondi in un periodo di 5 secondi sarebbe il 30% (0,3). Si è verificata entro il periodo di campionamento di 5 secondi (forse o potrebbe essere suddiviso nel periodo di campionamento)?
 
Se le metriche di rete hanno un aspetto positivo nelle medie e nei valori massimi, esaminare altri dati di telemetria: 
- Controllare il rapporto di eventi CPU insufficienti per verificare se le risorse della CPU rilevate disponibili erano insufficienti e hanno causato una qualità scarsa. 
- Il dispositivo audio era in modalità Half Duplex per impedire il feedback a causa di microfoni troppo vicini agli altoparlanti? 
- Controllare il rapporto di eventi AEC Half Duplex del dispositivo. Il problema del dispositivo o del glitch del microfono ha introdotto rumore o stato statico a causa di un'uscita audio USB quando è collegata a un hub o a un'docking station?  
- Controllare le proporzioni degli eventi Glitch del dispositivo e Del microfono. Il dispositivo funzionava correttamente?  
- Controllare le proporzioni degli eventi di acquisizione e rendering del dispositivo non funzionante.


Per altre informazioni sulle dimensioni e le misure disponibili nella telemetria di CQD, vedere Dimensioni [e misure disponibili in Call Quality Dashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Per i rumori di fondo, controllare il rapporto degli eventi di disattivazione dell'audio per vedere per quanto tempo i partecipanti sono stati disattivati.
 
Creare report dettagliati in CQD e filtrare in base all'ID riunione per esaminare tutti gli utenti e i flussi in una riunione e aggiungere i campi a cui si è interessati. Un utente che segnala il problema potrebbe non essere quello che ha avuto il problema. Stanno solo segnalando l'esperienza.
 
La telemetria non chiama necessariamente il problema, ma può aiutare a capire meglio dove cercare e informare le decisioni. Si tratta di aggiornamenti di rete, dispositivo, driver o firmware, utilizzo o utente?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Perché viene visualizzata una differenza fino a 0,2% nei valori di chiamata e di conteggio degli utenti per le misure e come ottenere volumi più accurati? 

Per calcolare il conteggio delle chiamate e le misure di conteggio degli utenti, viene eseguita un'operazione countif distinta rispetto alla chiamata o agli identificatori utente nel set di dati. Nei set di dati di grandi dimensioni si verifica un errore fino a 0,2% inerente all'operazione countif distinta. Per ottenere il volume più accurato, è consigliabile affidarsi alle misure di conteggio dei flussi perché non si basano su questa operazione countif distinta. L'applicazione di filtri per ridurre il volume di dati può ridurre l'errore, ma non eliminare questa fonte di errore in chiamate distinte e conteggi degli utenti. Vedere Dimensioni [e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) per le misure interessate.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Perché non è possibile visualizzare EUII in CQD?

Questi ruoli di amministratore possono accedere a CQD, ma non possono visualizzare EUII (informazioni identificabili dall'utente finale):

- lettore Microsoft 365 report
- Teams Communications Support Specialist

Per altre informazioni sui ruoli che possono accedere a CQD, incluso EUII, vedere Assegnare ruoli per l'accesso a [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Sto provando a usare CQD per i report di tipo utilizzo e trovo che alcuni dati sono incompleti, perché?

Gli strumenti di gestione della qualità delle chiamate come CQD, Call Analytics, CallRecord Graph API e Real-time Analytics si basano sulla telemetria diagnostica. Le informazioni che mostriamo negli Teams di gestione della qualità delle chiamate sono complete solo quanto i dati di telemetria ricevuti dai clienti che partecipano a una chiamata. Esistono diversi motivi per cui microsoft potrebbe non ricevere telemetria completa, ad esempio interruzioni di rete o errori di configurazione del firewall o [del proxy.](/microsoft-365/enterprise/urls-and-ip-address-ranges.md) Stiamo continuando a lavorare per migliorare l'affidabilità e la resilienza con cui i Teams client forniscono telemetria al servizio.

In questo caso, è consigliabile non affidarsi agli strumenti di gestione della qualità delle chiamate per la creazione di report sull'utilizzo. Teams'interfaccia di amministrazione offre [](teams-analytics-and-reports/teams-reporting-reference.md)una serie di report sull'utilizzo e un [report](teams-analytics-and-reports/meeting-attendance-report.md) sulla partecipazione alle riunioni è disponibile direttamente dal client Teams riunione.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Perché le informazioni Skype for Business vengono visualizzate in CQD quando si filtrano solo Teams dati?

Quando si filtrano Teams solo nei report CQD (isTeams = 1), si filtrano tutte le chiamate in cui il primo *endpoint* è Teams. Se il *secondo endpoint* è Skype for Business, queste informazioni verranno visualizzate nel report CQD. A seconda degli scenari dei clienti, CQD può includere Skype for Business Server 2019 quando [call data connector](/skypeforbusiness/hybrid/plan-call-data-connector.md) è configurato. Può anche includere Skype bot (AA, CVI, VDI), eventi live e chiamate PSTN.

È possibile rimuovere le informazioni Skype for Business dalle query filtrando in  base a dimensioni come La categoria Agente primo utente e *Seconda categoria agente utente.* È anche possibile usare *la coppia di* categorie agente utente che combina le dimensioni Primo e Secondo in un unico filtro.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Perché i report personalizzati restituiscono un massimo di 10.000 righe quando si sa che dovrebbero essere presenti altre voci?

CQD è progettato per le query di dati riepilogate e non è progettato per l'esportazione dei dati. Se possibile, è consigliabile ristrutturare i report per evitare che venga superato il limite di 10.000 righe. Iniziare esaminando gli indicatori KPI usando dimensioni di cardinalità più ampie e inferiori, ad esempio Mese, Anno, Data, Area geografica, Paese e così via. Da qui è possibile eseguire il drill-down in dimensioni di cardinalità sempre più elevate. L'Helpdesk e i Location-Enhanced report forniscono entrambi esempi di questo flusso di lavoro di drill-down.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Perché le Wi-Fi VPN vengono mostrate come Cablate anziché Wi-Fi?

Si tratta di un comportamento previsto. Il fornitore vpn ha creato un adattatore ethernet virtuale trattato come una connessione cablata. Poiché l'etichetta non è corretta, il sistema operativo non sa che si tratta di una connessione Wi-Fi e la segnala come cablata.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Ho attivato registrazione basata su criteri in Teams e ora le chiamate peer-to-peer vengono contrassegnate come conferenze: cosa è successo?

Questo comportamento è previsto quando la registrazione basata su criteri è abilitata in Microsoft Teams. Registrazione basata su criteri usa un bot Teams registratore distribuito in Microsoft Azure per acquisire il contenuto della riunione ai fini della conformità. Nella gestione della qualità delle chiamate, "peer-to-peer" è una descrizione del flusso del traffico multimediale, non dell'interazione tra gli utenti. Poiché un bot registratore è di per sé parte della chiamata, la chiamata non è più peer-to-peer, ma una chiamata multi-party. Le chiamate multi-party vengono classificate come conferenze da Microsoft Teams, quindi verranno indicate come tali quando si visualizzano queste chiamate in CQD e in altri strumenti di qualità delle chiamate.

## <a name="related-articles"></a>Articoli correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload tenant e edificio](CQD-upload-tenant-building-data.md)

[Dati e report CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione dei flussi in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
