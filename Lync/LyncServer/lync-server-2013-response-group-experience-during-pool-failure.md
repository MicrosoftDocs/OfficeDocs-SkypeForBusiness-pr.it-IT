---
title: 'Lync Server 2013: Esperienza dei Response Group durante un errore del pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Esperienza dei Response Group in Lync Server 2013 durante un errore del pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

Questa sezione descrive in dettaglio l'influenza delle attività di gruppo di risposta nelle fasi seguenti:

  - Si verifica un'interruzione nel pool principale, ma il failover non è ancora stato avviato.

  - Il servizio non viene superato nel pool di backup.

  - Il servizio non viene restituito al pool principale.

<div>

## <a name="user-experience-when-outage-occurs"></a>Esperienza utente quando si verifica un'interruzione

Quando si verifica un'interruzione del pool o del sito, ma l'amministratore non ha ancora avviato il failover, l'attività di Response Group viene gestita come descritto nella tabella seguente.

<div>


> [!NOTE]  
> Durante il ripristino di emergenza, le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario vengano importati nel pool di backup durante il ripristino Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.



</div>

### <a name="outage-occurs"></a>Si verifica un'interruzione

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di azione chiamata o utente</th>
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
<td><p>In corso le chiamate non ancora connesse a un agente</p></td>
<td><p>Le chiamate vengono disconnesse.</p></td>
</tr>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><ul>
<li><p>Le chiamate vengono disconnesse.</p></li>
<li><p>Se i gruppi di risposta sono stati importati, chiama Connetti al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate agente per conto di Response Group</p></td>
<td><p>La caratteristica è disabilitata durante questa fase.</p></td>
</tr>
<tr class="odd">
<td><p>Informazioni sull'accesso e sull'agente dell'agente</p></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</p></li>
<li><p>I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configurazione di Response Group</p></td>
<td><ul>
<li><p>I gruppi di risposta di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool principale, ma non possono essere modificati.</p></li>
<li><p>I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Esperienza utente durante il failover

Quando un amministratore richiama il failover in un pool di backup, le attività di Response Group vengono gestite durante e dopo il failover, come descritto nella tabella seguente. La prima colonna descrive il tipo di attività che potrebbe essere in atto. La colonna centrale descrive il modo in cui ogni attività viene gestita durante il breve periodo di tempo necessario per il failover del pool di backup. L'ultima colonna descrive il modo in cui viene gestita l'attività per la durata, dopo il completamento del processo di failover e il pool di backup per il pool principale.

<div>


> [!NOTE]  
> Durante il ripristino di emergenza, le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario vengano importati nel pool di backup durante il ripristino Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.



</div>

### <a name="failover-is-initiated"></a>Il failover viene avviato

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di azione chiamata o utente</th>
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
<li><p>Per i gruppi di risposta importati, le chiamate anonime che hanno raggiunto il pool di backup restano connesse.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>In corso le chiamate non ancora connesse a un agente</p></td>
<td><p>Le chiamate vengono disconnesse.</p></td>
<td><ul>
<li><p>Se i gruppi di risposta non sono stati importati, non sono presenti chiamate in questo stato.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate che hanno raggiunto il pool di backup restano connesse.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><ul>
<li><p>Le chiamate vengono disconnesse.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate si connettono al pool di backup, ma gli agenti ospitati nel pool principale sono irraggiungibili.</p></li>
</ul></td>
<td><ul>
<li><p>Se i gruppi di risposta non sono stati importati, le chiamate vengono disconnesse.</p></li>
<li><p>Per i gruppi di risposta importati, chiama Connetti al pool di backup.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate agente per conto di Response Group</p></td>
<td><p>La caratteristica è disabilitata durante questa fase</p></td>
<td><ul>
<li><p>Se i gruppi di risposta non vengono importati, le chiamate non riescono.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate hanno successo.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Informazioni sull'accesso e sull'agente dell'agente</p></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</p></li>
<li><p>I gruppi di agenti importati vengono visualizzati nella console agente e gli agenti possono accedere.</p></li>
</ul></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</p></li>
<li><p>I gruppi di agenti importati vengono visualizzati nella console agente e gli agenti possono accedere.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configurazione di Response Group</p></td>
<td><ul>
<li><p>I gruppi di risposta di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool principale, ma non possono essere modificati.</p></li>
<li><p>I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
<td><ul>
<li><p>I gruppi di risposte di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end, ma non possono essere modificati.</p></li>
<li><p>I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Esperienza utente durante il failback

Quando un amministratore richiama il failback nel pool principale, le attività di Response Group vengono gestite durante e dopo il failback, come descritto nella tabella seguente.

<div>


> [!NOTE]  
> Durante il ripristino di emergenza, le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario vengano importati nel pool di backup durante il ripristino Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.



</div>

### <a name="call-handling-in-failback"></a>Gestione delle chiamate in failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di azione chiamata o utente</th>
<th>Durante il failback</th>
<th>Dopo il completamento del failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate connesse a un agente</p></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Se i gruppi di risposta non sono stati importati, non sono presenti chiamate anonime in questo stato.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate anonime restano connesse.</p></li>
</ul></td>
<td><ul>
<li><p>Le chiamate regolari restano connesse.</p></li>
<li><p>Se i gruppi di risposta non sono stati importati, non sono presenti chiamate anonime in questo stato.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate anonime restano connesse.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>In corso le chiamate non ancora connesse a un agente</p></td>
<td><ul>
<li><p>Se i gruppi di risposta non sono stati importati, non sono presenti chiamate in questo stato.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate verranno disconnesse.</p></li>
</ul></td>
<td><ul>
<li><p>Se i gruppi di risposta non sono stati importati, non sono presenti chiamate in questo stato.</p></li>
<li><p>Per i gruppi di risposta importati, le chiamate verranno disconnesse.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><p>Chiamate connettersi al pool principale, ma gli agenti ospitati nel pool principale sono irraggiungibili.</p></td>
<td><p>Chiama Connetti al pool principale.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate agente per conto di Response Group</p></td>
<td><p>La caratteristica è disabilitata durante questa fase.</p></td>
<td><p>Le chiamate hanno esito positivo.</p></td>
</tr>
<tr class="odd">
<td><p>Informazioni sull'accesso e sull'agente dell'agente</p></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</p></li>
<li><p>I gruppi di agenti importati vengono visualizzati nella console agente e gli agenti possono accedere.</p></li>
</ul></td>
<td><ul>
<li><p>I gruppi di agenti di proprietà del pool principale possono essere visualizzati nella console dell'agente e gli agenti possono accedere.</p></li>
<li><p>I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</p></li>
<li><p>I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configurazione di Response Group</p></td>
<td><ul>
<li><p>I gruppi di risposta di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool principale, ma non possono essere modificati.</p></li>
<li><p>I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</p></li>
</ul></td>
<td><ul>
<li><p>I gruppi di risposte di proprietà del pool primario possono essere visualizzati e modificati.</p></li>
<li><p>I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</p></li>
<li><p>I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</p></li>
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

