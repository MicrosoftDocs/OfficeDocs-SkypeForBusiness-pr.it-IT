---
title: 'Lync Server 2013: Riepilogo DNS-bilanciamento del carico DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11128cb1989bfc2863fe52fe27d0c86eb4b468a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Riepilogo DNS-bilanciamento del carico DNS e del caricamento in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

La tabella seguente contiene un riepilogo dei record DNS che sono necessari per supportare il bilanciamento del carico DNS e il bilanciamento del carico hardware. Il ruolo del Director richiede record DNS simili a quelli del front end server. Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director. Diverso dal front end server, il pool di Director non ospita gli account utente o ospita i servizi per dispositivi mobili.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Record DNS necessari per il pool di server Director tramite bilanciamento del carico DNS e bilanciamento del carico hardware

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
<td><p>Record host Director utilizzato per la replica e il server in server</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Pool Director</p></td>
<td><p>Record host per il pool di server Director con bilanciamento del carico DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Pool Director</p></td>
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

