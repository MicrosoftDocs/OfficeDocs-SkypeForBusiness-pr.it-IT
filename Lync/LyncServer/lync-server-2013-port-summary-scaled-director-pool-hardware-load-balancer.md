---
title: 'Lync Server 2013: riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware'
description: 'Lync Server 2013: riassunto delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564552"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-21_

I requisiti delle porte del firewall per un pool di server Director sono costituiti dalle porte utilizzate per stabilire la comunicazione con il Director dall'interfaccia interna del server perimetrale o dall'interfaccia interna del proxy inverso. Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end. Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server. Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server. È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Porte director e protocollo per le definizioni firewall

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo/Protocollo/TCP o UDP/Porta</th>
<th>Indirizzo IP di origine</th>
<th>Indirizzo IP di destinazione</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>VIP del bilanciamento del carico hardware del server Director</p></td>
<td><p>Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e Front End Servers.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>VIP del bilanciamento del carico hardware del server Director</p></td>
<td><p>Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e Front End Servers.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front End Server o pool Front End</p></td>
<td><p>Comunicazione tra server tra il direttore di HLB VIP e i Front End Server</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Client interni</p></td>
<td><p>VIP del bilanciamento del carico hardware del server Director</p></td>
<td><p>Il Director fornisce servizi Web ai client interni e esterni.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Client interni</p></td>
<td><p>VIP del bilanciamento del carico hardware del server Director</p></td>
<td><p>Il Director fornisce servizi Web ai client interni e esterni.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>VIP del bilanciamento del carico hardware del server Director</p></td>
<td><p>Comunicazione SIP dal server perimetrale al Director e front end server.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Director</p></td>
<td><p>Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Director</p></td>
<td><p>Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Director</p></td>
<td><p>Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

