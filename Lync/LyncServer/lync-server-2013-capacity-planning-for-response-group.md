---
title: 'Lync Server 2013: Pianificazione della capacità per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Pianificazione della capacità per Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

<div id="sectionSection0" class="section">

La tabella seguente descrive il modello di Response Group User che puoi usare come base per i requisiti di pianificazione della capacità.

<div>


> [!NOTE]  
> I numeri nella tabella seguente presuppongono l'uso di file wave 16 kHz, mono, a 16 bit (WAV) per tutti i file audio del gruppo di risposte. Se si usano altri formati di file, ad esempio Windows Media Audio (WMA), i numeri possono variare.



</div>

<div>


> [!IMPORTANT]  
> Tieni presente che per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per tutti i gruppi di risposta in entrambi i pool.



</div>

### <a name="response-group-user-model"></a>Modello di Response Group User

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrica</th>
<th>Per pool Enterprise Edition (con 8 server front-end)</th>
<th>Per server Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate in arrivo al secondo</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Chiamate simultanee connesse a IVR o MoH</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sessioni anonime simultanee (senza messaggi istantanei)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Sessioni anonime simultanee (con messaggistica istantanea)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Agenti attivi (formali e informali)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Numero di gruppi di ricerca</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Numero di gruppi IVR (usare il riconoscimento vocale)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

