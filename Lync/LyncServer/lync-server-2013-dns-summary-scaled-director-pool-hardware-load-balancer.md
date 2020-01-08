---
title: 'Lync Server 2013: Riepilogo di DNS - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff76d69952d08db72e5647b58e38a43b4181c8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Riepilogo di DNS - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

La tabella seguente contiene un riepilogo dei record DNS necessari per il supporto del Director di bilanciamento del carico hardware. Il ruolo del Director richiede record DNS simili al server front-end. Il numero di record necessari viene riflesso nei nomi alternativi del soggetto necessari per il certificato Director. Diverso dal server front-end, il pool di Director non ospita gli account utente o ospita i servizi mobili.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Record DNS necessari per il pool di Director con un bilanciamento del carico hardware e un bilanciamento del carico DNS

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione/tipo/porta</th>
<th>Record FQDN/DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Record host Director usato per la replica e la comunicazione da server a server</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Pool Director HLB VIP</p></td>
<td><p>Record host per il pool di Director di bilanciamento del carico DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Pool Director HLB VIP</p></td>
<td><p>SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Pool Director HLB VIP</p></td>
<td><p>Servizi Web di dialin con bilanciamento del carico hardware pubblicati da proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Pool Director HLB VIP</p></td>
<td><p>Bilanciamento del carico hardware pubblicato per soddisfare i servizi Web da proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Pool Director HLB VIP</p></td>
<td><p>Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni del proxy inverso per il pool di Director</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

