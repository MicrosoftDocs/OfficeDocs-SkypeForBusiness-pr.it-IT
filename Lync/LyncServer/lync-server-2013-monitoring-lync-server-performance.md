---
title: 'Lync Server 2013: monitoraggio delle prestazioni di Lync Server'
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
ms.openlocfilehash: f7859ea116e4ae63a5777e816c37893f11cf1c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Monitoraggio delle prestazioni di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-15_

Le prestazioni di Lync Server 2013 sono influenzate da diversi fattori, come i profili utente, l'architettura di sistema, il software, i componenti hardware, i punti di integrazione di terze parti, come gateway e dispositivi di telefonia, connettività di rete e prestazioni, Windows Configurazione e prestazioni di servizio Active Directory oltre alle funzionalità del sistema operativo Windows.

Il nucleo delle prestazioni delle distribuzioni di Lync Server 2013 è il software server e l'hardware su cui è implementato. Ad esempio, un server front-end deve disporre di risorse hardware sufficienti per gestire il carico di utenti previsto (a breve termine). Se è necessario disporre di un server front-end per offrire servizi agli utenti di 10000, un server adeguatamente configurato deve soddisfare i requisiti di carico previsti per garantire la migliore esperienza possibile per gli utenti finali.

Il monitoraggio delle prestazioni del server è quindi estremamente importante per valutare se l'infrastruttura del server implementata dispone di risorse hardware adatte per i requisiti giornalieri per il caricamento di picco. Il monitoraggio delle prestazioni del server consente di identificare i colli di bottiglia di sistema che consentono agli amministratori di applicare azioni correttive prima che l'esperienza utente finale sia interessata. I dati sulle prestazioni devono essere usati per la pianificazione della capacità a lungo termine.

Mentre le informazioni dettagliate su tutti gli oggetti prestazioni e i contatori da rispettare sono collegate al [monitoraggio di Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), alcuni contatori delle prestazioni da seguire possono offrire agli amministratori una rapida visualizzazione delle prestazioni del sistema:

  - Per tenere traccia dell'integrità complessiva del sistema del server front-end, un buon punto di partenza consiste\\nel controllare il tempo processore% Processor. Il valore deve essere sempre inferiore a 80%.

  - Per tenere traccia delle prestazioni dell'istanza del software di database di SQL Server back-end utilizzata dal pool Front-End, monitorare i contatori delle prestazioni seguenti:
    
    LC: USrv-00-DBStore\\USrv-002-latenza coda (msec)
    
    LC: USrv-00-DBStore\\USrv-0 04-latenza SPROC (msec)
    
    Il server integro in stato stabile dovrebbe \<visualizzare i valori di latenza di 100 ms. Il meccanismo di limitazione si impegnerà quando la latenza raggiunge i 12 secondi, quindi il server front-end avvia richieste di limitazione al back-end. In questo modo i client inizieranno a ricevere un messaggio di errore troppo occupato per il server 503.

  - Per tenere traccia del tempo di elaborazione nel server front-end, monitorare il contatore seguente:
    
    LC: SIP-07-Load Management\\SIP-000-tempo di permanenza medio per i messaggi in arrivo
    
    Si tratta di un altro meccanismo di limitazione dei server front-end, questa volta a partire dal momento in cui il tempo di elaborazione nella parte anteriore è elevato. Se il tempo di elaborazione medio è superiore a sei secondi, il server entra in modalità di limitazione e consente solo una transazione in sospeso per ogni connessione client.

  - Per tenere traccia dei problemi di memoria in SQL back end server, monitorare il contatore seguente:
    
    Speranza di vita della\\pagina SQL Server buffer Manager
    
    Un valore basso, inferiore a 3600 secondi (insieme alle Scritture ad alta latenza/sec e alle pagine del checkpoint/sec) indica la pressione della memoria.

<div>

## <a name="additional-counters-to-view"></a>Altri contatori da visualizzare

Esistono diversi contatori chiave che rappresentano buoni indicatori dell'integrità complessiva del server front-end. Questo non è un elenco completo e non è concepito per identificare la causa radice. Questi contatori consentiranno di eseguire un rapido controllo sull'integrità del server. È consigliabile verificare questi contatori in ognuno dei server del pool. È importante comprendere i valori di questi contatori quando il server è integro. È necessaria una previsione per capire cosa è cambiato quando l'esperienza utente è degradata.

Il server front-end può indicare problemi che possono essere causati da colli di bottiglia altrove nel sistema. Questo significa che è la posizione migliore per iniziare quando si esamina l'integrità complessiva del sistema.

Di seguito sono riportati due contatori aggiuntivi da esaminare:

LC: USrv-00-DBStore\\USrv-002-latenza coda (msec)

LC: USrv-00-DBStore\\USrv-004-latenza SPROC (msec)

Il contatore della latenza delle code rappresenta l'ora in cui una richiesta è stata trascorsa nella coda al back-end e la latenza SPROC rappresenta il tempo impiegato per il back-end per elaborare la richiesta. Se, per qualsiasi motivo, il disco, la memoria, la rete e il processore nel back-end sono in difficoltà, il contatore della latenza della coda sarà elevato.

Può anche essere elevato se la latenza di rete è elevata tra il front-end e il back-end. Cos'è la latenza della coda accettabile?

