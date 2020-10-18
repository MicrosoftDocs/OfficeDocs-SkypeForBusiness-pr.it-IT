---
title: 'Lync Server 2013: Panoramica del monitoraggio'
description: 'Lync Server 2013: Panoramica del monitoraggio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f27d6aff71442c6193c220154af231481399ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577322"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a>Panoramica del monitoraggio in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

In Microsoft Lync Server 2013, il monitoraggio viene utilizzato per raccogliere informazioni sull'utilizzo e i dati QoE (Quality of Experience) sulle sessioni di comunicazione coinvolte dagli utenti. Il termine sessione è un termine generico riferito alla connessione di un utente a:

  - Conferenza

  - Una modalità di conferenza, ad esempio audio/video o di condivisione delle applicazioni

  - Un altro utente tramite una conversazione peer-to-peer come la messaggistica istantanea o una chiamata audio

<div>


> [!NOTE]  
> Lync Server 2013 tiene conto delle informazioni su ogni sessione: chi ha chiamato chi; quali endpoint sono stati utilizzati nella sessione; durata della sessione. Qual è la qualità percepita della sessione; E così via. Tuttavia, Lync Server non registra e archivia la chiamata vera e propria. Che include anche le sessioni di messaggistica istantanea: anche se Lync Server registra informazioni sulle sessioni di messaggistica istantanea, non gestisce un record di ogni messaggio istantaneo inviato durante la sessione.



</div>

Le informazioni dettagliate sulle chiamate raccolte da Lync Server possono essere utilizzate per qualsiasi numero di utilizzi, tra cui:

  - **Rendimento dell'investimento (ROI)**. Gli amministratori possono confrontare i dati di utilizzo raccolti da Monitoring Server a dati simili raccolti per il sistema di telefonia precedente per poter mostrare risparmi sui costi e contribuire a giustificare la distribuzione di Lync Server.

  - **Gestione dell'inventario dei dispositivi**. Le informazioni di gestione delle risorse consentono agli amministratori di individuare i dispositivi obsoleti ancora in uso che devono essere sostituiti, nonché identificare i dispositivi costosi che risultano inutilizzati.

  - Supporto tecnico. I dati sulla risoluzione dei problemi consentono ai tecnici dei servizi di supporto di stabilire le cause di una chiamata non riuscita, senza dover raccogliere log sul lato server o client. Tali informazioni possono essere facilmente accessibili e intese da personale di supporto che non dispone di una conoscenza approfondita tecnica di Microsoft Lync 2013 e Lync Server 2013.

  - **Risoluzione dei problemi di sistema**. Gli amministratori hanno la possibilità di rilevare i principali problemi che possono impedire agli utenti finali di eseguire attività di base come partecipare a una conferenza, eseguire una chiamata o inviare un messaggio istantaneo.

Oltre a queste informazioni sulla chiamata di base, il Monitoring Server fornisce anche un meccanismo che consente agli endpoint SIP (come Lync 2013) di fornire informazioni sulla risoluzione dei problemi a cui il server non avrebbe altrimenti accesso:

  - **Metriche che influiscono sulla qualità**. Queste metriche riguardano l'effettiva trasmissione della chiamata, ovvero offrono una sorta di registro di viaggio del percorso della chiamata in rete. Queste metriche, che includono dati come perdita di pacchetti, instabilità e tempi di round trip, offrono informazioni su cosa accade per la chiamata dal momento in cui lascia l'endpoint di partenza al momento in cui raggiunge l'endpoint di destinazione.

  - **Problemi segnalati all'utente finale**. Queste metriche includono notifiche di qualità scadente che Lync 2013 presenta agli utenti finali nei casi in cui sono troppo lontani da un microfono, che parlano troppo piano, che dispongono di una connessione di rete scadente o che stanno vivendo una qualità scadente perché un altro programma del computer utilizza le risorse disponibili.

  - **Informazioni sull'ambiente**. Queste metriche offrono dati dettagliati su aspetti che influiscono sulla qualità delle chiamate, come il tipo di microfono e altoparlanti in uso, se l'utente è connesso tramite VPN e se l'utente sta utilizzando una connessione wireless.

Al termine di ogni chiamata, gli endpoint conformi a SIP trasmettono automaticamente queste informazioni al Front End Server che ha inoltrato la chiamata. Non è necessario eseguire alcuna operazione per fare in modo che gli endpoint trasmettano tali informazioni, perché questo comportamento è incorporato nel protocollo SIP. Se si desidera raccogliere e archiviare tali informazioni, tuttavia, è necessario installare e abilitare il monitoraggio. In questo modo, le informazioni sulle chiamate vengono raccolte dagli agenti in esecuzione nel Front End Server e inoltrate a una coppia di database di SQL Server.

Si noti che il processo di installazione e configurazione del monitoraggio è stato semplificato in Lync Server 2013. Nelle versioni precedenti del software, il monitoraggio richiedeva un ruolo di Monitoring Server separato, che in genere indicava un computer separato accantonato per l'utilizzo come Monitoring Server. In Lync Server 2013, tuttavia, il ruolo Monitoring Server è stato eliminato. Al contrario, il servizio di monitoraggio, sotto forma di "agenti di raccolta dati unificati", è stato collocato in tutti i Front End Server. Sono presenti almeno due vantaggi principali. Collocazione del servizio di monitoraggio:

  - Consente di ridurre il numero di ruoli del server necessari per l'implementazione di Lync Server 2013. La rimozione del ruolo Monitoring Server contribuisce anche a ridurre i costi, eliminando la necessità di gestire server dedicati per il monitoraggio.

  - Riduce la complessità dell'installazione e dell'amministrazione di Lync Server 2013. La collocazione dei servizi di monitoraggio in ogni Front End Server significa che non è più necessario installare, configurare e gestire il ruolo Monitoring Server.

Per ulteriori informazioni, vedere l'argomento [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) nella Guida alla distribuzione di lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

