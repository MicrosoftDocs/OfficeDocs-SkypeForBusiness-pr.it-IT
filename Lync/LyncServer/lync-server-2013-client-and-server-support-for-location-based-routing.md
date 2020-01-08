---
title: 'Lync Server 2013: Supporto per client e server per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Supporto per client e server per il routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-06-18_

Il routing basato sulla posizione viene applicato da Lync Server. Lync Server può identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale. Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.

<div>

## <a name="lync-server-support"></a>Supporto di Lync Server

Il routing basato sulla posizione richiede che Lync Server 2013 CU1 sia distribuito in tutti i pool Front end e nei server Standard Edition in una determinata topologia. Se Lync Server 2013 CU1 non è installato in alcuni componenti Lync della topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente.

La tabella seguente identifica la combinazione di ruoli server e versioni supportate per il routing basato sulla posizione.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Versione pool</th>
<th>Versione Mediation Server</th>
<th>Supportati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</p></td>
<td><p>Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>non</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>non</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>qualsiasi</p></td>
<td><p>non</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>qualsiasi</p></td>
<td><p>non</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>qualsiasi</p></td>
<td><p>non</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Supporto client Lync

La tabella seguente identifica i client supportati dal routing basato sulla posizione.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di client</th>
<th>Supportati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sì</p></td>
<td><p>Incluso l'aggiornamento cumulativo di Lync 2013 febbraio 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Sì</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>non</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Sì</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Assistente di Lync</p></td>
<td><p>Sì</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync per Windows 8</p></td>
<td><p>non</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>non</p></td>
<td><p>Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se usato dagli utenti con il routing basato sulla posizione abilitato.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>Sì</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Per disabilitare il VoIP per i client di Lync Mobile 2013, assegnare un criterio di mobilità con l'impostazione, l'audio/video IP, disabilitato per tutti gli utenti abilitati per il routing basato sulla posizione. Per altre informazioni sui criteri di mobilità, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

