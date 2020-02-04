---
title: 'Lync Server 2013: monitorare la mobilità per le prestazioni'
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
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Monitoraggio della mobilità per le prestazioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-14_

Il servizio di mobilità di Lync Server (MCX) e l'API Web Unified Communications (UCWA) aumentano il carico nei server front-end e nei pool Front-end. I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione mobile è ridotta a icona, ad esempio dispositivi Android e Nokia che utilizzano Lync 2010 mobile, oltre a dispositivi Android e Apple che utilizzano Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminare la connessione al server quando l'applicazione per dispositivi mobili viene ridotta a icona. Man mano che l'uso della mobilità aumenta, è necessario monitorare le prestazioni della mobilità per determinare quando è necessario aumentare la propria capacità.

Diversi limiti influenzano le prestazioni di mobilità:

  - Memoria disponibile

  - Limite della coda di richiesta

  - Connessioni simultanee

  - Lunghezza coda di IIS

Altri limiti per i server che possono influenzare le prestazioni della mobilità sono un massimo di dodici accessi contemporanei, autenticazioni, rinnovi di sessioni e terminazioni. Non è necessario modificare questi massimali per la maggior parte delle distribuzioni.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Monitoraggio dei limiti della capacità di memoria del server in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Monitoraggio del servizio di mobilità e uso di UCWA in Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configurazione del servizio di mobilità per prestazioni elevate in Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Monitoraggio dei file di log della traccia delle richieste di IIS in Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Contatori delle prestazioni di mobilità in Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

