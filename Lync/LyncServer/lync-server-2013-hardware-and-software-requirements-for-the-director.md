---
title: 'Lync Server 2013: Requisiti hardware e software per il server Director'
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
ms.openlocfilehash: 52d91a739935b2e42bb925d5645350c5875e5b43
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Requisiti hardware e software per il server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

In questa sezione vengono illustrati i requisiti hardware e software per il Director e gli scenari di collocazione supportati per il Director.

<div>

## <a name="hardware-requirements-for-the-director"></a>Requisiti hardware per il Director

La tabella seguente elenca i requisiti hardware per il Director:

### <a name="hardware-requirements-for-the-director"></a>Requisiti hardware per il Director

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
<li><p>processore a 64 bit, quad-core, 2,0 GHz o superiore</p></li>
<li><p>processore duale a 64 bit, Dual-Core, 2,0 GHz o superiore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>4 gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>unità disco rigido RPM 10K (HDD)</p></li>
<li><p>SSD (Solid State Drive) a prestazioni elevate con prestazioni pari o superiori a 10K RPM HDD</p></li>
<li><p>2x RAID 10 (con striping e mirroring) 15K RPM per i file di dati del database</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>Schede di rete dual 1 Gigabit per secondo (Gbps) (scelta consigliata)</p></li>
<li><p>Scheda di rete single 1 Gbps (supportata)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Requisiti software per il direttore

Il ruolo Director può essere distribuito solo nei server che utilizzano Lync Server 2013 Enterprise Edition.

Per gli amministratori è necessario uno dei sistemi operativi a 64 bit seguenti:

  - Sistema operativo standard Windows Server 2008 R2 con Service Pack 1

  - Sistema operativo Windows Server 2008 R2 Enterprise con Service Pack 1

  - Sistema operativo Windows Server 2008 R2 Datacenter con Service Pack 1

  - Sistema operativo standard di Windows Server 2012

  - Sistema operativo Windows Server 2012 Datacenter

Lync Server 2013 richiede inoltre l'installazione dei programmi e degli aggiornamenti seguenti descritti nell'argomento [supporto e requisiti aggiuntivi del server in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Collocazione supportata

Il ruolo del server Director non può essere collocato con qualsiasi altro ruolo del server in Lync Server 2013. Tuttavia, se non si distribuisce un amministratore, i server front-end si assumeranno il ruolo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

