---
title: Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware
description: Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b30dfcc3515420ffb34343e4653e9518b1b9c3ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563462"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware in Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Un pool di server Director con scalabilità orizzontale, in cui sono distribuiti più Director per gestire la capacità aggiuntiva e per garantire la disponibilità elevata, richiede il bilanciamento del carico per la distribuzione delle comunicazioni client e di tutti i membri del pool. Un amministratore ospita i servizi Web molto simile a un pool Front end. Per garantire il bilanciamento del carico, è possibile utilizzare il bilanciamento del carico hardware oppure il bilanciamento del carico DNS (Domain Name System) insieme al bilanciamento del carico hardware. Quest'ultimo è necessario per i servizi Web e il bilanciamento del carico DNS da solo non offre le funzionalità richieste per tali servizi.

Negli argomenti seguenti vengono illustrate le considerazioni relative alla pianificazione per la distribuzione di un pool di server Director tramite bilanciamento del carico DNS in combinazione con il bilanciamento del carico hardware. Se si intende utilizzare il bilanciamento del carico hardware, ma non il bilanciamento del carico DNS per il pool di server Director, vedere l'argomento relativo al pool di bilanciamento del carico [hardware in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) che descrive i requisiti di pianificazione per la topologia.

![Pool di server Director con scalabilità implementata](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool di server Director con scalabilità implementata")

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Riepilogo del certificato-bilanciamento del carico DNS e del caricamento in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Riepilogo delle porte-bilanciamento del carico DNS e del caricamento in Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Riepilogo DNS-bilanciamento del carico DNS e del caricamento in Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

