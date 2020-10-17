---
title: Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c8d7f99b4a7c72b9eb039fb7447397e711caa36
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527923"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuito nel server perimetrale consentono la comunicazione dal partner federato XMPP al server perimetrale e consentono inoltre la comunicazione dal server perimetrale al partner federato XMPP. Una regola viene definita anche nel firewall con accesso interno dal front end server o dal pool Front end al server perimetrale o al pool di Edge.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo/TCP o UDP/porta</th>
<th>Origine (indirizzo IP)</th>
<th>Destinazione (indirizzo IP)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP dell'interfaccia del servizio Access Edge</p></td>
<td><p>Porta di comunicazione standard da server a server per XMPP. Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indirizzo IP dell'interfaccia del servizio Access Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Porta di comunicazione standard da server a server per XMPP. Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Qualsiasi</p></td>
<td><p>IP dell'interfaccia del server perimetrale interno</p></td>
<td><p>Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end al server perimetrale</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

