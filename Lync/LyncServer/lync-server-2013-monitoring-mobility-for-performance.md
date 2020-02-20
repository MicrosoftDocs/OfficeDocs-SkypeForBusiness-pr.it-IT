---
title: 'Lync Server 2013: monitoraggio della mobilità per le prestazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3532a6ebb8d8b095383f0737083d4b070e3aa882
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Monitoraggio della mobilità per le prestazioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-14_

Lync Server Mobility Service (MCX) e Unified Communications Web API (UCWA) aumentano il carico nei front end server e nei pool Front end. I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione per dispositivi mobili è ridotta a icona, come Android e Nokia su cui è in esecuzione Lync 2010 mobile, così come i dispositivi Android e Apple che eseguono Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminare la connessione al server quando l'applicazione per dispositivi mobili è ridotta a icona. Quando l'utilizzo della mobilità aumenta, è necessario monitorare le prestazioni dei dispositivi mobili per determinare quando è necessario aumentare la capacità.

Diversi limiti influenzano le prestazioni della mobilità:

  - Memoria disponibile

  - Limite coda richieste

  - Connessioni simultanee

  - Lunghezza coda IIS

Altri limiti nei server che possono influire sulle prestazioni della mobilità sono al massimo dodici accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni. Non è necessario modificare questi valori massimi per la maggior parte delle distribuzioni.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA in Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configurazione del servizio per dispositivi mobili per prestazioni elevate in Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Monitoraggio dei file di registro di traccia delle richieste IIS in Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Contatori delle prestazioni per dispositivi mobili in Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

