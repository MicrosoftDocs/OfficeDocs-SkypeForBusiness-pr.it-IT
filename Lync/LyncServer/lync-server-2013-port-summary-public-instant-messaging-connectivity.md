---
title: 'Lync Server 2013: riepilogo della porta-connettività di messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Riepilogo della porta-connettività di messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-16_

Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, prima di tutto si noti che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di Lync per contattare i contatti di messaggistica istantanea pubblica.

Windows Live Messenger può partecipare alle comunicazioni audio/video con i client Lync. Questo account per la porta del firewall e la configurazione di protocollo molto simili che in genere sono presenti nel firewall per supportare i client Lync come utenti esterni.

<div>


> [!IMPORTANT]  
> Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.<BR>La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, ad eccezione della Cina continentale. Skype diventerà il client federativo per gli utenti federati che in precedenza usavano Messenger.



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
<td><p>Interfaccia di Access Server Edge</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e federati che usano SIP.</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaccia di Access Server Edge</p></td>
<td><p>Partner di connettività per messaggistica istantanea pubblica</p></td>
<td><p>Per la connettività di messaggistica istantanea federata e federati che usano SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>Client</p></td>
<td><p>Interfaccia di Access Server Edge</p></td>
<td><p>Traffico SIP da client a server per l'accesso degli utenti esterni.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Interfaccia di Access Server Edge</p></td>
<td><p>Client di Messenger Live</p></td>
<td><p>Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interfaccia di Access Server Edge</p></td>
<td><p>Client di Messenger Live</p></td>
<td><p>Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Client di Messenger Live</p></td>
<td><p>Interfaccia di Access Server Edge</p></td>
<td><p>Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

