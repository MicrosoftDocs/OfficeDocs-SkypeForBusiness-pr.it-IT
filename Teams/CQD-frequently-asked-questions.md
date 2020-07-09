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
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086172"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Domande frequenti sul dashboard di Call Quality (Call Quality Dashboard)

## <a name="frequently-asked-questions"></a>Domande frequenti

[Perché Call Quality dashboard contrassegnare una chiamata come "buona" Se uno o più partecipanti alla riunione hanno avuto una cattiva esperienza?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Perché viene visualizzata una differenza di 0,2% nei valori delle chiamate e dei conteggi degli utenti sulle misure e su come ottenere volumi più accurati?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Perché i dati del report Call Quality dashboard V2 hanno un aspetto diverso rispetto ai dati del report di Call Quality dashboard V3?](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

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

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>Perché i dati del report Call Quality dashboard V2 hanno un aspetto diverso rispetto ai dati del report di Call Quality dashboard V3? 

Se vengono visualizzate differenze di dati tra Call Quality dashboard V2 e V3, verificare che il confronto o la convalida dei dati sia stata eseguita su un livello "mele-mele" e su uno stretto, non su un livello aggregato. Se ad esempio si filtrano entrambi i report per i dati client desktop di MSIT ' Building 30', la percentuale di qualità scadente dovrebbe essere uguale tra V2 e V3.

La classificazione CQDv2 per l'errore CallSetup viene considerata solo per la modalità "audio", in CQDv3 questa classificazione si verifica per ogni modalità (audio, video e condivisione applicazioni) ed è rappresentata nel rispettivo flusso di modalità. 

Per i team, CQDv2 applica lo stesso feedback degli utenti a tutte le modalità CQDv3 applica la base di feedback sulla modalità per i team.

Call Quality dashboard v3 include 
1. Chiamate di Skype for Business Server 2019 
2. Chiamate Skype bot, ad esempio: operatore automatico, coda di chiamata, servizio di annuncio conferenza, 
3. Interfaccia desktop virtuale,
4. Interoperabilità video per conferenze
3. Le chiamate di Publisher e Presenter di eventi dinamici e 
4. Chiamate PSTN. 

Per informazioni su come usare questi modelli di Power BI per analizzare e segnalare i dati di Call Quality dashboard, leggere [usare Power BI per i report di Call Quality dashboard](cqd-power-bi-query-templates.md).


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Perché i dati di Call Quality dashboard di Skype for business sono diversi da quelli di Call Quality dashboard da teams? 


> [!IMPORTANT]
> A partire dal 1 ° luglio 2020, il vecchio Call Quality dashboard accede ai dati dall'ultima Call Quality dashboard. I dati di Call Quality dashboard meno recenti non sono più disponibili e non è possibile esportare i dati di un edificio o di un report.


Se si sta provando a confrontare i dati tra i vecchi Call Quality Dashboard dal portale legacy di Skype for business (cqd.lync.com) e gli ultimi Call Quality dashboard dall'interfaccia di amministrazione di Teams (cqd.teams.microsoft.com), si noterà subito che i dati non corrispondono. Questo perché gli ultimi report di Call Quality dashboard su molti scenari di chiamata aggiuntivi. Se si usano ancora i report della versione precedente di Call Quality dashboard, usare questo articolo per interpretare questi report: [Call Quality dashboard per Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).



Ecco un esempio di applicazione di filtri specifici per confrontare i dati di Call Quality dashboard V2 e Call Quality dashboard V3:

1. Record QoE disponibile = vero

2. Add is Filter Pair server con valore: client: client e client: Server. La maggior parte dei tenant preferisce escludere server: chiamate server.

3. Aggiungere un filtro per la categoria agente utente e filtrare l'operatore automatico, la coda delle chiamate, il bot, il sistema di sala, MediationServer, il servizio di annuncio conferenza, VDI e così via.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="Screenshot dell'applicazione di filtri specifici in Call Quality dashboard V3":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="Screenshot dell'applicazione di filtri specifici in Call Quality dashboard V2":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Altre differenze previste tra Call Quality dashboard V2 e Call Quality dashboard V3

Per altre informazioni sulle differenze tra le versioni precedenti e quelle più recenti di Call Quality dashboard, vedere il Blog [introduttivo sul dashboard di qualità delle chiamate avanzate](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) , dal 5 novembre 2019.


> [!IMPORTANT]
> A partire dal 1 ° luglio 2020, il vecchio Call Quality dashboard accede ai dati dall'ultima Call Quality dashboard. I dati di Call Quality dashboard meno recenti non sono più disponibili e non è possibile esportare i dati di un edificio o di un report.

È probabile che vengano visualizzate più differenze di dati tra i report di Call Quality dashboard precedenti e quelli più recenti a livello di aggregazione o di riepilogo. Se si confrontano i dati a un livello più granulare, si otterrà un confronto "mele-mele". Ad esempio, se si stanno esaminando i dati per un singolo edificio, la percentuale di qualità scadente dovrebbe essere la stessa tra i report di Call Quality dashboard precedenti e quelli nuovi.

- Selezionare uno scenario con uno stato di priorità limitato, ad esempio connessioni cablate aziendali, desktop di Windows o una singola area geografica o un edificio.
- Controlla gli intervalli di indirizzi IP per i team MR, TR o MP. Gli intervalli di team sono più recenti di Skype for business online e questo può causare problemi di connettività che coinvolgono i firewall.
- Non confrontare i numeri di riepilogo o di primo livello. Questi confronti ti consentiranno di confrontare un grande volume di chiamate Skype for business online su una connessione cablata aziendale a un piccolo volume di chiamate di Team su una rete LTE o privata.
- Attenzione alla distorsione della posizione e alle differenze di popolazione: esistono molti confronti troppo dissimili per essere utili:
  - NOAM: APAC
  - NY: Goa
  - Cablata : WiFi
  - Rete aziendale: rete domestica
  
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