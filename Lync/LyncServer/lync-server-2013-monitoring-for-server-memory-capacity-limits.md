---
title: 'Lync Server 2013: monitoraggio dei limiti di capacità della memoria del server'
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
ms.openlocfilehash: 46580950c30326bb9852abc5ecb2a165398b3587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> Le informazioni contenute in questo argomento che si riferiscono alla pianificazione della capacità riguardano solo i client mobili Lync 2010 e il servizio di mobilità (MCX). La pianificazione della capacità per Unified Communications Web API (UCWA), utilizzata dai client per dispositivi mobili Lync 2013, viene fornita da Lync Server 2013, strumento di pianificazione.



</div>

Due contatori delle prestazioni per dispositivi mobili consentono di determinare l'utilizzo corrente e di pianificare la capacità per il servizio per dispositivi mobili di Lync Server 2013 (MCX), nonché di monitorare l'utilizzo della memoria per UCWA. Per UCWA, la categoria del contatore è **ls: Web – UCWA**. Per il servizio per dispositivi mobili (MCX), i contatori sono sotto la categoria **ls: Web-Mobile Communication Service**. I contatori da monitorare sono:

  - **Conteggio delle sessioni attivo con gli abbonamenti alla presenza attiva**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili (MCX) che dispongono di sottoscrizioni di presenza attiva (numero di utenti mobili sempre connessi)

  - **Conteggio delle sessioni attivo**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili

Se la differenza tra il **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva** e il numero di **sessioni** attivo è di dimensioni ridotte nel tempo, significa che la maggior parte degli utenti di dispositivi mobili ha un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per MCX). I dispositivi sempre connessi di UCWA includono i dispositivi Apple e Android che eseguono client mobili Lync 2013). Se il **numero di sessioni attualmente** attivo è molto più alto rispetto **al numero di sessioni attivo corrente con gli abbonamenti a presenza attiva**, ciò indica che più utenti utilizzano un dispositivo endpoint in background, ad esempio un dispositivo Apple iOS o Windows Phone in MCX. (Windows Phone è l'unico client per dispositivi mobili Lync 2013 che registrerà questo tipo di registrazione).

È necessario impostare un limite per il **conteggio delle sessioni attivo con gli abbonamenti per la presenza attiva** e i contatori delle prestazioni del **conteggio delle sessioni** attivo in base all'utilizzo previsto, ai risultati della pianificazione della capacità e al monitoraggio continuo del servizio per dispositivi mobili e di altri contatori di front end server. I limiti impostati devono consentire di valutare la capacità del server e aumentare gli avvisi in caso di superamento della capacità.

Per determinare i limiti corretti, è necessario determinare in primo luogo la quantità di memoria disponibile nel front end server per il servizio per dispositivi mobili. Monitorare i contatori per determinare quando è necessario pianificare la capacità aggiuntiva, in base alla formula seguente:

Memoria totale utilizzata dal servizio per dispositivi mobili MCX (MB) = 164 + (400 + 134)/ \* 1024 **Currently Active Session Count with Active Presence Subscriptions** + \* 400/1024 (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 capacity Calculator è un foglio di calcolo prepopolato con tutte le formule che consentono a un pianificatore di determinare quali saranno i requisiti per i server, tra cui CPU, memoria e disco rigido. È possibile scaricare il foglio di calcolo e un documento associato in:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

Il front end server deve disporre di memoria sufficiente per supportare il servizio per dispositivi mobili in situazioni di failover. È possibile monitorare la memoria disponibile corrente sul front end server utilizzando il contatore **memoria\\disponibile** per i MByte oppure utilizzando l'equazione citata in precedenza per pianificare la quantità di memoria che il servizio per dispositivi mobili deve utilizzare.

Se la quantità di memoria disponibile nel front end server è inferiore a 1.500 MB quando si pianifica il numero previsto di utenti di dispositivi mobili, è necessario aggiungere altro hardware per supportare il servizio per dispositivi mobili. Per ulteriori informazioni, vedere [monitoraggio dei dispositivi mobili per le prestazioni in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) nella documentazione relativa alle operazioni.

<div>

## <a name="see-also"></a>Vedere anche


[Monitoraggio della mobilità per le prestazioni in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

