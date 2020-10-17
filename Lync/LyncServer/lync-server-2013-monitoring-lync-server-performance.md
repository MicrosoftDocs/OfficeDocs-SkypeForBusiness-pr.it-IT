---
title: 'Lync Server 2013: monitoraggio delle prestazioni di Lync Server'
description: 'Lync Server 2013: monitoraggio delle prestazioni di Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe63a881c9db105fc36a1ccd0b0fdc15086a36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548102"
---
# <a name="monitoring-lync-server-2013-performance"></a>Monitoraggio delle prestazioni di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-15_

Le prestazioni di Lync Server 2013 sono intaccate da vari fattori, quali profili utente, architettura del sistema, software, componenti hardware, punti di integrazione di terze parti, ad esempio gateway e apparecchiature telefoniche, connettività e prestazioni di rete, configurazione del servizio Windows Active Directory e prestazioni oltre alla funzionalità del sistema operativo Windows.

Il fulcro delle prestazioni delle distribuzioni di Lync Server 2013 è il software e l'hardware del server su cui è implementato. Ad esempio, un server front-end deve disporre di risorse hardware sufficienti per gestire il carico utente previsto (di breve durata). Se è necessario un server front-end per fornire servizi a 10000 utenti, un server adeguatamente configurato deve soddisfare i requisiti di carico previsti per contribuire in ultima analisi a garantire il miglior utilizzo possibile dell'utente finale.

Il monitoraggio delle prestazioni del server è pertanto estremamente importante per valutare se l'infrastruttura server implementata dispone di risorse hardware adeguate per i requisiti di carico di picco giornalieri. Il monitoraggio delle prestazioni del server consente di identificare i colli di bottiglia del sistema che consentono agli amministratori di applicare azioni correttive prima che l'esperienza dell'utente finale venga interessa. I dati relativi alle prestazioni devono essere utilizzati per la pianificazione della capacità a lungo termine.

Anche se le informazioni dettagliate su tutti gli oggetti e i contatori di prestazioni da osservare sono collegate a nel [monitoraggio di Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), alcuni contatori delle prestazioni che è necessario seguire possono fornire agli amministratori una visualizzazione rapida delle prestazioni del sistema:

  - Per monitorare l'integrità complessiva del sistema del server front-end, un buon punto di partenza consiste nel controllare il processore \\ % del tempo processore. Il valore deve essere sempre inferiore al 80 percento.

  - Per tenere presenti le prestazioni dell'istanza del software di database di SQL Server back-end utilizzata dal pool Front End, monitorare i contatori delle prestazioni seguenti:
    
    LC: USrv – 00 – DBStore \\ USrv – 002 – latenza coda (msec)
    
    LC: USrv – 00 – DBStore \\ USrv – 0 04 – latenza SPROC (msec)
    
    Il server integro allo stato stazionario deve mostrare \< 100 valori di latenza MS. Il meccanismo di limitazione si impegnerà quando la latenza raggiunge i 12 secondi, il che significa che il server front-end avvia le richieste di limitazione al back-end. Questo fa sì che i client comincino a ricevere un messaggio di errore di 503 Server troppo occupato.

  - Per tenere conto del tempo di elaborazione nel server front-end, monitorare il seguente contatore:
    
    LC: SIP-07-Load Management \\ SIP-000-media del tempo di attesa per i messaggi in arrivo
    
    Si tratta di un altro meccanismo di limitazione nei server front-end, che questa volta inizia quando il tempo di elaborazione sul front-end è elevato. Se il tempo medio di elaborazione è superiore a sei secondi, il server entra in modalità di limitazione e consente solo una transazione in sospeso per ogni connessione client.

  - Per tenere conto dei problemi di memoria nel server back-end SQL, monitorare il seguente contatore:
    
    Aspettativa di vita di SQL Server buffer Manager \\ Page
    
    Un valore basso, inferiore a 3600 secondi (insieme alle Scritture a latenza elevata/sec e alle pagine del checkpoint/sec) indica la pressione della memoria.

<div>

## <a name="additional-counters-to-view"></a>Contatori aggiuntivi da visualizzare

Esistono diversi contatori chiave che rappresentano buoni indicatori di integrità generale dal front end server. Non si tratta di un elenco completo e non si intende identificare la causa principale. Questi contatori consentono di eseguire un rapido controllo sull'integrità del server. Si consiglia di verificare questi contatori su ciascuno dei server del pool. È importante comprendere quali sono i valori del contatore quando il server è integro. È necessaria una linea di base per capire cosa è cambiato quando l'esperienza utente è Degraded.

Il server front-end può indicare problemi che possono essere causati da colli di bottiglia in altre parti del sistema. Questo significa che è il punto di partenza migliore per esaminare l'integrità generale del sistema.

Di seguito sono riportati due contatori aggiuntivi da esaminare:

LC: USrv-00-DBStore \\ USrv-002-latenza della coda (msec)

LC: USrv-00-DBStore \\ USrv-004-latenza SPROC (msec)

Il contatore latenza coda rappresenta l'ora in cui una richiesta è stata spesa per la coda fino al back-end e la latenza di SPROC rappresenta il tempo impiegato per il back-end per elaborare la richiesta. Se, per qualsiasi motivo, il disco, la memoria, la rete e il processore sul back-end sono in difficoltà, il contatore latenza coda sarà elevato.

Può anche essere elevato se la latenza di rete è elevata tra il front-end e il back-end. Che cos'è la latenza della coda accettabile?

