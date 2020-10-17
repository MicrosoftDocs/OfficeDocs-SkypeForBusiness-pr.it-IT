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
# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="88b3a-102">Accesso ai dati di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b3a-102">Accessing monitoring data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b3a-103">_**Ultimo argomento modificato:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="88b3a-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="88b3a-p101">I dati di monitoraggio sono archiviati in una coppia di database di SQL Server: LcsCdr per i dati di registrazione dettagli chiamata, e QoEMetrics per i dati QoE. Questi sono normali database, ed è possibile accedere ai dati in essi contenuti tramite tutti gli strumenti solitamente utilizzati per accedere e analizzare i dati di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="88b3a-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="88b3a-106">Uno strumento da prendere in considerazione per l'accesso e l'analisi dei dati di monitoraggio è rappresentato dai rapporti di monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88b3a-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="88b3a-107">I report di monitoraggio sono un insieme di report standard pubblicati da Microsoft SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="88b3a-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="88b3a-108">Questi rapporti, cui è possibile accedere utilizzando un browser, contengono informazioni sull'utilizzo, di diagnostica della chiamate e sulla qualità multimediale, tutte basate su record di registrazione dettagli chiamata e QoE (Quality of Experience) archiviati nei database CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="88b3a-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="88b3a-109">I rapporti di monitoraggio vengono forniti con Lync Server 2013 e possono essere installati dalla distribuzione guidata di Lync Server dopo l'installazione di Lync Server e il monitoraggio è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="88b3a-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="88b3a-p103">Monitoring Reports richiede l'utilizzo di SQL Server Reporting Service. SQL Server Reporting Service può essere installato contemporaneamente a SQL Server o dopo l'installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="88b3a-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="88b3a-112">Per ulteriori informazioni, vedere l'argomento relativo all' [installazione di Lync server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) nella Guida alla distribuzione di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88b3a-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

