---
title: 'Lync Server 2013: poster: metodologia di qualità delle chiamate di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e18dc59e0b8669bb48962874291e63523f37eb48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Metodologia di qualità delle chiamate di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-06-24_

Questo articolo è un compagno del poster della [metodologia di qualità delle chiamate di Lync](http://go.microsoft.com/fwlink/?linkid=391841) , che è possibile scaricare dall'area download.

![Poster che descrive il]manifesto del processo di CQM che(images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "descrive il processo di CQM")

Puoi usare questo poster per informazioni su CQM, la metodologia di qualità delle chiamate per Lync 2013 e 2010 che ti aiuta a trovare ed eliminare i problemi che interessano la qualità delle chiamate e l'esperienza utente per le implementazioni di Lync che includono le funzionalità VoIP aziendale. La metodologia per la qualità delle chiamate è un nuovo Framework per la risoluzione dei problemi e servizi che consente di migliorare lo stato di miglioramento dei servizi VoIP aziendale in Lync. In questo articolo è possibile ottenere ulteriori informazioni su CQM, sui tipi di server e sulle soluzioni monitorate e su cosa fare con i dati di telemetria raccolti.

In caso di domande su come usare CQM, è possibile inviare le proprie domande a cqmfeedback@microsoft.com.

Il poster illustra le aree seguenti:

  - Che cos'è Lync CQM?

  - Priorità: eseguire query di tendenza

  - PCD

  - Gestito/non gestito

  - Server Plant Road

  - L'ultima strada di miglio

  - Strada dei punti finali

  - Gestione dei servizi

  - Regole del gioco da tavolo

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Che cos'è Lync CQM?

La metodologia per la qualità delle chiamate è un nuovo Framework per la risoluzione dei problemi e servizi che consente di migliorare lo stato di miglioramento dei servizi VoIP aziendale in Lync. Quando si usa CQM, è necessario meno sforzo per garantire la qualità delle chiamate e la soddisfazione degli utenti per i servizi VoIP aziendale. CQM è spiegato in modo più completo nella [metodologia](http://go.microsoft.com/fwlink/p/?linkid=615208)relativa alla qualità delle chiamate. Questo articolo e il poster sono riassunti di tale contenuto.

CQM suddivide la risoluzione dei problemi di sistema in tre percorsi o "strade". Questi sono: la strada server Plant, che esamina i server e i collegamenti tra di essi, la strada dei punti finali, che analizza i dispositivi utente e i supporti usati per trasportare le chiamate e l'ultima strada di Mile, che affronta l'integrazione delle chiamate tradizionali di rete telefonica commutata.

Ogni strada è divisa in più segmenti relativi a un'area o un argomento specifico e a ogni definizione di segmento viene applicata una qualità accettabile, vengono adottate le azioni per ottenere tale livello di qualità e viene messo in atto un piano di gestione dei servizi per mantenere livello di qualità prima di passare all'argomento successivo.

Il poster presenta Lync CQM come gioco da tavolo per tre giocatori, ognuno dei quali passerà attraverso una delle strade. Le schede incluse nel download vengono usate per simulare gli impedimenti alla qualità delle chiamate che devono essere superate. Suggerimenti e suggerimenti sulle destinazioni e su come raggiungerli sono inclusi lungo i tre percorsi, nonché le linee guida per la definizione delle priorità per cui perseguire prima le applicazioni effettive (nel gioco tutte e tre le strade vengono affrontate in parallelo).

Come funziona CQM nelle versioni precedenti di Lync? CQM è una novità per Lync 2013, ma la maggior parte può essere adattata per l'uso con Lync 2010. CQM può funzionare in misura con Microsoft Office Communicator, ma non è stato testato e non è supportato.

In caso di domande su come usare CQM, è possibile inviare le proprie domande a cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorità: eseguire query di tendenza

Il primo passaggio in CQM consiste nell'eseguire ogni query di tendenza per due settimane e quindi analizzare i risultati. Assegnare la priorità all'azione correttiva per il più grande collaboratore dello stream, il rapporto di flusso scadente più alto e le aree gestite (quelle che controlli).Se l'unità di controllo a più punti audio/video (MCU AV) o le query di mediazione mostrano risultati scarsi, iniziare dalla strada centrale rossa o server.Se le query cablate o wireless mostrano risultati scadenti, iniziare dalla strada blu o dell'ultimo miglio.Se le query VPN o esterne mostrano risultati scadenti, iniziare dalla strada verde o i punti finali.

Dopo aver scelto una strada per iniziare, definire una destinazione per ogni area (asserzione), lavorare per rispondere a tale obiettivo (raggiungere) e quindi implementare le procedure per rimanere in target (maintain). Puoi anche usare questo poster come gioco per comprendere i principi dietro CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

Lo strumento di diagnostica di prechiamata (PCD) ti aiuterà a identificare e diagnosticare i problemi nella rete perimetrale (il database QoE non raccoglie le informazioni sul bordo o la rete perimetrale) e anche per la risoluzione di problemi relativi alle connessioni nell'ultimo miglio. Lo strumento è disponibile sia come app di Windows 8 Modern che con un'app desktop di http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88Windows.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Gestito/non gestito

L'infrastruttura di distribuzione e di rete di Lync Server può in genere essere divisa in spazi gestiti e non gestiti. Lo spazio gestito include l'intera infrastruttura di rete cablata e il server. Lo spazio non gestito è l'infrastruttura wireless e l'infrastruttura di rete esterna.

Questa distinzione aumenta la chiarezza dei dati e consente all'organizzazione di concentrarsi sui carichi di lavoro che avranno un impatto misurabile sulla qualità della voce e del video degli utenti. Gli utenti hanno una diversa aspettativa di qualità se la chiamata viene inserita nell'infrastruttura che si è proprietari (gestita) rispetto all'infrastruttura che è in parte sotto il controllo di un'altra entità (non gestita). Questo non significa che gli utenti wireless siano lasciati ai propri dispositivi per avere ottime esperienze di Lync Server.

Migliorare la qualità vocale nello spazio non gestito richiede una qualità elevata nello spazio gestito. Se la connessione wireless (Wi-Fi) è considerata uno spazio gestito o non gestito dipende dall'organizzazione. Le tecniche per ottenere un ambiente sano sono diverse nei due spazi, così come le soluzioni.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>Server Plant Road

Il segmento 1 della strada server Plant risolve i server effettivi nell'implementazione di Lync. Raccogliere i dati di KHI riguardanti sia il server stesso che il relativo ruolo nell'implementazione e analizzare il risultato. Se l'azione è garantita, correggere eventuali problemi riscontrati. Altri dettagli su questo argomento sono presentati nell'articolo sugli [indicatori di integrità chiave in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) che accompagna il poster di KHI.

Il segmento successivo risolve i flussi multimediali tra il server MCU AV e Mediation Server. Per iniziare, determinare le destinazioni per le soglie di flusso scarse. I flussi scadenti sono in \> genere PacketLossRate .01 \> o PacketLossRateMax. 05. Un altro obiettivo auspicabile \< è PoorStreamsRatio 2%. Quindi, USA query dettagliate per trovare coppie di AVMCU e Mediation Server con flussi scadenti, analizzare la causa di flussi scadenti, esaminare le apparecchiature di rete nei percorsi di flusso scarsi, correggere flussi scadenti e definire la configurazione ottimale o "Gold" per la rete attrezzature. Per mantenere il risultato, implementare processi e strumenti per gestire la deriva della configurazione e segnalare nuove aree problematiche.

Esaminare quindi i flussi multimediali tra Mediation Server e il gateway PSTN (Public Switched Telephone Network). Per iniziare, determinare le destinazioni per le soglie di flusso scarse. I flussi scadenti sono in \> genere PacketLossRate .01 \> o PacketLossRateMax. 05. Un altro obiettivo auspicabile \< è PoorStreamsRatio 2%. Quindi, USA query dettagliate per trovare le coppie di Mediation Server e gateway con flussi scadenti, analizzare la causa di flussi scadenti, esaminare le apparecchiature di rete nei percorsi di flusso scarsi, correggere flussi scadenti e definire la configurazione ottimale o "Gold" per la rete attrezzature. Per mantenere il risultato, implementare processi e strumenti per gestire la deriva della configurazione e segnalare nuove aree problematiche.

Esaminare infine le metriche di integrità per il gateway PSTN. Identificare le statistiche che mostrano l'integrità e definire le relative destinazioni. In questo caso non vengono fornite indicazioni specifiche per poter usare molti possibili gateway. Dopo aver stabilito gli obiettivi, è necessario correggere i risultati per ottenere la destinazione; nel processo si definirà probabilmente una configurazione "Gold" o ottimale per il gateway. Per mantenere il risultato, implementare processi e strumenti per gestire la deriva della configurazione e segnalare nuove aree problematiche. Tieni presente che gli aggiornamenti del firmware e del software possono modificare la configurazione o consentirti di modificare la definizione della configurazione "Gold", quindi puoi avvicinarti a queste attività con attenzione.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>L'ultima strada di miglio

Tra i due modi in cui i client si connettono alla rete, è previsto che Wired fornisca la qualità più alta e, in questo modo, deve essere lo stato iniziale per i problemi dell'ultimo miglio. Usare la query cablata CQM (\_LastMile\_0 Wired) e i dati di rapporto flussi poveri forniti. È consigliabile definire una destinazione PoorStreamsRatio \< 5% per i siti \> con flussi di 300). Per raggiungere i propri obiettivi, correggere le subnet ordinate dal peggio al meglio e implementare QoS.

Dopo aver ottimizzato la qualità delle connessioni cablate, il miglioramento della qualità wireless diventa più semplice perché l'infrastruttura wireless si trova in cima al nucleo cablato in ogni posizione. I flussi wireless poveri in un sito con una buona qualità cablata devono essere attribuiti agli specifici componenti wireless. La query wireless CQM (LastMile\_1\_wireless) opera su un intervallo di date e restituirà tutti i flussi wireless interni nell'ambiente da client Lync a o da server di conferenza o Mediation Server. È consigliabile definire una destinazione PoorStreamsRatio \< 5% per i siti \> con flussi di 300). Per raggiungere i propri obiettivi, correggere le subnet ordinate dal peggio al meglio e implementare QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>Strada dei punti finali

Avviare richieste di informazioni nella strada dei punti finali con gli auricolari e altri dispositivi noti per produrre qualità accettabile se usati con Lync. Suggeriamo un target AvgSendListen MOS \> 3,6 per le implementazioni con oltre 100 flussi. Ottenere la destinazione identificando i dispositivi problematici e correggerli o sostituirli.

Esaminare quindi il dispositivo o il PC per l'elaborazione dell'audio per le chiamate degli utenti finali. Una metrica di qualità di destinazione suggerita \<è un AudioMicGlitchRate = 1. Quando si identificano le configurazioni di sistema ottimali per i sistemi utente, definire una configurazione PC "dorata", incluse le versioni dei driver.

Esaminiamo ora il percorso di rete di un flusso audio da un sistema di endpoint Lync, che può causare una scarsa qualità audio. Se l'audio viaggia su una connessione VPN, è possibile che vengano visualizzati problemi di latenza. Se un client Lync interno non riesce a stabilire un flusso multimediale diretto in un altro client Lync interno per una chiamata a due o peer-to-peer, ritornerà in un percorso che si inoltra attraverso un server perimetrale Lync, ancora una volta porta a problemi di latenza e un potenziale maggiore per perdita e jitter. Ti consigliamo di definire una metrica di qualità pari a 0% di elementi multimediali su VPN. Man mano che si rimedia per ottenere la destinazione impostata, identificare le subnet dei problemi e analizzare le regole del firewall, i formatori di pacchetti e altre importanti configurazioni di dispositivi di rete.

I pacchetti IP possono usare TCP (Transmission Control Protocol) o UDP (User Datagram Protocol). TCP è ottimale per i flussi di dati. UDP è senza connessione ed è più efficiente per gli elementi multimediali, poiché i meccanismi di ripristino TCP non possono risolvere la perdita in elementi multimediali in tempo reale. Lync preferisce sempre UDP, ma tornerà a TCP se non è possibile stabilire una sessione UDP. Le sessioni multimediali su TCP espongono una qualità più scadente rispetto a UDP. È consigliabile una definizione di qualità di connessioni 0% su TCP. Man mano che si rimedia per ottenere la destinazione impostata, identificare le subnet dei problemi e analizzare le regole del firewall, i formatori di pacchetti e altre importanti configurazioni di dispositivi di rete.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Gestione dei servizi

La gestione dei servizi è lo stato finale di CQM e la destinazione per tutte e tre le strade. Per mantenere livelli elevati di qualità delle chiamate, monitorare queste aree:

1.  **Gli utenti** : le attività correttive dovrebbero mostrare un aumento misurabile della soddisfazione dell'utente. È possibile misurare questo problema tramite ticket o altri meccanismi di feedback. È anche possibile pubblicare le metriche di qualità.

2.  **Processo** : definire processi giornalieri, settimanali e mensili in operazionalizzare CQM. Il ritmo di monitoraggio inizia con una frequenza più alta mentre si sta rimediando (giornalmente) e si sposta su una frequenza inferiore (mensile) durante la fase di stabilizzazione.

3.  **Strumenti** -identificare gli strumenti per misurare e correggere. Può risultare utile automatizzare l'uso delle query CQM per supportare i processi. I correttivi possono richiedere altri strumenti, ad esempio per applicare configurazioni standardizzate agli elementi di rete o per la risoluzione dei problemi di perdita nei flussi scadenti.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Regole del gioco da tavolo

Puoi usare questo poster come riferimento a un'implementazione di CQM o come gioco per la pratica dei concetti. Per giocare, è necessario un dado a 1 6 e le schede fornite. Una versione scaricabile delle schede è disponibile per la stampa su biglietti da visita standard Avery 5871.

Il gioco è per 3 giocatori. I giocatori possono usare tre percorsi per ottenere la qualità desiderata e raggiungere lo stato di gestione del servizio centrale: server Plant, end point e Last Mile. Ogni percorso si arresta lungo il tragitto in cui si asseriscono obiettivi di qualità, raggiungere obiettivi e mantenere un aspetto del sistema. Posizionare le schede nell'area indicata sopra e quindi disegnare 5 carte. Esaminare le schede disegnate e inserirle nel relativo segmento di bacheca. Ogni giocatore passa per passo tra le schede del percorso, asserendo obiettivi di qualità, ottenendo questi obiettivi e mantenendo i livelli di servizio. Il gioco viene completato quando tutti i giocatori raggiungono lo stato di gestione del servizio centrale. Vengono fornite regole più dettagliate con il download della scheda gioco.

Per **affermare** una destinazione di qualità, esaminare i parametri applicabili a tale destinazione e indicare ad alta voce cosa si vuole e non si sceglie di accettare. Sono stati consigliati i punti iniziali, ma è necessario effettuare la chiamata finale. L'eccezione è i dati di KHI, in cui devono essere usati gli standard stabiliti da Microsoft. Vedere il poster di KHI allegato.

Per **ottenere** il gioco, USA le schede fornite al posto delle query di dati e di sistema di KHI. Se all'inizio del gioco non è stato disegnato un biglietto relativo a un dato aspetto, è possibile continuare a superarlo. Se c'è una scheda pertinente, rotolare il dado. Se è stato eseguito il rollforward sotto il numero indicato nella scheda, è stato completato. Se si rotola o si supera il numero indicato, è necessario disegnare un'altra carta dal mazzo. Se la scheda indica che due o più giocatori devono essere rotolati, devono essere tutti rivolti correttamente.

Per **mantenere** il gioco, esponete ad alta voce il piano di gestione dei servizi relativo a questo aspetto dell'ambiente Lync.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Guida alla rete di Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicatori di integrità chiave: la base per il mantenimento di server Lync integri](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia di qualità delle chiamate di Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

