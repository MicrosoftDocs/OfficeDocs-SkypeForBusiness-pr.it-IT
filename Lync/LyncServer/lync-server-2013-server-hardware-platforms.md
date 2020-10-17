---
title: Piattaforme hardware del server Lync Server 2013
description: Piattaforme hardware server Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55deec50994d70cf305b794662a630c16c3af14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551382"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a>Piattaforme hardware server per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-28_

I ruoli del server e i computer Lync Server 2013 che eseguono gli strumenti di amministrazione di Lync Server richiedono hardware a 64 bit.

L'hardware specifico utilizzato per la distribuzione di Lync Server 2013 può variare a seconda delle dimensioni e dei requisiti di utilizzo. In questa sezione viene descritto l'hardware consigliato. Sebbene si tratti di suggerimenti e non di requisiti, l'utilizzo di hardware che non soddisfa tali indicazioni potrebbe generare rallentamenti significativi delle prestazioni e altri problemi.

<div>

## <a name="recommended-hardware-platform"></a>Piattaforma hardware consigliata

Per prestazioni ottimali, è consigliabile eseguire Lync Server nei server con hardware che soddisfi i requisiti indicati nella tabella seguente. Se si utilizzano componenti hardware meno potenti, è possibile che si verifichino problemi funzionali o di prestazioni insufficienti. Si noti che questi requisiti hardware sono superiori a quelli delle versioni precedenti di Lync Server, principalmente perché in Lync Server 2013 tutti i front end server eseguono SQL Server.

<div>


> [!NOTE]  
> Il teaming NIC è supportato e deve essere trasparente per Lync Server. Per informazioni dettagliate, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and Network Adapter Teaming</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Hardware consigliato per Front End Server, server back-end, server Standard Edition, server Chat persistente e archivio chat persistente e archivio conformità chat persistente (ruoli del server back-end per il server Chat persistente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Consigliata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore.</p>
<p>I processori Intel Itanium non sono supportati per i ruoli del server di Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabyte (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>Otto o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco</p>
<p>Due dei dischi dovrebbero utilizzare RAID 1 e sei dovrebbero utilizzare RAID 10.</p>
<p>- O</p></li>
<li><p>Unità SSD (Solid State Drive) con prestazioni simili a otto unità disco meccanico da 10.000 RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>1 scheda di rete Dual-Port, 1 Gbps o superiore (2 consigliate, che richiede la collaborazione con un singolo indirizzo MAC e un singolo indirizzo IP).</p>
<div>

> [!NOTE]  
> Le configurazioni dual o multi-homed non sono supportate per Front End Server, server back-end, server Standard Edition e server Chat persistente.<BR>Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e utilizzate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e pertanto sono supportate.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Hardware consigliato per server perimetrali, Mediation Server autonomi e server Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Consigliata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>processore duale a 64 bit, quad-core, 2,0 gigahertz (GHz) o superiore.</p>
<p>- O</p></li>
<li><p>processore a 4 vie a 64 bit, Dual Core, 2,0 GHz o superiore.</p></li>
</ul>
<p>I processori Intel Itanium non sono supportati per i ruoli del server di Lync Server.</p></td>
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
<p>- O</p></li>
<li><p>Unità SSD (Solid State Drive) con prestazioni simili a quattro unità disco meccanico da 10.000 RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>1 scheda di rete Dual-Port, 1 Gbps o superiore (2 consigliate, che richiede la collaborazione con un singolo indirizzo MAC e un singolo indirizzo IP). 2 le interfacce di rete sono necessarie nei server perimetrali e sono supportate su Mediation Server autonomi.</p></li>
</ul>
<div>

> [!NOTE]  
> Le configurazioni dual o multi-homed non sono supportate per i direttori.<BR>Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e utilizzate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e pertanto sono supportate.


</div>
<p>I server perimetrali richiedono due interfacce di rete che sono schede di rete Dual-Port, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ciascuna coppia viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).</p>
<p>L'installazione di altre schede di interfaccia di rete (NIC) per consentire la configurazione di un indirizzo IP PSTN specifico è supportata su Mediation Server autonomi.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

