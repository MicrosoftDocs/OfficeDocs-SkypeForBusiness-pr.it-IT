---
title: 'Lync Server 2013: assegnazione dei criteri di presenza per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905065e231869b4b6075fc1894e51c91df8f0aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Assegnazione di criteri di presenza per utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-11_

Un criterio di presenza è un insieme di limiti e restrizioni che influiscono sulla presenza. La tabella seguente descrive le impostazioni dei criteri di presenza disponibili in Lync Server 2013.

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
<td><p>Numero massimo di abbonamenti alle categorie del Sottoscrittore</p></td>
<td><p>Limita il numero di abbonamenti alle categorie di abbonati. Ad esempio, quando Communicator sottoscrive la presenza di un utente, ottiene un abbonamento a categoria per ogni scheda contatto, dati del calendario, note, servizi e categorie di stato.</p>
<p>Un'impostazione pari a 0 indica che l'utente o l'oggetto contatto non può essere sottoscritto da altri.</p>
<div>

> [!NOTE]  
> Questa impostazione può avere un impatto significativo sulle prestazioni se è impostata su un numero alto e l'utente medio ha un numero elevato di utenti che si abbonano alla propria presenza.


</div></td>
<td><p>Numero intero</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Numero massimo di avvisi per gli abbonamenti alla presenza in coda</p></td>
<td><p>Limita il numero di voci nella tabella abbonati richiesto. Questa impostazione determina il numero massimo di richieste che possono essere accodate per un determinato utente. Ad esempio, quando un utente sottoscrive la presenza dell'utente B, l'utente B riceverà una richiesta di conferma che l'utente a è ora abbonato all'utente B e viene creata una richiesta di conferma nella tabella sottoscrittori richiesto dall'utente B. Dopo che l'utente B accetta o riconosce l'abbonamento, la richiesta di conferma viene rimossa dalla tabella sottoscrittori richiesta dall'utente B.</p>
<p>Un'impostazione pari a 0 indica che l'utente non viene visualizzato quando qualcuno sottoscrive la propria presenza.</p></td>
<td><p>Numero intero o token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Per impostazione predefinita, i **criteri** e il servizio predefiniti: i criteri di presenza **media** vengono installati quando si distribuisce Lync Server. La tabella seguente descrive le impostazioni specifiche dei due criteri di presenza.

### <a name="presence-policies"></a>Criteri di presenza

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome del criterio</th>
<th>Descrizione</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criteri predefiniti</p></td>
<td><p>Criteri per gli utenti tipici. Questo è il criterio di presenza predefinito.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Servizio: media</p></td>
<td><p>Criteri per le applicazioni che richiedono ad altri utenti di sottoscrivere la presenza dell'oggetto.</p></td>
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

