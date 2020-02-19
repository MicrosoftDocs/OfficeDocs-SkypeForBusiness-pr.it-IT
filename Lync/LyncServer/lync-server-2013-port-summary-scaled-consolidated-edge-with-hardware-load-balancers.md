---
title: Riepilogo delle porte-server perimetrale consolidato in scala con i dispositivi di bilanciamento del carico hardware
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
ms.openlocfilehash: 78196bab17af69d83bbeacf636b4b2ba4e972121
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Riepilogo delle porte-perimetro consolidato con bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-04-27_

La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010. L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.

Oltre a IPv4, il server perimetrale supporta ora IPv6. Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.

**Server perimetrale consolidato in scala con bilanciamento del carico hardware**

![Porte e protocolli della rete perimetrale del server Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Porte e protocolli della rete perimetrale del server Edge")

<div>

## <a name="port-and-protocol-details"></a>Informazioni dettagliate sulle porte e sui protocolli

È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.

Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In altre parole, la messaggistica SIP da e al servizio Access Edge è coinvolta nella messaggistica istantanea, nella presenza, nelle conferenze Web, nell'audio/video (A/V) e nella federazione.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: interfaccia esterna – nodo 1 e nodo 2 (esempio)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Indirizzo IP pubblico del servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Revoca di certificati/controllo CRL e recupero</p></td>
</tr>
<tr class="even">
<td><p>Accesso/DNS/TCP/53</p></td>
<td><p>Indirizzo IP pubblico del servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su TCP</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/DNS/UDP/53</p></td>
<td><p>Indirizzo IP pubblico del servizio Access Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Query DNS su UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Indirizzo IP del servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge. Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: nodo interno dell'interfaccia 1 e nodo 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualsiasi (può essere definito come indirizzo front end server o indirizzo IP virtuale del pool Front end che esegue il servizio gateway XMPP)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Qualsiasi (può essere definito come l'IP o il pool del server front end server che contiene l'archivio di gestione centrale)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Traffico delle conferenze Web dalla distribuzione interna all'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia interna del server perimetrale</p></td>
<td><p>Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</p></td>
</tr>
</tbody>
</table>


I dispositivi di bilanciamento del carico hardware presentano requisiti specifici quando vengono distribuiti per garantire la disponibilità e il bilanciamento del carico per Lync Server. I requisiti sono definiti nella figura e nelle tabelle seguenti. I fornitori di terze parti possono utilizzare una terminologia diversa per i requisiti definiti in questo articolo. Sarà necessario eseguire il mapping dei requisiti di Lync Server alle caratteristiche e alle opzioni di configurazione fornite dal fornitore del dispositivo di bilanciamento del carico hardware.

Quando si configurano i dispositivi di bilanciamento del carico hardware, considerare i requisiti seguenti:

  - SNAT (Source Network Address Translation) può essere configurato sul bilanciamento del carico hardware (HLB) per il servizio Access Edge e il servizio Web Conferencing Edge

  - SNAT non può essere configurato nel servizio A/V Edge – il servizio A/V Edge deve rispondere con l'indirizzo del server reale, non con l'IP virtuale di HLB (VIP), per l'attraversamento semplice di UDP su NAT (STUN)/Traversal utilizzando Relay NAT (turno)/Federation turno (FTURN) per funzionare correttamente
    
      - Se il client invia una richiesta a HLB, la risposta deve tornare dal VIP di HLB
    
      - Se il client invia una richiesta al server perimetrale, è necessario che la risposta venga restituita dall'IP del server perimetrale.

  - Gli indirizzi IP pubblici vengono utilizzati su ogni interfaccia del server e sui VIP di HLB e i requisiti dell'indirizzo IP pubblico sono N + 1, dove esiste un indirizzo IP pubblico per ogni interfaccia del server reale e uno per ogni VIP di HLB. Se si dispone di 2 server perimetrali nel pool, vengono ottenuti 9 indirizzi IP pubblici, in cui vengono utilizzati 3 per i VIP di HLB e uno per ogni interfaccia server perimetrale (un totale di sei per i server)

  - Per il servizio Access Edge e il servizio Web Conferencing Edge (e l'utilizzo di NAT su HLB) il client contatta il VIP, il VIP cambia l'indirizzo IP di origine dal client al proprio indirizzo IP. L'interfaccia del server indirizza l'indirizzo del mittente al VIP, il VIP cambia l'indirizzo di origine dall'indirizzo IP dell'interfaccia del server e invia il pacchetto al client

  - Per il servizio A/V Edge, il VIP non deve modificare l'indirizzo IP di origine e l'indirizzo del server reale viene restituito direttamente al client: non è possibile configurare NAT su HLB per il traffico AV
    
      - Se il client invia una richiesta al VIP di HLB, la risposta deve tornare dal VIP di HLB
    
      - Se il client invia una richiesta all'IP del server perimetrale, la risposta deve tornare dall'IP del server perimetrale

  - Per AV, il firewall esterno manterrà l'indirizzo IP pubblico del server reale per tutti i pacchetti

  - Una volta stabilito, il client per la comunicazione del servizio a/V Edge è al server reale, non a HLB

  - Perimetro interno ai server e ai client interni devono essere instradati e le route permanenti sono impostate per tutte le reti interne che ospitano server o client

  - Il VIP del servizio Access Edge di HLB agirà come il gateway predefinito per ogni interfaccia server perimetrale

<div>


> [!NOTE]
> Per ulteriori informazioni sulla pianificazione e la funzionalità NAT, fare riferimento ai <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisiti hardware per il bilanciamento del carico per Lync Server 2013</A>.



</div>

![Dettagli relativi a porte e protocolli del server perimetrale](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Dettagli relativi a porte e protocolli del server perimetrale")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Impostazioni delle porte esterne necessarie per il server perimetrale consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali dell'interfaccia esterna

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</p></td>
<td><p>Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Il servizio proxy XMPP invia traffico ai contatti XMPP nelle federazioni XMPP definite</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/SIP (TLS)/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Access Edge</p></td>
<td><p>Traffico SIP client-server per l'accesso degli utenti esterni</p></td>
</tr>
<tr class="even">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Access Edge</p></td>
<td><p>SIP signaling, federato e la connettività di messaggistica istantanea pubblica con SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Indirizzo VIP pubblico del servizio Access Edge</p></td>
<td><p>Partner federato</p></td>
<td><p>SIP signaling, federato e la connettività di messaggistica istantanea pubblica con SIP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/443 di Web Conferencing/PSOM (TLS)</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio Web Conferencing Edge Server perimetrale</p></td>
<td><p>File multimediali Web Conferencing</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Indirizzo VIP pubblico del servizio A/V Edge Server perimetrale</p></td>
<td><p>Negoziazione STUN/TURN dei candidati su TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: IP virtuale dell'interfaccia interna

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
<td><p>Qualsiasi (può essere definito come amministratore, indirizzo IP virtuale del pool di server Director, indirizzo IP virtuale del pool Front end o front-end)</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Traffico SIP in uscita (da amministratore, indirizzo IP virtuale del pool di Director, Front End Server o indirizzo IP virtuale del pool Front End) a VIP Edge interno</p></td>
</tr>
<tr class="even">
<td><p>Accesso/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Qualsiasi (può essere definito come amministratore, indirizzo IP virtuale del pool di server Director, indirizzo IP virtuale del pool Front end o front-end)</p></td>
<td><p>Traffico SIP in ingresso (per il server Director, l'indirizzo IP virtuale del pool di Director, l'indirizzo IP virtuale front-end o il pool Front End) dall'interfaccia interna del server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Percorso preferito per trasferimenti multimediali A/V tra utenti interni ed esterni</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni se non è possibile stabilire la comunicazione UDP. TCP viene utilizzato per il trasferimento di file e la condivisione del desktop</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interfaccia VIP interna del server perimetrale</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni se non è possibile stabilire la comunicazione UDP. TCP viene utilizzato per il trasferimento di file e la condivisione del desktop</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

