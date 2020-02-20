---
title: 'Lync Server 2013: requisiti hardware e software per il Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff5e28b21e06cc438c7eb092515443579f5c004
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Requisiti hardware e software per il Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

In questa sezione vengono illustrati i requisiti hardware e software per il server Director e gli scenari di collocazione supportati per il server Director.

<div>

## <a name="hardware-requirements-for-the-director"></a>Requisiti hardware per il server Director

Nella tabella seguente sono elencati i requisiti hardware per il server Director:

### <a name="hardware-requirements-for-the-director"></a>Requisiti hardware per il server Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Requisito minimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>Processore a 64 bit, quad-core, 2.0 GHz o superiore</p></li>
<li><p>Processore doppio a 64 bit, dual-core, 2.0 GHz o superiore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>4 gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>Unità disco rigido 10K RPM</p></li>
<li><p>Unità SSD (Solid State Drive) ad alte prestazioni, equivalenti o superiori rispetto alle unità disco rigido 10K RPM</p></li>
<li><p>Dischi 2x RAID 10 (con striping e mirroring) 15K RPM per file di dati del database</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>Scheda di rete doppia a 1 gigabit al secondo (Gbps) (consigliata)</p></li>
<li><p>Scheda di rete singola a 1 Gbps (supportata)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Requisiti software per il server Director

Il ruolo di Director può essere distribuito solo sui server che eseguono Lync Server 2013 Enterprise Edition.

Per i direttori è necessario uno dei seguenti sistemi operativi a 64 bit:

  - Sistema operativo Windows Server 2008 R2 Standard con Service Pack 1

  - Sistema operativo Windows Server 2008 R2 Enterprise con Service Pack 1

  - Sistema operativo Windows Server 2008 R2 Datacenter con Service Pack 1

  - Sistema operativo Windows Server 2012 standard

  - Sistema operativo Windows Server 2012 Datacenter

Lync Server 2013 richiede inoltre l'installazione dei programmi e degli aggiornamenti seguenti descritti nell'argomento [additional server support and requirements in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Collocazione supportata

Il ruolo server Director non può essere collocato con qualsiasi altro ruolo del server in Lync Server 2013. Tuttavia, se non si distribuisce un Director, i Front End Server assumeranno il ruolo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

