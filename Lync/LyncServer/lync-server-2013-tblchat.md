---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620dcb49580f8d19a8f262c22b1005e3cefeac4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-12_

tblChat contiene tutti i messaggi di chat.

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
<td><p>ID nodo.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint e non null</p></td>
<td><p>Numero sequenziale univoco (per ID nodo) che definisce l'ordine della chat room generato dalla tabella tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint e non null</p></td>
<td><p>Indicatore di data e ora per il messaggio di chat.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, not null</p></td>
<td><p>ID principale del poster.</p></td>
</tr>
<tr class="odd">
<td><p>Messaggio di avviso</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il messaggio è un messaggio di avviso. False se non lo è.</p></td>
</tr>
<tr class="even">
<td><p>contenuto</p></td>
<td><p>nvarchar (max), not null</p></td>
<td><p>Contenuto della chat (la versione in formato testo normale). Il contenuto è in genere in testo normale con le eccezioni seguenti:</p>
<ul>
<li><p>I file sono rappresentati come ma-filelink: collegamenti.</p></li>
<li><p>I collegamenti sono rappresentati come elemento HTML (anche se il tipo di contenuto non può essere considerato HTML).</p></li>
<li><p>Le storie sono codificate come formato "[storia]...."-like.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>RTF</p></td>
<td><p>varchar (max)</p></td>
<td><p>Contenuto della chat (la versione RTF). Può essere null se il client non lo consente.</p></td>
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
<td><p>&lt;channelID, chat&gt;</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

