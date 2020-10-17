---
title: 'Lync Server 2013: riepilogo delle porte-connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bce3413e7e41e3784cb0ba300c621a7c042b618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534163"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Riepilogo delle porte-connettività per la messaggistica istantanea pubblica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-16_

Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, è necessario tenere presente che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di contattare i contatti di messaggistica istantanea pubblica.

Windows Live Messenger è in grado di partecipare alle comunicazioni audio/video con i client Lync. Questo account per la porta del firewall molto simile e la configurazione del protocollo che in genere si dispone sul firewall per supportare i client Lync come utenti esterni.

<div>


> [!IMPORTANT]  
> Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.<BR>La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, tranne che per la Cina continentale. Skype diventerà il client federativo per gli utenti federati che in precedenza utilizzavano Messenger.



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

## <a name="see-also"></a>Vedere anche


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

