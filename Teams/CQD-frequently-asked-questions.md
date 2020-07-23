---
title: Domande frequenti sul dashboard di Call Quality (Call Quality Dashboard)
ms.author: lolaj
author: LolaJacobsen
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
description: Leggere le domande frequenti (FAQ) e le risposte su Microsoft teams Call Quality Dashboard (Call Quality Dashboard).
ms.openlocfilehash: 43dd0f85c21914320ff48c2e0aab82614670ff90
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372125"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Domande frequenti sul dashboard di Call Quality (Call Quality Dashboard)

## <a name="frequently-asked-questions"></a>Domande frequenti

[Perché Call Quality dashboard contrassegnare una chiamata come "buona" Se uno o più partecipanti alla riunione hanno avuto una cattiva esperienza?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Perché viene visualizzata una differenza di 0,2% nei valori delle chiamate e dei conteggi degli utenti sulle misure e su come ottenere volumi più accurati?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Perché i dati di Call Quality dashboard di Skype for business sono diversi da quelli di Call Quality dashboard da teams?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Perché non è possibile visualizzare EUII in Call Quality dashboard?](#why-cant-i-see-euii-in-cqd)

[Perché è possibile visualizzare le informazioni di Skype for business in Call Quality dashboard quando è stato filtrato solo per i team?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Perché Call Quality dashboard contrassegnare una chiamata come "buona" Se uno o più partecipanti alla riunione hanno avuto una cattiva esperienza?

Vedere le regole usate da Call Quality dashboard per la [classificazione del flusso](stream-classification-in-call-quality-dashboard.md).
 
Per i flussi audio, tutti e cinque i classificatori, calcolati per la media in base alla lunghezza della chiamata, potrebbero essere tutti all'interno dei parametri "buoni". Ciò non significa che gli utenti non abbiano sperimentato qualcosa che ha contribuito a una disattivazione audio, statica o glitch. 

Per determinare se si trattava di un problema di rete, esaminare il delta tra i valori medi per la sessione e i valori max. I valori max sono i massimi rilevati e segnalati durante la sessione.
 
Ecco un esempio di come risolvere questo problema. Supponiamo che tu prenda una traccia di rete durante una chiamata e i primi 20 minuti non ci siano pacchetti persi, ma allora hai una lacuna di 1,5 secondi di pacchetti e quindi buona per il resto della chiamata. La media sta per essere <perdita di pacchetti del 10% (0,1) anche in una analisi di Wireshark Trace RTP. Qual è stata la perdita di pacchetti max? 1,5 sec in un periodo di 5 secondi sarebbe 30% (0,3). Che si verificano nel periodo di campionamento di cinque secondi (forse può essere diviso nel periodo di campionamento)?
 
Se le metriche di rete hanno un aspetto ottimale nei valori medi e Max, cercare altri dati di telemetria: 
- Controllare il rapporto di eventi insufficienti della CPU per verificare se le risorse della CPU rilevate disponibili sono insufficienti e causano scarsa qualità. 
- Il dispositivo audio è in modalità half duplex per evitare di ricevere commenti e suggerimenti a causa dei microfoni da chiudere agli altoparlanti? 
- Controllare il rapporto tra l'evento AEC half duplex Device. È stato il dispositivo glitch o il microfono glitching introducendo rumore o statica a causa di rilasci audio USB quando è collegato a un hub o una stazione di ancoraggio:  
- Verificare le proporzioni degli eventi glitch e microfoni del dispositivo. Il dispositivo funzionava correttamente?  
- Controlla i rapporti di evento non funzionanti del dispositivo di acquisizione e rendering.


Per altre informazioni sulle dimensioni e le misure disponibili in telemetria Call Quality dashboard, leggere [le dimensioni e le misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).

Per il rumore di fondo, controllare il rapporto tra gli eventi per visualizzare la durata del disattivazione dei partecipanti.
 
Creare report dettagliati in Call Quality dashboard e filtrare l'ID riunione per esaminare tutti gli utenti e i flussi di una riunione e aggiungere i campi a cui si è interessati. Un utente che segnala il problema potrebbe non essere quello che ha avuto il problema. Stanno solo segnalando l'esperienza.
 
La telemetria non chiamerà necessariamente il problema, ma può aiutarti a capire meglio dove cercare e informare le tue decisioni. È la rete, il dispositivo, il driver o gli aggiornamenti del firmware, l'uso o l'utente?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Perché viene visualizzata una differenza di 0,2% nei valori delle chiamate e dei conteggi degli utenti sulle misure e su come ottenere volumi più accurati? 
Per calcolare le misure conteggio chiamate e conteggio utenti, viene eseguita un'operazione conta.se distinta rispetto alla chiamata o agli identificatori utente nel set di dati. Nei set di dati di grandi dimensioni esiste un errore di 0,2% inerente all'operazione conta.se distinta. Per il volume più accurato, devi basarti sulle misure di conteggio flusso poiché non si basano su questa operazione conta.se distinta. L'applicazione di filtri per ridurre il volume dei dati può ridurre l'errore, ma potrebbe non eliminare questa origine di errore in conteggi distinti per gli utenti e le chiamate. Fare riferimento a [dimensioni e misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md) per cui sono interessate le misure.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Perché i dati di Call Quality dashboard di Skype for business sono diversi da quelli di Call Quality dashboard da teams? 


> [!IMPORTANT]
> A partire dal 1 ° luglio 2020, il vecchio Call Quality Dashboard (CQD.lync.com) USA i dati della versione più recente di Call Quality Dashboard (Call Quality dashboard. Teams.microsoft.com). I dati di Call Quality dashboard meno recenti non sono più disponibili e non è possibile esportare i dati di un edificio o di un report. È comunque possibile usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for business), ma presto disattiveremo l'accesso a CQD.lync.com, quindi dovrai trasferirti in Call Quality dashboard. Teams.microsoft.com se non è già stato fatto.


Se si sta provando a confrontare i dati tra i vecchi Call Quality Dashboard dal portale legacy di Skype for business (cqd.lync.com) e gli ultimi Call Quality dashboard dall'interfaccia di amministrazione di Teams (cqd.teams.microsoft.com), si noterà subito che i dati non corrispondono. Questo perché gli ultimi report di Call Quality dashboard su molti scenari di chiamata aggiuntivi. Se si usano ancora i report della versione precedente di Call Quality dashboard, usare questo articolo per interpretare questi report: [Call Quality dashboard per Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Perché non è possibile visualizzare EUII in Call Quality dashboard?

Questi ruoli di amministratore possono accedere a Call Quality dashboard, ma non possono visualizzare EUII (informazioni identificabili per gli utenti finali):
- Lettore di report di Microsoft 365
- Specialista supporto comunicazioni Teams

Per altre informazioni sui ruoli che possono accedere a Call Quality dashboard, incluso EUII, vedere [assegnare ruoli per l'accesso a Call Quality dashboard](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Perché è possibile visualizzare le informazioni di Skype for business in Call Quality dashboard quando è stato filtrato solo per i team?

Quando si filtrano solo i team in report di Call Quality Dashboard (teams = 1), si filtrano tutte le chiamate in cui il *primo endpoint* è teams. Se il *secondo endpoint* è Skype for business, le informazioni verranno visualizzate nel report di Call Quality dashboard.

CQDv2 e CQDv3 avranno sempre conteggi totali diversi poiché CQDv3 avrà nuovi scenari che CQDv2 non avrà. Ecco perché confrontando i numeri totali di riepilogo o aggregati senza filtri saranno presenti le differenze previste.  

A seconda dello scenario dei clienti, CQDv3 includerà le chiamate in locale di SFB 2019 (se SFB 2019 viene usato con un connettore dati), le chiamate di Skype bot (AA, CVI, VDI), gli eventi dinamici e le chiamate PSTN. Scenari/funzionalità disponibili per i clienti, ma i loro dati non sono in Call Quality dashboard V2.

Ad esempio, è prevedibile che i clienti e i flussi audio di 200.000, con 5000 errori nel report di riepilogo di Call Quality dashboard V2; Versus 300.000 flussi audio con 5500 errori (provenienti da 2019 su Prem chiamate, CVI chiamate, chiamate PSTN e così via) in Call Quality dashboard V3.

Per determinare se sono presenti differenze impreviste, è necessario esaminare varie disaggregazioni dei dati complessivi.  Confronta con intenti.  L'affettamento dei dati tramite la coppia di categorie di agenti utente è una delle prime cose che consigliamo.  Il *primo prodotto* e il *secondo prodotto* sono anche buoni filtri dei dati.  


## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

[Che cos'è Call Quality dashboard?](CQD-what-is-call-quality-dashboard.md)

[Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e della creazione](CQD-upload-tenant-building-data.md)

[Dati e report di Call Quality dashboard](CQD-data-and-reports.md)

[Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in Call Quality dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)