---
title: Server di sintesi DNS-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ab0c9b68d21af782570c850642ce7e83b996d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Server di sintesi DNS-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-27_

I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte. Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.

Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Per informazioni dettagliate sulla configurazione automatica dei client Lync 2013 se il DNS split-brain non è configurato, vedere la sezione "configurazione automatica senza DNS split brain" in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Nella tabella seguente è incluso un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata con scalabilità implementata (bilanciamento del carico hardware) illustrata in Reference Architecture 3: Scaled Consolidated Edge (Hardware Load Balanced). Si noti che alcuni record DNS sono necessari solo per la configurazione automatica per i client Lync. Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisiti della scheda di rete per i server perimetrali

Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna. Ad esempio, come illustrato nella figura dello scenario perimetrale consolidato con scalabilità verticale in [scala consolidata con bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), il gateway predefinito dovrebbe puntare al firewall esterno.

È possibile configurare due schede di rete in ogni server perimetrale, come indicato di seguito:

  - **Scheda di rete 1 (interfaccia interna)**
    
    Interfaccia interna con indirizzo 172.25.33.10 assegnato.
    
    Nessun gateway predefinito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene client o server Lync Server che eseguono Lync Server (ad esempio, da 172.25.33.0 a 192.168.10.0).

  - **Scheda di rete 2 (interfaccia esterna)**
    
    A questa scheda di rete sono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 per il servizio Access Edge, 131.107.155.20 per il servizio Web Conferencing Edge, 131.107.155.30 per il servizio A/V Edge.
    
    <div>
    

    > [!NOTE]
    > Gli indirizzi IP assegnati alle interfacce di rete esterne effettive del server perimetrale possono dipendere da quale dispositivo di bilanciamento del carico hardware si sceglie. Fare riferimento alla documentazione del dispositivo di bilanciamento del carico hardware per comprendere i requisiti degli indirizzi IP effettivi.<BR>È possibile, anche se non consigliabile, utilizzare un singolo indirizzo IP per tutte e tre le interfacce dei servizi perimetrali. Benché in questo modo sia possibile utilizzare meno indirizzi IP, vengono richiesti numeri di porte diversi per ogni servizio. Il numero di porta predefinito è 443/TCP, che garantisce il passaggio del traffico attraverso i firewall più remoti. Se si modificano i valori delle porte su (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge potrebbe causare problemi per gli utenti remoti in cui un firewall che sono dietro non consente il traffico su 5061/TCP e 444/TCP. L'utilizzo di tre indirizzi IP distinti inoltre semplifica la risoluzione dei problemi poiché consente di applicare un filtro in base all'indirizzo IP.

    
    </div>
    
    L'indirizzo IP del servizio Access Edge è primario, con gateway predefinito impostato su router con connessione Internet (131.107.155.1).
    
    Servizio Web Conferencing Edge e indirizzi IP del servizio A/V Edge secondario.

<div>


> [!TIP]
> La configurazione del server perimetrale con due schede di rete è una delle due opzioni. L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale. Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Record DNS necessari per la topologia perimetrale consolidata e bilanciamento del carico hardware (esempio)

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
<th>FQDN/Record DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interfaccia esterna del servizio Access Edge (contoso). Ripetere per tutti i domini SIP con utenti abilitati per Lync, se necessario.</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaccia esterna del servizio Web Conferencing Edge</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interfaccia esterna del servizio A/V Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna del servizio Access Edge. Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna del servizio SIP Access Edge necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (denominato Federazione avanzata nelle versioni precedenti). Ripetere quanto necessario per tutti i domini SIP con gli utenti abilitati per Lync e i client Microsoft Lync mobile che utilizzano il servizio di notifica push o il servizio di notifica push di Apple</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaccia interna perimetrale consolidata</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

