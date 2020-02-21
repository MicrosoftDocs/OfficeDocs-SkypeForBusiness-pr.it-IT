---
title: 'Lync Server 2013: visualizzazione conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a>Visualizzazione conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

La visualizzazione conferenze archivia le informazioni sulle conferenze. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numero ID per identificare la sessione. Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI della conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo dell'URI della conferenza. Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Utilizzato per le conferenze ricorrenti. Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri ma una ConfInstance diversa.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Ora di inizio della conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Ora di fine della conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI dell'utente che ha organizzato la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OrganizerType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di URI dell'utente che ha organizzato la conferenza. Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tenant dell'utente che ha organizzato la conferenza. Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome di dominio completo del pool che ha ospitato la conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bandiera</strong></p></td>
<td><p>smallint</p></td>
<td><p>Maschera di bit che contiene gli attributi di conferenza. I valori possibili sono:</p>
<p>0X01 – transazione sintetica</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

