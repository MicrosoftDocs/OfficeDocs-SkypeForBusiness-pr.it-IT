---
title: Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-04-27_

Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010. L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.

Oltre a IPv4, il server perimetrale supporta ora IPv6. Per chiarezza, solo IPv4 viene usato negli scenari.

**Edge consolidato in scala con il bilanciamento del carico hardware**

![Porte e protocolli della rete perimetrale del server perimetrale](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Porte e protocolli della rete perimetrale del server perimetrale")

<div>

## <a name="port-and-protocol-details"></a>Dettagli sulla porta e sul protocollo

È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.

Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentito per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita. In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico hardware: interfaccia esterna-nodo 1 e nodo 2 (esempio)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Controllo e recupero di certificati revocati/CRL</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Indirizzo IP del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server. Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Indirizzo IP pubblico del servizio Edge A/V Edge Server</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico hardware: nodo di interfaccia interno 1 e nodo 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (può essere definito come indirizzo del server front-end o indirizzo IP virtuale del pool Front-end che gestisce il servizio gateway XMPP)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (può essere definito come front end Server IP o pool che contiene l'Central Management store)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Replica delle modifiche da Central Management store a Edge Server</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (può essere definito come IP Director, IP del server front end o IP virtuale del pool)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico di Web Conferencing dalla distribuzione interna all'interfaccia Internal Edge Server</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Any (può essere definito come IP Director, IP del server front end o IP virtuale del pool)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Any (può essere definito come IP Director, IP del server front end o IP virtuale del pool)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</p></td>
</tr>
</tbody>
</table>


I dispositivi di bilanciamento del carico hardware hanno requisiti specifici quando vengono distribuiti per consentire il bilanciamento del carico e della disponibilità per Lync Server. I requisiti sono definiti nella figura e nelle tabelle seguenti. I fornitori di terze parti possono usare terminologia diversa per i requisiti definiti in questo articolo. Sarà necessario eseguire il mapping dei requisiti di Lync Server alle funzionalità e alle opzioni di configurazione fornite dal fornitore del dispositivo di bilanciamento del carico hardware.

Quando si configurano i criteri di bilanciamento del carico hardware, tenere presente quanto segue:

  - La conversione di SNAT (Source Network Address Translation) può essere configurata nel servizio di bilanciamento del carico hardware (HLB) per Access Edge service e Web Conferencing Edge service

  - SNAT non può essere configurato nell'A/V Edge service: l'A/V Edge service deve rispondere con l'indirizzo del server reale, non con l'IP virtuale di HLB (VIP), per l'attraversamento semplice di UDP su NAT (STUN)/Traversal l'uso di Relay NAT (TURN)/Federation TURN (FTURN) per funzionare correttamente
    
      - Se il cliente invia una richiesta a HLB, la risposta deve tornare dal VIP di HLB
    
      - Se il client invia una richiesta al bordo, la risposta deve tornare dall'IP del bordo

  - Gli indirizzi IP pubblici vengono usati per ogni interfaccia server e per i VIP di HLB e i requisiti per l'indirizzo IP pubblico sono N + 1, dove esiste un indirizzo IP pubblico per ogni interfaccia del server reale e uno per ogni VIP di HLB. In cui sono presenti 2 server perimetrali nel pool, vengono visualizzati 9 indirizzi IP pubblici, in cui vengono usati 3 per i VIP di HLB e uno per ogni interfaccia Edge Server (un totale di sei per i server)

  - Per il servizio Access Edge e Web Conferencing Edge (e l'uso di NAT su HLB) il cliente contatta il VIP, il VIP cambia l'indirizzo IP di origine dal client al proprio indirizzo IP. L'interfaccia del server indirizza l'indirizzo del mittente al VIP, il VIP cambia l'indirizzo di origine dall'indirizzo IP dell'interfaccia server e invia il pacchetto al client

  - Per il servizio A/V Edge, il VIP non deve cambiare l'indirizzo IP di origine e l'indirizzo del server reale viene restituito direttamente al client: non è possibile configurare il NAT in HLB per il traffico AV
    
      - Se il cliente invia una richiesta al VIP di HLB, la risposta deve tornare dal VIP di HLB
    
      - Se il client invia una richiesta all'IP del bordo, la risposta deve tornare dall'IP del bordo

  - Per AV, il firewall esterno manterrà l'indirizzo IP pubblico del server reale per tutti i pacchetti

  - Una volta stabilito, il client per comunicare con un servizio Edge a/V è il server reale, non il HLB

  - Il bordo interno ai server e ai client interni deve essere instradato e le route permanenti sono impostate per tutte le reti interne che ospitano server o client.

  - Il servizio VIP Access Edge di HLB fungerà da gateway predefinito per ogni interfaccia Edge Server

<div>


> [!NOTE]
> Per altre informazioni sulla pianificazione e la funzionalità NAT, vedere <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisiti di bilanciamento del carico hardware per Lync Server 2013</A>.



</div>

![Dettagli su porte e protocolli del server perimetrale](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Dettagli su porte e protocolli del server perimetrale")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Impostazioni della porta esterna necessarie per il bordo consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali di interfacce esterne

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Il servizio proxy XMPP invia il traffico ai contatti XMPP in federazioni XMPP definite</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Edge Access</p></td>
<td><p>Traffico SIP da client a server per l'accesso degli utenti esterni</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Edge Access</p></td>
<td><p>Segnalazione SIP, federati e connettività di messaggistica istantanea pubblica tramite SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Indirizzo VIP pubblico del servizio Edge Access</p></td>
<td><p>Partner federato</p></td>
<td><p>Segnalazione SIP, federati e connettività di messaggistica istantanea pubblica tramite SIP</p></td>
</tr>
<tr class="even">
<td><p>Web Conferencing/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico di Edge Server Web Conferencing Edge</p></td>
<td><p>Supporto per Web Conferencing</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Edge A/V Edge</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Edge A/V Edge</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali di interfacce interne

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
<td><p>Any (può essere definito come amministratore, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del front end server o del pool Front-End)</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Traffico SIP in uscita (da Director, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del server front-end o del pool Front-End) a VIP Edge interno</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Any (può essere definito come amministratore, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del front end server o del pool Front-End)</p></td>
<td><p>Traffico SIP in ingresso (a Director, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del server front-end o del pool Front-End) dall'interfaccia interna di Edge Server</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni se non è possibile stabilire la comunicazione UDP, viene usato TCP per il trasferimento di file e la condivisione desktop</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni se non è possibile stabilire la comunicazione UDP, viene usato TCP per il trasferimento di file e la condivisione desktop</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

