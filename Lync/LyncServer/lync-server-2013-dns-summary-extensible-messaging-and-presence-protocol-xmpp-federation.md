---
title: Riepilogo DNS-Federazione XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Riepilogo DNS-Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-08_

Per configurare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, è possibile creare due record DNS (Domain Name System) in un server DNS esterno che risolverà i record nel servizio Edge di Access del server perimetrale o del pool di Edge.

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo DNS per il protocollo di messaggistica e presenza estensibile


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
<th>FQDN</th>
<th>Indirizzo IP/record host FQDN</th>
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5269</p></td>
<td><p>_xmpp-server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync. Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP. Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>xmpp.contoso.com (ad esempio)</p></td>
<td><p>Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</p></td>
<td><p>Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP. In genere, il record SRV creato punterà al record host (A o AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione della federazione di XMPP in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  


[Determinare i requisiti di DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

