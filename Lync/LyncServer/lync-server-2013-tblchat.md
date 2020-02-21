---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efadf0e5e850b825f6e5f47928e615ba32b9fd33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-12_

In tblChat sono inclusi tutti i messaggi di chat.

### <a name="columns"></a>Colonne

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelId</p></td>
<td><p>int, not null</p></td>
<td><p>ID del nodo.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, non null</p></td>
<td><p>Numero sequenziale univoco (per ID di nodo) che definisce l'ordine delle chat room, generato dalla tabella tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, not null</p></td>
<td><p>Timestamp per il messaggio chat.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, not null</p></td>
<td><p>ID di entità dell'autore del post.</p></td>
</tr>
<tr class="odd">
<td><p>Avviso di emergenza</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il messaggio è un messaggio di avviso. False in caso contrario.</p></td>
</tr>
<tr class="even">
<td><p>contenuto</p></td>
<td><p>nvarchar (max), not null</p></td>
<td><p>Contenuto della chat (versione in testo normale). Il contenuto è solitamente in testo normale con le eccezioni seguenti:</p>
<ul>
<li><p>I file sono rappresentati come collegamenti ma-filelink:.</p></li>
<li><p>I collegamenti sono rappresentati come elemento HTML (sebbene il tipo di contenuto non possa essere considerato HTML).</p></li>
<li><p>I brani sono codificati nel formato "[STORY]...."-like.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>RTF</p></td>
<td><p>varchar (massimo)</p></td>
<td><p>Contenuto della chat (versione RTF). Può essere Null se il client non lo fornisce.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Chiave

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelID, chatd&gt;</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

