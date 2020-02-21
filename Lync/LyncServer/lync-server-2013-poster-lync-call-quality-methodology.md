---
title: 'Lync Server 2013: poster: metodologia della qualità delle chiamate di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: caff54dd2919bacfda02fceff138650f90bae650
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Metodologia della qualità delle chiamate di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-06-24_

Questo articolo è una compagna del poster della [metodologia della qualità delle chiamate di Lync](https://go.microsoft.com/fwlink/?linkid=391841) , che è possibile scaricare dall'area download.

![Poster che descrive il processo di CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster che descrive il processo di CQM")

È possibile utilizzare questo poster per informazioni su CQM, la metodologia relativa alla qualità delle chiamate per Lync 2013 e 2010 che consente di individuare ed eliminare i problemi che influiscono sulla qualità delle chiamate e sull'esperienza utente per le implementazioni di Lync che includono le funzionalità di VoIP aziendale. La metodologia della qualità delle chiamate è una nuova soluzione per la risoluzione dei problemi e la gestione del servizio che può migliorare gli sforzi di ottimizzazione dei servizi VoIP aziendale in Lync. In questo articolo, è possibile ottenere ulteriori informazioni su CQM, sui tipi di server e sulle soluzioni monitorate e su cosa fare con i dati di telemetria raccolti.

In caso di domande sull'utilizzo di CQM, è possibile inoltrare le proprie domande a cqmfeedback@microsoft.com.

Nel poster vengono illustrate le aree seguenti:

  - Che cos'è Lync CQM?

  - Priorità: eseguire le query di tendenza

  - PCD

  - Gestito/non gestito

  - La strada del server Plant

  - La strada dell'ultimo miglio

  - La strada dei punti finali

  - Gestione dei servizi

  - Regole del gioco di bordo

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Che cos'è Lync CQM?

La metodologia della qualità delle chiamate è una nuova soluzione per la risoluzione dei problemi e la gestione del servizio che può migliorare gli sforzi di ottimizzazione dei servizi VoIP aziendale in Lync. Quando si utilizza CQM, è necessario meno sforzo per garantire la qualità delle chiamate e la soddisfazione degli utenti per i servizi VoIP aziendale. CQM è illustrato in una descrizione più completa della [metodologia della qualità delle chiamate](https://go.microsoft.com/fwlink/p/?linkid=615208). Questo articolo e il poster sono riassunti di quel contenuto.

CQM interrompe la risoluzione dei problemi del sistema in tre percorsi o "strade". Queste sono le seguenti: la strada del server Plant, che analizza i server e i collegamenti tra di essi, la strada dei punti finali, che esamina i dispositivi utente e i supporti utilizzati per effettuare le chiamate e l'ultima strada di Mile, che risolve l'integrazione delle chiamate di rete a commutazione tradizionale.

Ogni strada è suddivisa in più segmenti relativi a un'area o a un argomento specifico e per ogni segmento vengono apportate informazioni su un livello di qualità accettabile, vengono eseguite azioni per ottenere tale livello di qualità e viene messo in atto un piano di gestione dei servizi per mantenere livello di qualità prima di passare all'argomento successivo.

Il poster presenta Lync CQM come un gioco da tavola per tre giocatori, ognuno dei quali passerà attraverso una delle strade. Le schede incluse nel download vengono utilizzate per simulare gli ostacoli alla qualità delle chiamate che devono essere superate. Suggerimenti e suggerimenti sugli obiettivi e su come raggiungerli sono inclusi lungo i tre percorsi, nonché linee guida per la definizione della priorità per la strada da perseguire in primo luogo nelle applicazioni effettive (nel gioco, tutte e tre le strade vengono affrontate in parallelo).

Come funziona CQM nelle versioni precedenti di Lync? CQM è un nuovo per Lync 2013, ma la maggior parte di esso può essere adattato per essere utilizzato con Lync 2010. CQM potrebbe funzionare a un livello di Microsoft Office Communicator, ma non è stato testato e non è supportato.

In caso di domande sull'utilizzo di CQM, è possibile inoltrare le proprie domande a cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorità: eseguire le query di tendenza

Il primo passaggio di CQM consiste nell'eseguire ciascuna delle query di tendenza per due settimane e quindi analizzare i risultati. Assegnare la priorità all'azione correttiva da parte del collaboratore del flusso più grande, del rapporto di flusso meno elevato e delle aree gestite (quelli che si controllano).Se l'unità di controllo a più punti audio/video (MCU AV) o le query Mediation mostrano risultati scarsi, iniziare con la strada Plant rossa o server.Se le query cablate o wireless mostrano risultati scadenti, iniziare con la strada blu o l'ultima miglia.Se la VPN o le query esterne mostrano risultati scadenti, iniziare sulla strada verde o finale.

Dopo aver scelto una strada per iniziare, definire una destinazione per ogni area (Assert), lavorare per soddisfare tale obiettivo (raggiungere) e quindi implementare le procedure per rimanere in target (maintain). È inoltre possibile utilizzare questo poster come gioco per comprendere i principi che stanno alla base di CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

Lo strumento di diagnostica di PreCall (PCD) consentirà di identificare e diagnosticare i problemi della rete perimetrale (il database QoE non raccoglie informazioni sul proprio perimetro o sulla propria rete geometrica), nonché di risolvere eventuali problemi di connessione nell'ultimo miglio. Lo strumento è disponibile sia come app Windows 8 Modern o come applicazione desktop di Windows all' https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88indirizzo.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Gestito/non gestito

La distribuzione e l'infrastruttura di rete di Lync Server possono in genere essere suddivisi in spazi gestiti o non gestiti. Lo spazio gestito include l'intera infrastruttura del server e della rete cablata all'interno. Lo spazio non gestito è l'infrastruttura wireless e l'infrastruttura di rete esterna.

Questa distinzione aumenta la chiarezza dei dati e aiuta l'organizzazione a concentrarsi sui carichi di lavoro che avranno un impatto misurabile sulla qualità vocale e video degli utenti. Gli utenti hanno un'aspettativa di qualità diversa se la chiamata viene applicata all'infrastruttura che si è proprietaria (gestita) rispetto all'infrastruttura che è in parte sotto il controllo di un'altra entità (non gestita). Questo non significa che gli utenti wireless sono lasciati ai propri dispositivi per avere ottime esperienze di Lync Server.

Migliorare la qualità vocale nello spazio non gestito richiede una qualità elevata nello spazio gestito. Se la rete wireless (Wi-Fi) viene considerata come uno spazio gestito o non gestito spetta alla propria organizzazione. Le tecniche per ottenere un ambiente integro sono diverse nei due spazi, come lo sono le soluzioni.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>La strada del server Plant

Il segmento 1 della strada del server Plant indirizza i server effettivi nell'implementazione di Lync. Raccogliere i dati di KHI sia per il server stesso che per il relativo ruolo nell'implementazione e analizzarne i risultati. Se l'azione è garantita, correggere eventuali problemi riscontrati. Ulteriori dettagli su questo argomento sono riportati nell'articolo sugli [indicatori di integrità chiave in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) che accompagna il poster di KHI.

Il segmento successivo indirizza i flussi multimediali tra il server MCU AV e Mediation Server. Iniziare determinando gli obiettivi per le soglie di flusso scarse. I flussi poveri sono in \> genere PacketLossRate .01 \> o PacketLossRateMax. 05. Un altro obiettivo auspicabile \< è PoorStreamsRatio 2%. Successivamente, utilizzare query dettagliate per individuare coppie di AVMCU e Mediation Server con flussi insufficienti, esaminare la causa di flussi insufficienti, esaminare le apparecchiature di rete nei percorsi di flusso scarso, correggere i flussi insufficienti e definire la configurazione ottimale o "oro" per la rete Attrezzatura. Per mantenere la propria realizzazione, implementare i processi e gli strumenti per gestire la deriva della configurazione e segnalare nuove aree problematiche.

Successivamente, esaminare i flussi multimediali tra il Mediation Server e il gateway PSTN (Public Switched Telephone Network). Iniziare determinando gli obiettivi per le soglie di flusso scarse. I flussi poveri sono in \> genere PacketLossRate .01 \> o PacketLossRateMax. 05. Un altro obiettivo auspicabile \< è PoorStreamsRatio 2%. Successivamente, utilizzare query dettagliate per trovare coppie di Mediation Server e gateway con flussi insufficienti, esaminare la causa di flussi insufficienti, esaminare le apparecchiature di rete nei percorsi di flusso scarso, correggere flussi insufficienti e definire la configurazione ottimale o "oro" per la rete Attrezzatura. Per mantenere la propria realizzazione, implementare i processi e gli strumenti per gestire la deriva della configurazione e segnalare nuove aree problematiche.

Infine, esaminare le metriche di integrità per il gateway PSTN. Identificare le statistiche che mostrano l'integrità e definire le destinazioni nei suoi confronti. Non vengono fornite indicazioni specifiche in questo modo, poiché è possibile utilizzare molti possibili gateway. Una volta stabilite le destinazioni, correggere i risultati in base alle esigenze per raggiungere l'obiettivo. nel processo è probabile che si definisca una configurazione "oro" o ottimale per il gateway. Per mantenere la propria realizzazione, implementare i processi e gli strumenti per gestire la deriva della configurazione e segnalare nuove aree problematiche. Tenere presente che gli aggiornamenti del firmware e del software possono alterare la configurazione o portare a modificare la definizione della configurazione "Gold", in modo da avvicinarsi a queste attività con attenzione.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>La strada dell'ultimo miglio

Dei due modi in cui i client si connettono alla rete, è previsto che Wired consegni la qualità più alta e che corrisponda al livello di priorità iniziale per i problemi relativi all'ultimo chilometro. Utilizzare la query Wired CQM (LastMile\_0\_Wired) e i dati del rapporto flussi scadenti forniti. È consigliabile definire una destinazione PoorStreamsRatio \< 5% per i siti \> con 300 flussi. Per raggiungere i propri obiettivi, correggere le subnet ordinate dal peggiore al meglio e implementare QoS.

Dopo aver ottimizzato la qualità delle connessioni cablate, è più facile migliorare la qualità wireless perché l'infrastruttura wireless si siede in cima al core cablato in ogni posizione. I flussi wireless insufficienti in un sito con una buona qualità cablata devono essere attribuiti ai componenti wireless specifici. La query wireless CQM (LastMile\_1\_wireless) opera su un intervallo di date e restituirà tutti i flussi wireless interni nell'ambiente provenienti da client Lync a o da server conferenza o Mediation Server. È consigliabile definire una destinazione PoorStreamsRatio \< 5% per i siti \> con 300 flussi. Per raggiungere i propri obiettivi, correggere le subnet ordinate dal peggiore al meglio e implementare QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>La strada dei punti finali

Avviare richieste di informazioni sulla strada dei punti finali con gli auricolari e altri dispositivi noti per produrre una qualità accettabile quando vengono utilizzati con Lync. È consigliabile un target AvgSendListen MOS \> 3,6 per le implementazioni con oltre 100 flussi. Ottenere la destinazione identificando i dispositivi problematici e correggerli o sostituirli.

Successivamente, esaminare il dispositivo o il PC che elabora l'audio per le chiamate degli utenti finali. Una metrica di qualità di destinazione consigliata \<è un AudioMicGlitchRate = 1. Quando si identificano le configurazioni di sistema ottimali per i sistemi utente, definire una configurazione PC "dorata", incluse le versioni dei driver.

A questo punto, esaminare il percorso di rete di un flusso audio da un sistema di endpoint di Lync, che può causare una qualità audio scadente. Se l'audio si sposta su una connessione VPN, è possibile che vengano visualizzati problemi di latenza. Se un client Lync interno non è in grado di stabilire un flusso Direct Media su un altro client Lync interno per una chiamata a due o peer-to-peer, ritornerà a un percorso che passa attraverso un server perimetrale Lync, riconducendo di nuovo ai problemi di latenza e aumentando le potenzialità per perdita e instabilità. È consigliabile definire una metrica di qualità pari a 0% media su VPN. Durante la correzione per raggiungere il target impostato, identificare le subnet dei problemi e esaminare le regole del firewall, i formatori di pacchetti e altre importanti configurazioni degli strumenti di rete.

I pacchetti IP possono utilizzare il protocollo TCP (Transmission Control Protocol) o UDP (User Datagram Protocol). TCP è ottimale per i flussi di dati. UDP è senza connessione ed è più efficiente per i supporti poiché i meccanismi di ripristino TCP non possono risolvere la perdita nei media in tempo reale. Lync preferisce sempre UDP, ma tornerà a TCP se non è possibile stabilire una sessione UDP. Le sessioni multimediali su TCP presentano una qualità più bassa rispetto all'UDP. Si consiglia una definizione di qualità delle connessioni 0% su TCP. Durante la correzione per raggiungere il target impostato, identificare le subnet dei problemi e esaminare le regole del firewall, i formatori di pacchetti e altre importanti configurazioni degli strumenti di rete.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Gestione dei servizi

La gestione dei servizi è lo stato finale di CQM e la destinazione per tutte e tre le strade. Per mantenere livelli elevati di qualità delle chiamate, monitorare queste aree:

1.  **Gli utenti** -le attività di correzione devono mostrare un aumento misurabile della soddisfazione dell'utente. È possibile misurarlo tramite ticket di problema o altri meccanismi di commenti e suggerimenti. È inoltre possibile pubblicare metriche di qualità.

2.  **Process** -definire i processi quotidiani, settimanali e mensili in operazionalizzare CQM. Il ritmo di monitoraggio inizia con una frequenza più alta durante la correzione (ogni giorno) e si sposta su una frequenza più bassa (mensilmente) Man mano che si stabilizza.

3.  **Strumenti** : consente di identificare gli strumenti per la misura e il correttivo. Potrebbe essere utile per automatizzare l'esecuzione delle query di CQM per supportare i processi. La correzione potrebbe richiedere strumenti aggiuntivi, ad esempio per applicare configurazioni standardizzate sugli elementi di rete o la risoluzione dei problemi relativi alla perdita di flussi scadenti.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Regole del gioco di bordo

È possibile utilizzare questo poster come riferimento a un'implementazione di CQM o come gioco per la pratica dei concetti. Per la riproduzione, è necessario un dado a 1 6 facce e le schede fornite. È disponibile una versione scaricabile delle schede per la stampa sui biglietti da visita standard Avery 5871.

Il gioco è per 3 giocatori. Sono disponibili tre percorsi che possono essere utilizzati dai giocatori per ottenere la qualità desiderata e raggiungere lo stato di gestione dei servizi Center: server Plant, end point e Last Mile. Ogni percorso viene interrotto lungo la strada in cui vengono asseriti obiettivi di qualità, ottenendo obiettivi e mantenendo un aspetto del sistema. Posizionare le schede nell'area indicata sopra, quindi disegnare 5 schede. Esaminare le schede disegnate e inserirle nel relativo segmento di scheda. Ogni giocatore si sposta, passo dopo passo, nelle schede del percorso, asserendo obiettivi di qualità, ottenendo tali obiettivi e mantenendo i livelli di servizio. Il gioco viene completato quando tutti i giocatori raggiungono lo stato di gestione del servizio Center. Le regole più dettagliate sono fornite con il download della scheda gioco.

Per **affermare** una destinazione di qualità, esaminare i parametri applicabili a tale destinazione e dichiarare ad alta voce ciò che si vuole e non si sceglie di accettare. Sono stati consigliati i punti iniziali, ma è necessario effettuare la chiamata finale. L'eccezione è data KHI, in cui devono essere utilizzati gli standard stabiliti da Microsoft. Vedere il poster di KHI di accompagnamento.

Per **ottenere** il gioco, utilizzare le schede fornite al posto delle query di sistema e dei dati di KHI. Se all'inizio del gioco non è stata disegnata una scheda relativa a un determinato aspetto, è possibile continuare a superarla. Se è presente una scheda pertinente, eseguire il rollback del dado. Se è stato eseguito il rollforward con il numero indicato sulla scheda, è stato eseguito il successo. Se si passa al numero indicato o al di sopra, è necessario disegnare un'altra carta dal deck. Se la scheda indica che è necessario eseguire il rollforward di due o più giocatori, è necessario che tutti gli utenti vengano ripartiti.

Per **mantenere** il gioco, dichiarare ad alta voce il piano di gestione dei servizi relativo a tale aspetto dell'ambiente Lync.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Guida alla rete di Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicatori di integrità chiave: la base per la gestione dei server Lync integri](https://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia qualità chiamata Lync](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

