---
title: 'Lync Server 2013: configurazione del servizio per dispositivi mobili per prestazioni elevate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35d45c1b437c04e96885f098df6026650d61768
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Configurazione del servizio per dispositivi mobili per prestazioni elevate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Questo argomento si applica solo a Lync Server 2013 Mobility Service (MCX) e non si applica a Unified Communications Web API (UCWA), come recapitato negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

Quando si installa il servizio per dispositivi mobili (MCX) su Internet Information Services (IIS) 7,5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel front end server. È consigliabile utilizzare IIS 7.5 per la mobilità. Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.

Di seguito sono conformate le impostazioni delle prestazioni:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Impostazioni per MCX in IIS 7,5

1.  Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).

2.  Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).

3.  Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).

4.  Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.

</div>

</div>

<span> </span>

</div>

</div>

</div>

