---
title: 'Lync Server 2013: monitoraggio dei limiti della capacità di memoria del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Monitoraggio dei limiti della capacità di memoria del server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> Le informazioni contenute in questo argomento che fanno riferimento alla pianificazione della capacità riguardano solo i client mobili Lync 2010 e il servizio mobilità (MCX). La pianificazione della capacità per Unified Communications Web API (UCWA), usata dai client per dispositivi mobili Lync 2013, è fornita da Lync Server 2013, strumento di pianificazione.



</div>

Due contatori delle prestazioni della mobilità possono aiutare a determinare l'uso corrente e ad aiutarti a pianificare la capacità per il servizio di mobilità di Lync Server 2013 (MCX), nonché a monitorare l'uso della memoria per UCWA. Per UCWA, la categoria contatore è **ls: Web – UCWA**. Per il servizio mobilità (MCX), i contatori sono sotto la categoria **ls: Web-servizio di comunicazione mobile**. I contatori da monitorare sono:

  - **Conteggio delle sessioni attualmente attivo con gli abbonamenti alla presenza attiva**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio di mobilità (MCX) con abbonamenti alla presenza attiva (numero di utenti di dispositivi mobili sempre connessi)

  - **Conteggio delle sessioni attualmente attivo**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio mobilità

Se la differenza tra il **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva** e il conteggio delle **sessioni** attive è ridotta nel tempo, significa che la maggior parte degli utenti di dispositivi mobili ha un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per MCX). I dispositivi UCWA sempre connessi includono dispositivi Apple e Android con client mobili Lync 2013. Se il **conteggio delle sessioni attualmente attivo** è molto più elevato del **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva**, questo indica che più utenti usano un dispositivo endpoint in background, ad esempio un dispositivo iOS di Apple o un Windows Phone in MCX. Windows Phone è l'unico client per dispositivi mobili Lync 2013 che verrà registrato come questo.

È necessario impostare un limite per il **conteggio delle sessioni attivo con gli abbonamenti alla presenza attiva** e i contatori delle prestazioni **attualmente attivi** , in base ai risultati previsti per l'uso, alla pianificazione della capacità e al monitoraggio continuo del servizio di mobilità e di altri contatori del server front-end. I limiti impostati devono consentire di valutare la capacità del server e generare avvisi quando viene superata la capacità.

Per determinare i limiti appropriati, è prima di tutto necessario determinare la quantità di memoria disponibile nel server front-end per il servizio di mobilità. Monitorare i contatori per determinare quando è necessario pianificare la capacità aggiuntiva, in base alla formula seguente:

Memoria totale usata dal servizio di mobilità di MCX (MB) = 164 + (400 + 134)/ \* 1024 **numero di sessione attualmente attivo con abbonamenti alla presenza attiva** + 400/1024 \* (numero di**sessione attivo corrente** - **conteggio sessioni attivo con abbonamenti alla presenza attiva**)

<div>


> [!IMPORTANT]  
> Il calcolatore di capacità di Microsoft Lync Server 2010 è un foglio di calcolo precompilato con tutte le formule che consentono a un planner di determinare quali saranno i requisiti per i server, tra cui CPU, memoria e disco rigido. È possibile scaricare il foglio di calcolo e un documento associato in:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

Il server front-end richiede abbastanza memoria disponibile per supportare il servizio di mobilità in situazioni di failover. È possibile monitorare la memoria disponibile corrente sul server front-end usando il contatore **memoria\\disponibile MBytes** oppure usando l'equazione menzionata in precedenza per pianificare la quantità di memoria che si prevede venga usata dal servizio di mobilità.

Se la quantità di memoria disponibile nel server front-end è inferiore a 1.500 MB quando si prevede il numero previsto di utenti della mobilità, è necessario aggiungere altro hardware per supportare il servizio di mobilità. Per altri dettagli, vedere [monitoraggio della mobilità per le prestazioni in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) nella documentazione delle operazioni.

<div>

## <a name="see-also"></a>Vedere anche


[Monitoraggio della mobilità per le prestazioni in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

