---
title: 'Lync Server 2013: Riepilogo delle porte - singolo server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0179d6fd27207d28caa10ffa01bea155f9b00c03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Riepilogo delle porte - singolo server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

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
<td><p>Director</p></td>
<td><p>Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaccia interna del proxy inverso</p></td>
<td><p>Director</p></td>
<td><p>Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Server front-end o pool Front-End</p></td>
<td><p>Comunicazioni tra server tra il Director e il front end server</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Client interni</p></td>
<td><p>Servizi Web Director</p></td>
<td><p>Il Director offre servizi Web a client interni ed esterni.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Client interni</p></td>
<td><p>Servizi Web Director</p></td>
<td><p>Il Director offre servizi Web a client interni ed esterni.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Director</p></td>
<td><p>Comunicazioni SIP dall'Edge Server al Director e al server front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClasAgent. exe) e raccolta log</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClasAgent. exe) e raccolta log</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClasAgent. exe) e raccolta log</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