A 12 secondi, i server front-end avviano richieste di limitazione ai server back-end. Questo significa che i server avviano la restituzione del server troppo occupato-503 errori ai client. Un server integro dovrebbe avere latenze della coda di DBStore con meno di 100 msec a stato costante, ma durante i periodi in cui il server è appena online e gli utenti sono tutti connessi contemporaneamente, tale contatore può essere molto elevato e può anche essere visualizzato in più secondi.

Potrebbe essere installata una configurazione con bilanciamento del carico, in cui è installato un pool con più server front-end e un bilanciamento del carico configurato per "numero minimo di connessioni". In questo caso, se viene riavviato un server front-end, tutti gli utenti che tentano di riconnettersi verranno puntati sul server riavviato, perché il server avrà meno connessioni rispetto agli altri membri del pool. Durante questo periodo, il server front-end corrispondente può essere sovraccaricato mentre gli altri membri del pool non lo sono.

Ti consigliamo di eseguire la manutenzione durante le ore lavorative per ridurre l'effetto sulle prestazioni perché gli utenti non saranno tutti concorrenti per la connessione al server contemporaneamente.

Se i due contatori delle prestazioni precedenti sono elevati, il collo di bottiglia più probabile è il server back-end SQL. I componenti successivi da confermare sono i seguenti:

  - La CPU di SQL Server è troppo elevata? Ad esempio, è maggiore di 80%?

  - La latenza del disco è elevata?

In un mondo ideale hai abbastanza RAM per avere sia i database RTC che RTCDYN in memoria. Quindi, l'unico motivo per cui il server accede al disco è la scrittura nei file di log e lo svuotamento dei database. I test hanno dimostrato che 12 GB di RAM sono sufficienti per le distribuzioni degli utenti di 100.000. Si presuppone che la dimensione dei database RTC e RTCDYN sia inferiore a 12 GB. Se i database sono più grandi, potrebbe essere necessario ulteriore memoria.

Per determinare se SQL Server richiede RAM aggiuntiva, è possibile visualizzare il contatore delle prestazioni di SQL Server buffer Manager per la durata della pagina. Un valore minore di 3.600 indica la pressione della memoria. Se si dispone di memoria sufficiente perché SQL Server deve essere scritto nel database, è anche possibile che non vengano visualizzate poche letture nell'unità di database.

Esiste un meccanismo di limitazione aggiuntivo in un server front-end di Lync Server 2013 che viene avviato se il tempo di elaborazione del server è elevato. La limitazione della latenza di DBStore è abilitata solo se la latenza di SQL Server è elevata. Un esempio in cui tale limitazione è abilitata è se il server front-end è associato alla CPU.

Se il tempo medio **di elaborazione (LC: SIP-07-Load\\Management SIP-000-media del tempo di attesa per i messaggi in arrivo)** sul server supera i sei secondi, il server entra in modalità di limitazione e dà solo agli utenti una transazione in sospeso per ogni connessione client. Una volta che il tempo di elaborazione scende a tre secondi, il server esce dalla modalità di limitazione e offre agli utenti fino a 20 transazioni in sospeso per connessione client. Ogni volta che il numero di transazioni in una connessione specifica supera la soglia precedente, la connessione viene contrassegnata come flusso controllato. Il risultato è che il server non pubblica alcuna ricevuta su di essa e viene incrementato il contatore delle **connessioni controllate di\\flusso LC: SIP-01-peer** . Se una connessione rimane in uno stato controllato dal flusso per più di un minuto, il server la chiude. Lo fa pigramente. Quando ha la possibilità di verificare la connessione, determina se è stata strozzata troppo a lungo e la chiude se ha più di un minuto.

Questi sono i due meccanismi di limitazione e c'è un solo contatore delle prestazioni che riepiloga le operazioni di limitazione del server.

**LC: SIP-04-risposte\\sip-053-risposte 503 locali/sec**

  - Il termine "local" nel contatore precedente fa riferimento alle risposte generate localmente.

  - Il codice 503 corrisponde al server non disponibile, in cui non è possibile visualizzare i codici di 503 in un server integro. Durante il periodo dopo che un server è stato appena portato online, potresti vedere alcuni codici di 503. Dopo che tutti gli utenti hanno eseguito l'accesso e il server ritorna a uno stato stabile, non devono essere presenti codici 503 aggiuntivi.

**LC: SIP-04-risposte\\sip-074-risposte 504 locali/sec**

Questo contatore delle prestazioni indica i problemi di connettività con altri server e può indicare errori di connessione o ritardi nella connessione. Se vengono visualizzati errori di 504, il contatore delle prestazioni seguente deve essere controllato.

**LC: SIP-01-peer\\SIP-017-invia in sospeso**

Questo contatore indica il numero di richieste e risposte in coda in uscita. Se questo contatore è elevato, il problema non è probabilmente nel server locale. Tieni presente che questo contatore può essere elevato se sono presenti problemi di latenza della rete. Potrebbe anche indicare i problemi con la scheda di rete locale, ma è più probabile causata da un problema in un server remoto. Questo contatore sarebbe probabilmente elevato in un server Director quando il pool con cui sta provando a comunicare è in overload. La chiave con questo contatore consiste nell'esaminare le istanze, non solo nel totale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

