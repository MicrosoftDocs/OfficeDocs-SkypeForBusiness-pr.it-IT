---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-12_

tblPrincipal contiene tutte le entità, inclusi utenti, cartelle e gruppi.

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
<td><p>prinID</p></td>
<td><p>int, not null</p></td>
<td><p>ID entità.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID principale. Questa operazione viene ampiamente usata come chiave primaria alternativa perché il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory. Il GUID di un'entità memorizzata nella cache è uguale al GUID dell'oggetto Active Directory corrispondente.</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>URI principale. Lo schema SIP viene usato per gli utenti e ma-GRP viene usato per quasi tutto il resto.</p></td>
</tr>
<tr class="even">
<td><p>prinname</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome comune. Usato solo dai tipi di utente.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Nome visualizzato. Usato solo dai tipi di utente.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome società. Usato solo dai tipi di utente.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Posta elettronica. Usato solo dai tipi di utente.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Nome di dominio dell'oggetto Active Directory in cui l'entità è una versione memorizzata nella cache. Può essere null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome dell'entità utente (UPN) dell'utente. Usato solo dai normali tipi di utente.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint e non null</p></td>
<td><ul>
<li><p>0: Principal è attivo.</p></li>
<li><p>1: Principal è disabilitato perché le funzionalità SIP dell'utente sono disabilitate.</p></li>
<li><p>2: Principal viene eliminato perché l'oggetto Active Directory associato è stato eliminato.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint e non null</p></td>
<td><p>Tipo di entità (dalla tabella tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>Assegnazione Lync pool per l'entità.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Valore dei criteri del server di chat persistente per l'utente, se è presente il criterio tipo di tag.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>ID principale del creatore.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint e non null</p></td>
<td><p>Indicatore di data e ora per la creazione.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>ID dell'oggetto Principal che ha aggiornato l'ultimo aggiornamento.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint e non null</p></td>
<td><p>Indicatore di data e ora per l'ultimo aggiornamento.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>DateTime, not null</p></td>
<td><p>Data e ora dell'ultimo aggiornamento della sincronizzazione di Active Directory per l'entità.</p></td>
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
<td><p>prinID</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblPrincipalType. ptypeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

