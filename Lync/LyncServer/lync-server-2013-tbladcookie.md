---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>tblADCookie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-25_

tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.

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
<td><p>prinGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID principale del dominio da monitorare.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Nome di dominio completo (FQDN) del controller di dominio corrente usato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>immagine (binario)</p></td>
<td><p>Cookie di sincronizzazione di Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>DateTime</p></td>
<td><p>Indicatore di data e ora con il tempo di aggiornamento delle righe.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>DateTime</p></td>
<td><p>Ora fino a quando la riga non viene bloccata per le modifiche. Questo fa parte di un meccanismo di blocco software che garantisce che solo uno dei servizi di chat esegue la sincronizzazione di Active Directory alla volta.</p></td>
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
<th>Colonne</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Chiave esterna con ricerca nella tabella Principal. prinGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

