---
title: 'Lync Server 2013: assegnazione dei criteri di presenza per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c169c6995ca49cc89742bd026b18dc254430cb9d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Assegnazione di criteri di presenza per utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-11_

Per criteri di presenza si intende un insieme di limiti e restrizioni che influiscono sulla presenza. Nella tabella seguente vengono descritte le impostazioni dei criteri di presenza disponibili in Lync Server 2013.

### <a name="presence-policy-settings"></a>Impostazioni dei criteri di presenza

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome XML</th>
<th>Nome visualizzato</th>
<th>Descrizione</th>
<th>Tipo</th>
<th>Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>Numero massimo di sottoscrizioni di categoria dei sottoscrittori</p></td>
<td><p>Limita il numero di sottoscrizioni di categoria dei sottoscrittori. Ad esempio, quando Communicator sottoscrive la presenza di un utente, ottiene una sottoscrizione di categoria per ogni categoria scheda contatto, dati del calendario, note, servizi e stato.</p>
<p>Un valore 0 indica che l'utente o l'oggetto contatto non può essere sottoscritto da altri.</p>
<div>

> [!NOTE]  
> Questa impostazione può avere un impatto notevole sulle prestazioni se è impostata su un valore elevato e l'utente medio presenta un numero elevato di utenti che sottoscrivono la sua presenza.


</div></td>
<td><p>Numero intero</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Numero massimo di avvisi di sottoscrizione presenza in coda</p></td>
<td><p>Limita il numero di voci nella tabella dei sottoscrittori richiedenti che possono essere accodati per un dato utente. Ad esempio, quando l'utente A sottoscrive la presenza dell'utente B, l'utente B riceve una richiesta che indica che l'utente A ha sottoscritto l'utente B e viene creata una richiesta di accettazione nella tabella dei sottoscrittori richiedenti dell'utente B. Dopo che l'utente B accetta la sottoscrizione, la richiesta di accettazione viene rimossa dalla tabella dei sottoscrittori richiedenti dell'utente B.</p>
<p>Un valore 0 indica che all'utente non viene inviata alcuna richiesta quando qualcuno sottoscrive la sua presenza.</p></td>
<td><p>Numero intero o token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Per impostazione predefinita, i **criteri** e il servizio predefiniti: i criteri di presenza **media** vengono installati quando si distribuisce Lync Server. Nella tabella seguente sono descritte le impostazioni specifiche dei due criteri di presenza.

### <a name="presence-policies"></a>Criterio di presenza

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome criterio</th>
<th>Descrizione</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criterio predefinito</p></td>
<td><p>Criterio per gli utenti tipici. Si tratta del criterio di presenza predefinito.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Servizio: Medio</p></td>
<td><p>Criterio per le applicazioni che richiedono più utenti che sottoscrivano la presenza dell'oggetto.</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

