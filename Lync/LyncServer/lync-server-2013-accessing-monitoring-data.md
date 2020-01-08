---
title: 'Lync Server 2013: accesso ai dati di monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f6033c927a0d0c27b139d889c5fb0b0d9d4825
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Accesso ai dati di monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

I dati di monitoraggio vengono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dei dettagli delle chiamate e QoEMetrics per la qualità dei dati dell'esperienza. Non c'è niente di speciale in questi due database; Ciò significa che è possibile accedere ai dati archiviati in tali database con uno degli strumenti usati in genere per l'accesso e l'analisi dei dati di SQL Server.

Uno strumento da tenere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è i report di monitoraggio di Lync Server. I report di monitoraggio sono un set di report standard pubblicati da Microsoft SQL Server Reporting Service. Questi report, accessibili tramite un Web browser, consentono l'utilizzo, le informazioni di diagnostica delle chiamate e le informazioni sulla qualità dei contenuti multimediali, tutte basate sui record di registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) archiviati nei database CDR e QoE. I report di monitoraggio vengono forniti con Lync Server 2013 e possono essere installati dalla distribuzione guidata di Lync Server dopo l'installazione di Lync Server e il monitoraggio è stato configurato.

Come notato, il monitoraggio dei report richiede l'uso di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente all'installazione di SQL Server o può essere installato in qualsiasi momento dopo l'installazione di SQL Server.

Per altre informazioni, vedere l'argomento [installazione dei report di monitoraggio di Lync server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) nella Guida alla distribuzione di lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

