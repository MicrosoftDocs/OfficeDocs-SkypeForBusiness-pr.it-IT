---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-12_

tblNode contiene l'albero di oggetti (con nodi Category o chat room) come gestito nel pannello di controllo di Lync Server 2013 e nei cmdlet amministrativi.

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
<td><p>nodeID</p></td>
<td><p>int, not null</p></td>
<td><p>ID nodo (numero univoco).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>ID nodo dell'elemento padre. Il nodo radice (con ID 1) si include anche come padre.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il nodo è una categoria.</p>
<p>False se il nodo è una chat room.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Nome del nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descrizione del nodo.</p></td>
</tr>
<tr class="odd">
<td><p>invitare</p></td>
<td><p>po'</p></td>
<td><p>Per le categorie:</p>
<ul>
<li><p>True se gli inviti sono attivati.</p></li>
<li><p>False se gli inviti sono spenti.</p></li>
</ul>
<p>Per le camere:</p>
<ul>
<li><p>False se gli inviti sono disattivati (esegue l'override della categoria padre).</p></li>
<li><p>Null se l'impostazione invita viene ereditata dalla categoria padre.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>connessi</p></td>
<td><p>po'</p></td>
<td><p>Per le categorie:</p>
<ul>
<li><p>True se la cronologia chat è attivata.</p></li>
<li><p>False se la cronologia chat è disinserita.</p></li>
</ul>
<p>Per le camere:</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>po'</p></td>
<td><p>Per le categorie:</p>
<ul>
<li><p>True se gli upload di file sono consentiti.</p></li>
<li><p>False se gli upload di file non sono consentiti.</p></li>
</ul>
<p>Per le camere:</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>disabilitato</p></td>
<td><p>bit, not null</p></td>
<td><p>True se la chat room è disabilitata. Si applica solo alle chat room. (False per le categorie)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>comportamento</p></td>
<td><p>smallint e non null</p></td>
<td><p>Comportamento (ricercato nella tabella EnumValue):</p>
<ul>
<li><p>4: normale (normale chat room).</p></li>
<li><p>5: Auditorium (auditorium chat room, solo i relatori possono collaborare).</p></li>
</ul>
<p>Si applica solo alle chat room.</p></td>
</tr>
<tr class="odd">
<td><p>visibilità</p></td>
<td><p>smallint e non null</p></td>
<td><p>Visibilità (ricercata nella tabella EnumValue):</p>
<ul>
<li><p>2: privato</p></li>
<li><p>3: ambito</p></li>
<li><p>6: aprire</p></li>
</ul>
<p>Si applica solo alle chat room.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>GUID del componente aggiuntivo se un componente aggiuntivo è associato a questa chat room. (Le categorie non hanno componenti aggiuntivi)</p>
<p>Le informazioni del componente aggiuntivo sono ricercate nella tabella SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, not null</p></td>
<td><p>ID dell'entità che ha creato questo nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint e non null</p></td>
<td><p>Indicatore di data e ora della creazione di nodi.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>ID dell'entità che ha eseguito l'aggiornamento più recente di questo nodo.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint e non null</p></td>
<td><p>Indicatore di data e ora dell'ultimo aggiornamento di questo nodo.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>DateTime</p></td>
<td><p>Ora dell'ultima operazione di eliminazione dei ripulimenti (rimozione degli ambiti da tabella tblScopedPrincipal e ruoli della tabella tblPrincipalRole) che hanno interessato questo nodo. Viene usato dal meccanismo di aggiornamento della cache interno del servizio chat.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Tasti

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
<td><p>nodeID</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
<tr class="even">
<td><p>comportamento</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblEnumValue. valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibilità</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblEnumValue. valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblNode. nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblSiopWhiteList. siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

