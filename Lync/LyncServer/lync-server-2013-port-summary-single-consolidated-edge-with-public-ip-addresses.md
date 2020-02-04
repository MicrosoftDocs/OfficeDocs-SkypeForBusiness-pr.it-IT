---
title: Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010. L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end. Le informazioni sulla pianificazione per il proxy inverso e la Federazione si trovano in [scenari per proxy inverso in Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica nelle sezioni di Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , rispettivamente.

Oltre a IPv4, il server perimetrale supporta ora IPv6. Per chiarezza, solo IPv4 viene usato negli scenari.

**Rete perimetrale aziendale per singoli bordi consolidati con indirizzi IP pubblici**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Dettagli sulla porta e sul protocollo

È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.

Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentita per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita. In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a>Riepilogo del firewall per un singolo bordo consolidato con indirizzi IP pubblici: interfaccia esterna

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</p></td>
<td><p>Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Controllo e recupero di certificati revocati/CRL</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su TCP</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su UDP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Traffico SIP da client a server per l'accesso degli utenti esterni</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e pubblica con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e pubblica con SIP</p></td>
</tr>
<tr class="even">
<td><p>Web Conferencing/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico di Edge Server Web Conferencing Edge</p></td>
<td><p>Supporto per Web Conferencing</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server. Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a>Riepilogo del firewall per un singolo bordo consolidato con indirizzi IP pubblici: interfaccia interna

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
<th>Indirizzo IP di origine</th>
<th>Indirizzo IP di destinazione</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (può essere definito come IP standard server, indirizzo IP del server Standard Edition o indirizzo IP del pool in cui è in uso il servizio gateway XMPP)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</p></td>
<td><p>IP del server perimetrale o pool che contiene l'interfaccia interna</p></td>
<td><p>Traffico SIP in uscita (da Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end) all'interfaccia interna del server Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Any (può essere definito come Director, indirizzo IP del pool di Director, Front End Server o indirizzo del pool Front-End)</p></td>
<td><p>Traffico SIP in ingresso (per Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o di front end) dall'interfaccia interna di Edge Server</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (può essere definito come indirizzo IP del server front-end o ogni indirizzo IP del server front-end in un pool Front-End)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico di Web Conferencing dal server front-end o da ogni server front-end se in un pool, all'interfaccia interna di Edge Server</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (può essere definito come indirizzo IP del server front-end o pool che contiene l'Central Management store)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Replica delle modifiche da Central Management store a Edge Server</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Riepilogo del firewall per la Federazione


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
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge di Access</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e pubblica con SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Riepilogo firewall-connettività di messaggistica istantanea pubblica


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
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Partner di connettività per messaggistica istantanea pubblica</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e pubblica con SIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>Partner di connettività per messaggistica istantanea pubblica</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e pubblica con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>Client</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>Traffico SIP da client a server per l'accesso degli utenti esterni</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>Client di Messenger Live</p></td>
<td><p>Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>Client di Messenger Live</p></td>
<td><p>Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Client di Messenger Live</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile


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
<td><p>Indirizzo IP dell'interfaccia del servizio Edge Server Edge</p></td>
<td><p>Porta di comunicazione standard da server a server per XMPP. Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indirizzo IP dell'interfaccia del servizio Edge Server Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Porta di comunicazione standard da server a server per XMPP. Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Ogni IP dell'interfaccia del server perimetrale interno</p></td>
<td><p>Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool di Edge</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

