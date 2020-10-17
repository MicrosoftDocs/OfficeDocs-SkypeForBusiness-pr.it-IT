---
title: 'Lync Server 2013: accesso ai dati di monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f763fe840a630ffd7ff2ee132d3251b009be6f34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505133"
---
# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Accesso ai dati di monitoraggio in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

I dati di monitoraggio sono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dettagli chiamata, e QoEMetrics per i dati QoE. Questi sono normali database, ed è possibile accedere ai dati in essi contenuti tramite tutti gli strumenti solitamente utilizzati per accedere e analizzare i dati di SQL Server.

Uno strumento da prendere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è rappresentato dai rapporti di monitoraggio di Lync Server. I report di monitoraggio sono un insieme di report standard pubblicati da Microsoft SQL Server Reporting Services. Questi rapporti, cui è possibile accedere utilizzando un browser, contengono informazioni sull'utilizzo, di diagnostica della chiamate e sulla qualità multimediale, tutte basate su record di registrazione dettagli chiamata e QoE (Quality of Experience) archiviati nei database CDR e QoE. I rapporti di monitoraggio vengono forniti con Lync Server 2013 e possono essere installati dalla distribuzione guidata di Lync Server dopo l'installazione di Lync Server e il monitoraggio è stato configurato.

Monitoring Reports richiede l'utilizzo di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente a SQL Server o dopo l'installazione di SQL Server.

Per ulteriori informazioni, vedere l'argomento relativo all' [installazione di Lync server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) nella Guida alla distribuzione di lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

