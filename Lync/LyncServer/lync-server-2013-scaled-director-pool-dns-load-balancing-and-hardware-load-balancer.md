---
title: Pool di server Director con scalabilità implementata - bilanciamento del carico DNS e bilanciamento del carico hardware
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
ms.openlocfilehash: 16203f7e291b7957793e71872483c93f2d1d04d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Pool di server Director con scalabilità implementata - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Un pool di Director in scala, in cui sono distribuiti più Director per gestire capacità aggiuntive e per ottenere una disponibilità elevata, richiede il bilanciamento del carico per distribuire le comunicazioni client e server a tutti i membri del pool. Un amministratore ospita i servizi Web in modo molto simile a un pool Front-end. Per specificare il bilanciamento del carico, è possibile usare il bilanciamento del carico hardware o il bilanciamento del carico del sistema DNS (Domain Name System) e il bilanciamento del carico hardware. Il bilanciamento del carico hardware è necessario per i servizi Web e il bilanciamento del carico DNS da solo non offre le funzionalità necessarie per i servizi Web.

Gli argomenti seguenti descrivono le considerazioni sulla pianificazione per la distribuzione di un pool di Director tramite il bilanciamento del carico DNS in combinazione con il bilanciamento del carico hardware. Se si intende usare il bilanciamento del carico hardware, ma non il bilanciamento del carico DNS per il pool di Director, vedere l'argomento servizio di bilanciamento del carico hardware per il [pool di Director in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) che descrive i requisiti di pianificazione per tale topologia.

![Pool di server Director con scalabilità implementata](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool di server Director con scalabilità implementata")

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Riepilogo delle porte - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Riepilogo di DNS - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

