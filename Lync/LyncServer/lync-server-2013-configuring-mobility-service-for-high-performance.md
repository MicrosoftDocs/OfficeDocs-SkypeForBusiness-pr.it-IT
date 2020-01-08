---
title: 'Lync Server 2013: configurazione del servizio di mobilità per prestazioni elevate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Configurazione del servizio di mobilità per prestazioni elevate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Questo argomento si applica solo al servizio di mobilità di Lync Server 2013 (MCX) e non si applica a UCWA (Unified Communications Web API), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

Quando si installa il servizio di mobilità (MCX) in Internet Information Services (IIS) 7,5, il programma di installazione del servizio di mobilità configura alcune impostazioni di prestazioni nel server front-end. È consigliabile usare IIS 7,5 per la mobilità. Le impostazioni influenzano il numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.

Ecco le impostazioni delle prestazioni:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Impostazioni per MCX in IIS 7,5

1.  **MaxConcurrentThreadsPerCPU** è impostato su zero (0).

2.  **maxConcurrentRequestsPerCPU** è impostato su zero (0).

3.  Il modello di processo di ASP.NET è impostato su AutoConfig (solo per IIS 7,5).

4.  Il limite della coda HTTP. sys è impostato su 1.000 (per impostazione predefinita).

</div>

</div>

<span> </span>

</div>

</div>

</div>

