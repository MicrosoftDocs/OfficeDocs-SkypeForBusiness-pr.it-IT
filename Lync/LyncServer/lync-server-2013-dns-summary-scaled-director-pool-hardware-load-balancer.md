---
title: 'Lync Server 2013: pool di directory di riepilogo DNS con scalabilità orizzontale, bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10c742d8d58392b06bc563cd0a947d46243703d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Pool di server Director con scalabilità verticale di riepilogo DNS, bilanciamento del carico hardware in Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

La tabella seguente contiene un riepilogo dei record DNS che sono necessari per supportare il bilanciamento del carico hardware. Il ruolo del Director richiede record DNS simili a quelli del front end server. Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director. Diverso dal front end server, il pool di Director non ospita gli account utente o ospita i servizi per dispositivi mobili.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Record DNS necessari per il pool di server Director utilizzando un dispositivo di bilanciamento del carico hardware e il bilanciamento del carico DNS

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
<th>FQDN/Record DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Record host Director utilizzato per la replica e la comunicazione tra server e server</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>VIP di HLB del pool di server Director</p></td>
<td><p>Record host per il pool di server Director con bilanciamento del carico DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>VIP di HLB del pool di server Director</p></td>
<td><p>SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>VIP di HLB del pool di server Director</p></td>
<td><p>Servizi Web dialin pubblicati con bilanciamento del carico hardware dal proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>VIP di HLB del pool di server Director</p></td>
<td><p>Bilanciamento del carico hardware pubblicato per i servizi Web di meet proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>VIP di HLB del pool di server Director</p></td>
<td><p>Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni per il proxy inverso per il pool di server Director</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

