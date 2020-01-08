---
title: 'Lync Server 2013: Piattaforme hardware server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2682d0d8636c024dee4151842a143e65b11d48c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Piattaforme hardware server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-07-28_

I ruoli server e i computer di Lync Server 2013 che eseguono gli strumenti di amministrazione di Lync Server richiedono hardware a 64 bit.

L'hardware specifico usato per la distribuzione di Lync Server 2013 può variare a seconda delle dimensioni e dei requisiti di utilizzo. Questa sezione descrive l'hardware consigliato. Anche se si tratta di raccomandazioni, non di requisiti, l'uso di hardware che non soddisfa questi suggerimenti può causare problemi di prestazioni significativi e altri problemi.

<div>

## <a name="recommended-hardware-platform"></a>Piattaforma hardware consigliata

Per ottenere prestazioni ottimali, è consigliabile eseguire Lync Server nei server con hardware che soddisfi i requisiti della tabella seguente. Se usi hardware meno potente, potresti riscontrare problemi di funzionalità o prestazioni scarse. Si noti che questi requisiti hardware sono superiori a quelli delle versioni precedenti di Lync Server, principalmente perché in Lync Server 2013 tutti i server front-end eseguono SQL Server.

<div>


> [!NOTE]  
> Il teaming di NIC è supportato e deve essere trasparente per Lync Server. Per informazioni dettagliate, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server o Lync Server e Network Adapter Teaming</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Hardware consigliato per i server front-end, i server di back-end, i server Standard Edition, i server di chat persistenti e l'Archivio Chat persistente e lo Store di conformità della chat persistente (ruoli del server back-end per il server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Consigliato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64-bit Dual Processor, hex-core, 2,26 gigahertz (GHz) o versioni successive.</p>
<p>I processori Intel Itanium non sono supportati per i ruoli di Lync Server Server.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabyte (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</p>
<p>Due dischi dovrebbero usare RAID 1 e sei dovrebbero usare RAID 10.</p>
<p>-O</p></li>
<li><p>SSD (Solid State Drive) che garantiscono prestazioni simili alle unità disco meccaniche di 8 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP).</p>
<div>

> [!NOTE]  
> Le configurazioni dual o multihomed non sono supportate per i server front-end, i server back-end, i server Standard Edition e i server di chat permanenti.<BR>Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e usate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e quindi sono supportate.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Hardware consigliato per Edge Server, Mediation Server autonomi e direttori

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Consigliato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64-bit Dual Processor, quad-core, 2,0 gigahertz (GHz) o versioni successive.</p>
<p>-O</p></li>
<li><p>processore a 4 vie a 64 bit, Dual-Core, 2,0 GHz o superiore.</p></li>
</ul>
<p>I processori Intel Itanium non sono supportati per i ruoli di Lync Server Server.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>16 gigabyte (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>4 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</p>
<p>I dischi devono essere in una configurazione di 2x RAID 1.</p>
<p>-O</p></li>
<li><p>SSD (Solid State Drive) che garantiscono prestazioni simili alle unità disco meccaniche di 4 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP). 2 le interfacce di rete sono necessarie in Edge Server e sono supportate nei server di mediazione autonomi.</p></li>
</ul>
<div>

> [!NOTE]  
> Le configurazioni dual o multihomed non sono supportate per gli amministratori.<BR>Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e usate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e quindi sono supportate.


</div>
<p>I server perimetrali richiedono due interfacce di rete che sono schede di rete a doppia porta, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ogni coppia che viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).</p>
<p>L'installazione di schede di interfaccia di rete aggiuntive (NIC) per consentire la configurazione di un indirizzo IP PSTN specifico è supportata nei server di mediazione autonomi.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

