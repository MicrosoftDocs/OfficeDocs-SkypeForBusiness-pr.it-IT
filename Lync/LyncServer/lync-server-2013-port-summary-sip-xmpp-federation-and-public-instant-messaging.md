---
title: Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2512b49f9e0bcdc092354a5f43cb234c7e4d5445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-15_

I requisiti relativi a porte, protocolli e firewall per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server sono simili a quelli per il server perimetrale distribuito. I client avviano la comunicazione con il servizio Access Edge tramite TLS/SIP/TCP 443. I partner federati, tuttavia, avvierà le comunicazioni al servizio Access Edge su MTLS/SIP/TCP 5061.

Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, è necessario tenere presente che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di contattare i contatti di messaggistica istantanea pubblica.

Windows Live Messenger è in grado di partecipare alle comunicazioni audio/video con i client Lync. Questo account per la porta del firewall molto simile e la configurazione del protocollo che in genere si dispone sul firewall per supportare i client Lync come utenti esterni.

<div>


> [!IMPORTANT]
> Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.<BR>La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, tranne che per la Cina continentale. Skype diventerà il client federativo per gli utenti federati che in precedenza utilizzavano Messenger.



</div>

Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuiti nel server perimetrale consentono la comunicazione dal partner federato XMPP al server perimetrale e consentono anche la comunicazione dal server perimetrale al sistema XMPP. partner federato. Una regola viene definita anche nel firewall con accesso interno dal front end server o dal pool Front end al server perimetrale o al pool di Edge.

<div>

## <a name="firewall-summary---sip-federation"></a>Riepilogo del firewall-federazione SIP


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
<th>Notes</th>
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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Partner per la connettività per messaggistica istantanea pubblica</p></td>
<td><p>Interfaccia di accesso ai server perimetrali</p></td>
<td><p>Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</p></td>
</tr>
<tr class="even">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaccia di accesso ai server perimetrali</p></td>
<td><p>Partner per la connettività per messaggistica istantanea pubblica</p></td>
<td><p>Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/SIP (TLS)/TCP/443</p></td>
<td><p>Client</p></td>
<td><p>Interfaccia di accesso ai server perimetrali</p></td>
<td><p>Traffico SIP da client a server per l'accesso degli utenti esterni.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Interfaccia di accesso ai server perimetrali</p></td>
<td><p>Client Live Messenger</p></td>
<td><p>Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interfaccia di accesso ai server perimetrali</p></td>
<td><p>Client Live Messenger</p></td>
<td><p>Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Client Live Messenger</p></td>
<td><p>Interfaccia di accesso ai server perimetrali</p></td>
<td><p>Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Riepilogo del firewall-protocollo XMPP (Extensible Messaging and Presence Protocol)


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


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

