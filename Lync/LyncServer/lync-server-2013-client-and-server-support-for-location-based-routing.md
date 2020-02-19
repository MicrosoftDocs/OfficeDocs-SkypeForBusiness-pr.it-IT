---
title: 'Lync Server 2013: supporto per client e server per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d78ae3fcfe9bd834fbddced1bdeccc20be45481
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Supporto per client e server per il routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-06-18_

Il routing in base alla posizione viene applicato da Lync Server. Lync Server è in grado di identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale. Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.

<div>

## <a name="lync-server-support"></a>Supporto di Lync Server

Il routing in base alla posizione richiede che Lync Server 2013 CU1 sia distribuito su tutti i pool Front end e i server Standard Edition in una determinata topologia. Se Lync Server 2013 CU1 non è installato in alcuni componenti di Lync nella topologia, non è possibile applicare completamente le restrizioni relative al routing basato sulla posizione.

La tabella seguente identifica la combinazione di ruoli del server e versioni supportate per il routing in base alla posizione.


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
<th>Supportato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 febbraio 2013 aggiornamento cumulativo</p></td>
<td><p>Lync Server 2013 febbraio 2013 aggiornamento cumulativo</p></td>
<td><p>sì</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 febbraio 2013 aggiornamento cumulativo</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 febbraio 2013 aggiornamento cumulativo</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 febbraio 2013 aggiornamento cumulativo</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>qualsiasi</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>qualsiasi</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>qualsiasi</p></td>
<td><p>no</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Supporto per client Lync

Nella tabella seguente vengono identificati i client supportati dal routing basato sulla posizione.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di client</th>
<th>Supportato</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>sì</p></td>
<td><p>Incluso Lync 2013 febbraio 2013 Cumulative Update</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>sì</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>no</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>sì</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>sì</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync per Windows 8</p></td>
<td><p>no</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>no</p></td>
<td><p>Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se utilizzato dagli utenti con il routing basato sulla posizione abilitato.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>sì</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Per disabilitare VoIP per i client Lync Mobile 2013, assegnare un criterio per dispositivi mobili con l'impostazione, IP audio/video, disabilitato per tutti gli utenti abilitati per il routing in base alla posizione. Per ulteriori informazioni sui criteri per dispositivi mobili, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



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