A 12 secondi, i Front End Server avviano le richieste di limitazione ai server back-end. Questo significa che i server avviano la restituzione del server troppo occupato – 503 errori ai client. Un server integro deve avere una latenza di coda di DBStore inferiore a 100 msec allo stato stazionario, ma nei periodi in cui il server è appena online e gli utenti eseguono tutti i log in contemporaneamente, tale contatore può essere molto elevato e potrebbe anche essere visualizzato in più secondi.

È possibile che si disponga di una configurazione con bilanciamento del carico, in cui si dispone di un pool distribuito con più server front-end e di un bilanciamento del carico configurato per il "numero minimo di connessioni". In questo caso, se un server front-end viene riavviato, tutti gli utenti che tentano di riconnettersi verranno indirizzati al server riavviato, in quanto il server avrà meno connessioni rispetto agli altri membri del pool. Durante questo periodo, il server front-end corrispondente può essere sovraccaricato mentre gli altri membri del pool non lo sono.

Si consiglia di eseguire la manutenzione durante le ore non consentite per ridurre le prestazioni influenzate poiché gli utenti non saranno tutti concorrenti per la connessione al server contemporaneamente.

Se i due contatori delle prestazioni precedenti sono alti, il collo di bottiglia più probabile è il server back-end SQL. Di seguito sono riportati i componenti seguenti da confermare:

  - La CPU di SQL Server è troppo alta? Ad esempio, è maggiore di 80%?

  - La latenza del disco è elevata?

In un ambiente ideale, si dispone di RAM sufficiente per avere entrambi i database RTC e RTCDYN in memoria. L'unico motivo per il quale il server dovrebbe accedere al disco è quindi scrivere nei file di registro e incasso nei database. I test hanno evidenziato che 12 GB di RAM sono sufficienti per le distribuzioni di 100.000 utenti. Si presuppone che la dimensione dei database RTC e RTCDYN sia inferiore a 12 GB. Se i database sono più grandi, potrebbe essere necessaria una memoria aggiuntiva.

È possibile determinare se SQL Server richiede ulteriore RAM rivedendo il contatore delle prestazioni di durata della pagina di gestione buffer di SQL Server. Un valore inferiore a 3.600 indica la pressione della memoria. Se si dispone di una quantità di memoria sufficiente perché SQL Server deve essere scritto nel database, è inoltre consigliabile leggere poche letture nell'unità di database.

Esiste un ulteriore meccanismo di limitazione in un server front end di Lync Server 2013 che inizia se il tempo di elaborazione del server è elevato. La limitazione della latenza di DBStore è abilitata solo se la latenza del server SQL è alta. Un esempio in cui tale limitazione è abilitata è se il server front-end è associato alla CPU.

Se il tempo medio **di elaborazione (LC: SIP-07-Load Management \\ SIP-000-media per i messaggi in arrivo)** sul server supera i sei secondi, il server entra in modalità di limitazione e fornisce solo agli utenti una transazione in sospeso per ogni connessione client. Dopo che il tempo di elaborazione è stato impostato su tre secondi, il server non è più in modalità di limitazione e fornisce agli utenti un massimo di 20 transazioni in sospeso per ogni connessione client. Ogni volta che il numero di transazioni su una connessione specifica supera la soglia sopra riportata, la connessione viene contrassegnata come controllata dal flusso. Il risultato è che il server non invia alcuna ricevuta su di esso e il contatore delle ** \\ connessioni controllate dal flusso LC: SIP-01-Peers** viene incrementato. Se una connessione rimane in uno stato controllato dal flusso per più di un minuto, il server la chiude. Lo fa in modo pigramente. Quando ha la possibilità di controllare la connessione, determina se è stata limitata troppo a lungo e la chiude se ha più di un minuto.

Questi sono i due meccanismi di limitazione ed è presente un solo contatore delle prestazioni che riepiloga la limitazione dell'esecuzione del server.

**LC: SIP-04-Responses \\ SIP-053-Local 503 risposte/sec**

  - Il termine "local" nel contatore precedente si riferisce a risposte generate localmente.

  - Il codice 503 corrisponde al server non disponibile, in cui non è possibile visualizzare i codici 503 in un server integro. Durante il periodo in cui un server viene appena portato online, è possibile che vengano visualizzati alcuni codici 503. Quando tutti gli utenti eseguono l'accesso e il server torna a uno stato stabile, non devono essere presenti ulteriori codici 503.

**LC: SIP-04-Responses \\ SIP-074-Local 504 risposte/sec**

Questo contatore delle prestazioni indica problemi di connettività con altri server e può indicare errori di connessione o ritardi nella connessione. Se si stanno visualizzando 504 errori, è necessario controllare il seguente contatore delle prestazioni.

**LC: SIP-01-peer \\ SIP-017-invia in sospeso**

Questo contatore indica il numero di richieste e risposte in uscita in coda. Se il contatore è alto, è probabile che il problema non sia sul server locale. Si noti che questo contatore può essere elevato se sono presenti problemi di latenza della rete. Potrebbe anche indicare problemi relativi alla scheda di rete locale, ma è più probabile che sia causata da un problema su un server remoto. È probabile che questo contatore sia elevato su un server Director quando il pool in cui si sta tentando di comunicare è sovraccarico. La chiave con questo contatore consiste nell'esaminare le istanze, non solo il totale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

