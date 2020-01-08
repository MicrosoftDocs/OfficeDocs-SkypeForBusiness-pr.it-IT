---
title: 'Lync Server 2013: visualizzazione VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Visualizzazione VoIPDetails in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La visualizzazione VoIPDetails contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI telefono dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Telefono</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI telefono dell'utente che ha partecipato alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI dell'utente che ha scollegato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di URI dell'utente che ha scollegato la sessione. Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tenant dell'utente che ha scollegato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI telefono dell'utente che ha scollegato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mediation Server usato dall'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mediation Server usato dall'utente che ha partecipato alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Gateway usato dall'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Togateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Gateway usato dall'utente che ha partecipato alla sessione.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

