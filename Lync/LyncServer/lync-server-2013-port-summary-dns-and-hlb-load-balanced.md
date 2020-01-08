---
title: 'Lync Server 2013: Riepilogo delle porte - bilanciamento del carico DNS e bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd2a276f9495d314d2a8d4588f027df08978b94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Riepilogo delle porte - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

I requisiti della porta firewall per un singolo Director sono costituiti dalle porte usate per stabilire la comunicazione con il Director dall'interfaccia interna o dalla rete interna del proxy inverso. Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al Director, oltre al pool Front end e al server front-end. Inoltre, deve essere disponibile una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server. Il protocollo SIP USA SIP/MTLS/TCP 5061 dall'Edge Server al pool Front end e front end server. Deve essere creata anche una regola che consente la comunicazione SIP/MTLS/TCP 5061 da parte del Director, del pool Front end e del front end server all'interfaccia interna del server perimetrale.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Porte e protocolli per Director singole per le definizioni di firewall

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo/protocollo/TCP o UDP/porta</th>
<th>Indirizzo IP di origine</th>
<th>Indirizzo IP di destinazione</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>VIP di bilanciamento del carico hardware Director</p></td>
<td><p>Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata al Direttore servizi Web di HLB VIP e front end server.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>VIP di bilanciamento del carico hardware Director</p></td>
<td><p>Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata al Direttore servizi Web di HLB VIP e front end server.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Pool Front end o front end server</p></td>
<td><p>Comunicazioni tra server tra il Director HLB VIP e il front end server o Front End Servers.</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Client interni</p></td>
<td><p>VIP di bilanciamento del carico hardware Director</p></td>
<td><p>Il Director offre servizi Web a client interni e esterni.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Client interni</p></td>
<td><p>VIP di bilanciamento del carico hardware Director</p></td>
<td><p>Il Director offre servizi Web a client interni e esterni.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Director</p></td>
<td><p>Comunicare SIP dall'Edge Server al Director, oltre ai server front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Director</p></td>
<td><p>Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Director</p></td>
<td><p>Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Director</p></td>
<td><p>Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

