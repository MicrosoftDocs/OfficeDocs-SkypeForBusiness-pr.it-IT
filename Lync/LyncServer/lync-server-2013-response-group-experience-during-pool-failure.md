---
title: Esperienza di Response Group di Lync Server 2013 durante un errore del pool
description: Esperienza di Response Group di Lync Server 2013 durante un errore del pool.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564572"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Esperienza di Response Group in Lync Server 2013 durante un errore del pool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

In questa sezione viene descritto in dettaglio in che modo l'attività Response Group è intaccata nelle fasi seguenti:

  - Si verifica un'interruzione nel pool primario, ma il failover non è stato ancora avviato.

  - Il servizio non viene eseguito nel pool di backup.

  - Il servizio non viene ripristinato nel pool primario.

<div>

## <a name="user-experience-when-outage-occurs"></a>Esperienza utente quando si verifica un'interruzione

Quando si verifica un'interruzione del pool o del sito, ma l'amministratore non ha ancora avviato il failover, l'attività dei Response Group viene gestita come descritto nella tabella seguente.

<div>


> [!NOTE]  
> Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.



</div>

### <a name="outage-occurs"></a>Si verifica un'interruzione

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di chiamata o azione dell'utente</th>
<th>Durante l'interruzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate connesse a un agente</p></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Le chiamate anonime vengono disconnesse.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate in corso non ancora connesse a un agente</p></td>
<td><p>Le chiamate vengono disconnesse.</p></td>
</tr>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><ul>
<li><p>Le chiamate vengono disconnesse.</p></li>
<li><p>Se i Response Group sono stati importati, le chiamate si connettono al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate agente per conto di Response Group</p></td>
<td><p>La funzionalità è disabilitata in questa fase.</p></td>
</tr>
<tr class="odd">
<td><p>Accesso dell'agente e informazioni sull'agente</p></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configurazione di Response Group</p></td>
<td><ul>
<li><p>I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</p></li>
<li><p>I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Esperienza utente durante il failover

Quando un amministratore richiama il failover su un pool di backup, l'attività dei Response Group viene gestita durante e dopo il failover come descritto nella tabella seguente. Nella prima colonna viene descritto il tipo di attività che potrebbe essere in corso. Nella colonna centrale viene descritto il modo in cui ogni attività viene gestita durante il breve periodo di tempo necessario per eseguire il failover del pool di backup. Nell'ultima colonna viene descritto il modo in cui l'attività viene gestita per la durata, dopo il completamento del processo di failover e il pool di backup per il pool primario.

<div>


> [!NOTE]  
> Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.



</div>

### <a name="failover-is-initiated"></a>Il failover è stato avviato

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di chiamata o azione dell'utente</th>
<th>Durante il failover</th>
<th>Dopo il completamento del failover</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate connesse a un agente</p></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Le chiamate anonime vengono disconnesse.</p></li>
</ul></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Per i Response Group importati, le chiamate anonime che hanno raggiunto il pool di backup restano connesse.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate in corso non ancora connesse a un agente</p></td>
<td><p>Le chiamate vengono disconnesse.</p></td>
<td><ul>
<li><p>Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</p></li>
<li><p>Per i Response Group importati, le chiamate che hanno raggiunto il pool di backup restano connesse.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><ul>
<li><p>Le chiamate vengono disconnesse.</p></li>
<li><p>Per i Response Group importati, le chiamate vengono connesse al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</p></li>
</ul></td>
<td><ul>
<li><p>Se i Response Group non sono stati importati, le chiamate vengono disconnesse.</p></li>
<li><p>Per i Response Group importati, le chiamate vengono connesse al pool di backup.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate agente per conto di Response Group</p></td>
<td><p>La funzionalità è disabilitata durante questa fase</p></td>
<td><ul>
<li><p>Se i Response Group non sono stati importati, le chiamate vengono eseguite correttamente.</p></li>
<li><p>Per i Response Group importati, le chiamate vengono eseguite correttamente.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Accesso dell'agente e informazioni sull'agente</p></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</p></li>
</ul></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configurazione di Response Group</p></td>
<td><ul>
<li><p>I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</p></li>
<li><p>I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
<td><ul>
<li><p>I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end, ma non possono essere modificati.</p></li>
<li><p>I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Esperienza utente durante il failback

Quando un amministratore richiama il failback al pool primario, l'attività del gruppo di risposta viene gestita durante e dopo il failback come descritto nella tabella seguente.

<div>


> [!NOTE]  
> Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.



</div>

### <a name="call-handling-in-failback"></a>Gestione delle chiamate nel failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di chiamata o azione dell'utente</th>
<th>Durante il failback</th>
<th>Dopo il completamento del failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate connesse a un agente</p></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Se i Response Group non sono stati importati, non ci sono chiamate anonime in questo stato.</p></li>
<li><p>Per i Response Group importati, le chiamate anonime restano connesse.</p></li>
</ul></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Se i Response Group non sono stati importati, non ci sono chiamate anonime in questo stato.</p></li>
<li><p>Per i Response Group importati, le chiamate anonime restano connesse.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate in corso non ancora connesse a un agente</p></td>
<td><ul>
<li><p>Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</p></li>
<li><p>Per i Response Group importati, le chiamate vengono disconnesse.</p></li>
</ul></td>
<td><ul>
<li><p>Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</p></li>
<li><p>Per i Response Group importati, le chiamate vengono disconnesse.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><p>Le chiamate si connettono al pool primario, ma gli agenti ospitati nel pool primario non sono raggiungibili.</p></td>
<td><p>Le chiamate si connettono al pool primario.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate agente per conto di Response Group</p></td>
<td><p>La funzionalità è disabilitata in questa fase.</p></td>
<td><p>Le chiamate hanno esito positivo.</p></td>
</tr>
<tr class="odd">
<td><p>Accesso dell'agente e informazioni sull'agente</p></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</p></li>
</ul></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configurazione di Response Group</p></td>
<td><ul>
<li><p>I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</p></li>
<li><p>I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
<td><ul>
<li><p>I Response Group di proprietà del pool primario possono essere visualizzati e modificati.</p></li>
<li><p>I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

