---
title: 'Lync Server 2013: Panoramica del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Panoramica del monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

In Microsoft Lync Server 2013 viene usato il monitoraggio per raccogliere le informazioni sull'utilizzo e i dati di qualità dell'esperienza (QoE) sulle sessioni di comunicazione coinvolte dagli utenti. Una sessione è un termine generico che copre la connessione di un utente a:

  - Conferenza

  - Modalità di conferenza (ad esempio condivisione audio/video o applicazioni)

  - Un altro utente tramite una conversazione peer-to-peer, ad esempio la messaggistica istantanea o una chiamata audio

<div>


> [!NOTE]  
> Lync Server 2013 tiene traccia delle informazioni relative a ogni sessione: chi ha chiamato chi; quali endpoint sono stati usati nella sessione; durata della sessione Qual è stata la qualità percepita della sessione; E così via. Tuttavia, Lync Server non registra e archivia la chiamata effettiva stessa. Che include anche le sessioni di messaggistica istantanea: Sebbene Lync Server registri informazioni sulle sessioni di messaggistica istantanea, non mantiene un record di ogni messaggio istantaneo inviato durante la sessione.



</div>

Le informazioni dettagliate sulle chiamate raccolte da Lync Server possono essere usate per qualsiasi numero di usi, tra cui:

  - **Return on Investment (ROI)**. Gli amministratori possono confrontare i dati di utilizzo raccolti da Monitoring Server in base a dati simili raccolti per il sistema di telefonia precedente per mostrare il risparmio dei costi e giustificare la distribuzione di Lync Server.

  - **Gestione inventario dispositivi**. Le informazioni sulla gestione degli asset consentono agli amministratori di identificare i vecchi dispositivi ancora in uso che devono essere sostituiti, nonché di identificare i dispositivi costosi che non sembrano essere sempre usati.

  - Help desk. La risoluzione dei problemi dei dati consente agli ingegneri del supporto di determinare il motivo per cui la chiamata di un utente non è riuscita e di farlo senza dover raccogliere log lato server o client. Queste informazioni possono essere facilmente accessibili e comprese dal personale di supporto che non ha una profonda conoscenza tecnica di Microsoft Lync 2013 e Lync Server 2013.

  - **Risoluzione dei problemi di sistema**. Consente agli amministratori di rilevare problemi importanti che potrebbero impedire agli utenti finali di eseguire attività di base, ad esempio partecipare a una conferenza, stabilire una chiamata o inviare un messaggio istantaneo.

Oltre a queste informazioni di base sulle chiamate, il server di monitoraggio offre anche un meccanismo che consente agli endpoint SIP (ad esempio Lync 2013) di fornire informazioni di risoluzione dei problemi a cui il server non avrebbe altrimenti accesso:

  - **Metriche multimediali che incidono sulla qualità**. Queste metriche trattano la trasmissione effettiva della chiamata stessa; in altre cose, essi includono una sorta di log di viaggio durante i viaggi di chiamata attraverso la rete. Queste metriche (che includono elementi come perdita di pacchetti, jitter e tempi di andata e ritorno) offrono informazioni su ciò che è accaduto alla chiamata dal momento in cui ha lasciato l'endpoint fino al momento in cui è arrivato all'endpoint dell'altra persona.

  - **Problemi segnalati all'utente finale**. Queste metriche includono notifiche di qualità scadente che Lync 2013 presenta agli utenti finali nei casi in cui siano troppo lontani da un microfono, che parli troppo dolcemente, che abbiano una connessione di rete scadente o che abbiano una qualità scadente perché un altro programma nel computer è utilizzo delle risorse disponibili.

  - **Informazioni sull'ambiente**. Queste metriche denominano fattori di qualità come il tipo di microfono e gli altoparlanti usati, se l'utente è connesso tramite una connessione VPN e se l'utente si trova in una connessione wireless.

Alla fine di ogni chiamata, gli endpoint conformi a SIP trasmettono automaticamente queste informazioni al server front-end che facilita la chiamata. Non è necessario eseguire alcuna operazione per ottenere gli endpoint per trasmettere tali informazioni; Questo comportamento è incorporato nel protocollo SIP. Tuttavia, se si vogliono raccogliere e archiviare tali informazioni, è necessario installare e abilitare il monitoraggio. Se si installa e si Abilita il monitoraggio, le informazioni sulle chiamate vengono raccolte dagli agenti in uso nel server front-end e inoltrate a una coppia di database di SQL Server.

Si noti che il processo di installazione e configurazione del monitoraggio è stato semplificato in Lync Server 2013. Nelle versioni precedenti del software il monitoraggio richiedeva un ruolo di server di monitoraggio distinto, che in genere significava un computer separato da accantonare per l'uso come server di monitoraggio. In Lync Server 2013, tuttavia, il ruolo del server di monitoraggio è stato eliminato. Il servizio di monitoraggio, sotto forma di "agenti di raccolta dati unificati", è invece stato collocato in tutti i server front-end. Questo ha almeno due vantaggi principali. Collocazione del servizio di monitoraggio:

  - Riduce il numero di ruoli del server necessari per l'implementazione di Lync Server 2013. Il decremento del ruolo del server di monitoraggio consente inoltre di ridurre i costi eliminando la necessità di gestire server dedicati per il monitoraggio.

  - Riduce la complessità della configurazione e dell'amministrazione di Lync Server 2013. Collocando i servizi di monitoraggio in ogni server front-end non è più necessario installare, configurare e gestire il ruolo del server di monitoraggio.

Per altre informazioni, vedere l'argomento [distribuzione di monitoraggio in Lync server 2013](lync-server-2013-deploying-monitoring.md) nella Guida alla distribuzione di lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

