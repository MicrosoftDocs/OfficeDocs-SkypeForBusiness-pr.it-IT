---
title: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT
description: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564562"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-04-03_

La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010. L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.

Oltre a IPv4, il server perimetrale supporta ora IPv6. Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.

**Perimetro di rete per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Informazioni dettagliate sulle porte e sui protocolli

È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.

Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea, presenza, Web Conferencing, audio/video (A/V) e Federazione.

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a>Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT: interfaccia esterna

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
<td><p>Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</p></td>
<td><p>Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Revoca di certificati/controllo CRL e recupero</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/DNS/TCP/53</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su TCP</p></td>
</tr>
<tr class="even">
<td><p>Accesso/DNS/UDP/53</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su UDP</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/SIP (TLS)/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Traffico SIP client-server per l'accesso degli utenti esterni</p></td>
</tr>
<tr class="even">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Per connettività di messaggistica istantanea pubblica e federata con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Per connettività di messaggistica istantanea pubblica e federata con SIP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/443 di Web Conferencing/PSOM (TLS)</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio Web Conferencing Edge Server perimetrale</p></td>
<td><p>File multimediali Web Conferencing</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge. Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a>Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT: interfaccia interna

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
<td><p>Qualsiasi (può essere definito come IP Server Standard Edition, indirizzo IP del server Standard Edition o indirizzo IP del pool che esegue il servizio gateway XMPP)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</p></td>
<td><p>Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Riepilogo firewall per la federazione


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
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Indirizzo IP pubblico del servizio Access Edge</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Per connettività di messaggistica istantanea pubblica e federata con SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Riepilogo firewall - connettività per messaggistica istantanea pubblica


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
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Partner per la connettività per messaggistica istantanea pubblica</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Per connettività di messaggistica istantanea pubblica e federata con SIP</p></td>
</tr>
<tr class="even">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Partner per la connettività per messaggistica istantanea pubblica</p></td>
<td><p>Per connettività di messaggistica istantanea pubblica e federata con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/SIP (TLS)/TCP/443</p></td>
<td><p>Client</p></td>
<td><p>Servizio Access Edge Server perimetrale</p></td>
<td><p>Traffico SIP client-server per l'accesso utente esterno</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Client Live Messenger</p></td>
<td><p>Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Client Live Messenger</p></td>
<td><p>Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Client Live Messenger</p></td>
<td><p>Servizio A/V Edge Server perimetrale</p></td>
<td><p>Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

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
<td><p>Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</p></td>
<td><p>Porta di comunicazione standard da server a server per XMPP. Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Porta di comunicazione standard da server a server per XMPP. Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Ogni IP dell'interfaccia del server perimetrale interno</p></td>
<td><p>Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

