---
title: 'Lync Server 2013: Riepilogo di DNS - singolo server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>Riepilogo di DNS - singolo server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

La tabella seguente contiene un riepilogo dei record DNS necessari per supportare il singolo Director. Il ruolo del Director richiede record DNS simili al server front-end. Il numero di record necessari viene riflesso nei nomi alternativi del soggetto necessari per il certificato Director. Diverso dal server front-end, il Director non ospita gli account utente o ospita i servizi di mobilità.

### <a name="dns-records-required-for-the-director"></a>Record DNS necessari per il Director

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione/tipo/porta</th>
<th>Record FQDN/DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Record host Director usato per la replica e il server al server</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>SIP (Session Initiation Protocol) in ingresso dall'interfaccia Edge interna del server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servizi Web di dialin pubblicati da proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servizi Web pubblicati su Meet proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Pubblicato e definito dai servizi Web esterni per i Web Ticket proxy inverso per il direttore</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

