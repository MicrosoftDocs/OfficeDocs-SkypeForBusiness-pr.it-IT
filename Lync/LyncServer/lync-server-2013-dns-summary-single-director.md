---
title: 'Lync Server 2013: Riepilogo DNS-singolo server Director'
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
ms.openlocfilehash: d1eaaebf1fb695bc1ee6ea1b86f980a666cf0a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515533"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a>Riepilogo DNS-singolo Director in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

La tabella seguente contiene un riepilogo dei record DNS necessari per il supporto del singolo Director. Il ruolo del Director richiede record DNS simili a quelli del front end server. Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director. Diverso dal front end server, il Director non ospita gli account utente o ospita i servizi per dispositivi mobili.

### <a name="dns-records-required-for-the-director"></a>Record DNS necessari per il server Director

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
<th>FQDN/Record DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Record host Director utilizzato per la replica e il server in server</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>SIP (Session Initiation Protocol) in ingresso dall'interfaccia perimetrale interna del server perimetrale</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servizi Web Accesso esterno pubblicati da proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servizi Web Accesso Riunione pubblicati da proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Pubblicati e definiti dai servizi Web esterni per il proxy inverso per il server Director</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

