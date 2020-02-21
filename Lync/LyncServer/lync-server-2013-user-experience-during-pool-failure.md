---
title: Esperienza utente di Lync Server 2013 durante l'errore del pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63bef718af5664c18ccedca7482e4ca0a0a7f95e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Esperienza utente durante un errore del pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Se si verifica il il failover di un pool, tutti gli utenti del pool interessato sono obbligati a disconnettersi e quindi a connettersi al pool di backup. Per un breve periodo di tempo, gli utenti che si connettono al pool di backup possono trovarsi in modalità Resilienza. In modalità di resilienza, gli utenti non sono in grado di eseguire attività che causerebbero una modifica permanente su Lync Server, ad esempio l'aggiunta di un contatto. Al termine del failover, tutti gli utenti possono ottenere tutti i servizi dal pool di backup.

Tutte le sessioni in corso per l'utente al momento del failover del pool vengono interrotte e, per proseguire, l'utente deve ristabilirle dopo il failover.

Gli utenti non vengono ricollocati durante il failover o il failback. Gli utenti che si trovano in un pool su cui si verifica un problema verranno infatti serviti temporaneamente dal pool di backup. Quando il pool principale viene ripristinato, l'amministratore può eseguire il failback di tali utenti in modo che vengano serviti di nuovo dal rispettivo pool principale originale.

Nota in Lync 2013, il database del server delle informazioni percorso non viene replicato nel pool di backup. Come procedura consigliata, l'amministratore dovrebbe eseguire con regolarità il backup del database LIS e utilizzare la copia di backup più recente per ripristinare tale database nel pool di backup dopo il failover.

<div>

## <a name="user-experience-during-failover"></a>Esperienza utente durante il failover

Quando un utente si trova in un pool su cui si verifica un problema, viene disconnesso. Tutte le sessioni peer-to-peer a cui l'utente stava partecipando vengono terminate, così come le conferenze che ha organizzato. L'utente non può riconnettersi finché non scade il timer di resilienza della funzione di registrazione o finché l'amministratore non avvia le procedure di failover, a seconda di quale di questi eventi avviene per primo. Quando l'utente si riconnette, si riconnetterà al pool di backup. Se si connette prima che il failover sia stato completato, sarà in modalità Resilienza fino al completamento del failover. Solo a quel punto l'utente potrà stabilire nuove sessioni o ristabilire le sessioni precedenti.

</div>

<div>

## <a name="user-experience-during-failback"></a>Esperienza utente durante il failback

Il failback del pool può avvenire mentre un utente interessato è connesso al pool di backup. L'utente rimane connesso e operativo durante il failback. Tale processo viene completato nel giro di diversi minuti. Come riferimento, è previsto che il failback richieda fino a 60 minuti per un pool di 20.000 utenti.

Nelle tabelle riportate di seguito vengono illustrati ulteriori dettagli sul modo in cui un utente con un client Lync 2013 o un client Microsoft Lync 2010 viene influenzato durante e dopo il failback e in che modo gli utenti in altri pool visualizzano e interagiscono con un utente in un pool di cui non è stato eseguito il failover. Gli utenti che dispongono di client Microsoft Office Communicator 2007 R2 non possono accedere fino a quando non è stato completamente eseguito il failover del pool Front end.

Con il termine *utente interessato* viene indicato qualsiasi utente di cui sia stato eseguito il failover dal pool principale e che venga servito dal pool di backup. Per definizione, gli utenti che si trovavano originariamente nel pool di backup non sono utenti interessati.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Esperienza utente per un utente interessato in un pool in corso di failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Stato o attività dell'utente</th>
<th>Durante il failback</th>
<th>Dopo il completamento del failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utente già connesso</p></td>
<td><p>L'utente resta connesso al pool di backup. A un certo punto l'utente verrà disconnesso e riconnesso al pool principale originale, in modalità Resilienza.</p></td>
<td><p>L'utente rimane connesso e passa alla modalità normale.</p></td>
</tr>
<tr class="even">
<td><p>Nuova connessione dell'utente</p></td>
<td><p>L'utente può connettersi al pool principale in modalità Resilienza.</p></td>
<td><p>L'utente può connettersi al pool principale originale in modalità normale.</p></td>
</tr>
<tr class="odd">
<td><p>Conferenze in corso organizzate dall'utente interessato</p></td>
<td><p>Tutte le modalità di conferenza vengono terminate. Viene visualizzato il pulsante Torna a partecipare, ma nessun utente può ripartecipare alla conferenza mentre l'utente interessato è in modalità Resilienza.</p></td>
<td><p>Tutte le modalità ora funzionano. Tutti i partecipanti devono fare clic sul pulsante per tornare a partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p>Conferenze in corso organizzate da un utente non interessato</p></td>
<td><p>La conferenza prosegue e l'utente interessato può continuare a parteciparvi, ma può eseguire esclusivamente le operazioni consentite in modalità Resilienza.</p></td>
<td><p>La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano dopo che l'utente esce dalla modalità Resilienza.</p></td>
</tr>
<tr class="odd">
<td><p>Pianificazione o modifica delle riunioni pianificate, creazione di conferenze ad hoc</p></td>
<td><p>Attività impossibili mentre l'utente è in modalità Resilienza.</p></td>
<td><p>Attività disponibili per tutte le modalità.</p></td>
</tr>
<tr class="even">
<td><p>Presenza come viene visualizzata da altri utenti dello stesso pool</p></td>
<td><p>Presenza sconosciuta mentre l'utente è connesso al pool di backup in modalità Resilienza.</p></td>
<td><p>Viene visualizzato l'ultimo stato di presenza impostato dall'utente. Le eventuali variazioni di tale stato ora saranno visibili.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilità dell'Elenco contatti e del Servizio Rubrica</p></td>
<td><p>Non disponibili</p></td>
<td><p>Disponibili</p></td>
</tr>
<tr class="even">
<td><p>Tutte le sessioni peer-to-peer e tutte le modalità</p></td>
<td><p>Disponibili</p></td>
<td><p>Disponibili</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Esperienza utente di un utente che si trova in un pool non interessato durante il failback di un altro pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attività dell'utente</th>
<th>Durante il failback</th>
<th>Dopo il completamento del failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Visualizzazione della presenza dell'utente interessato</p></td>
<td><p>Viene visualizzato l'ultimo stato di presenza impostato dall'utente interessato.</p></td>
<td><p>Funzionante. Gli utenti non interessati vedono le modifiche apportate dagli utenti interessati.</p></td>
</tr>
<tr class="even">
<td><p>Conferenze in corso organizzate dall'utente interessato</p></td>
<td><p>Tutte le modalità di conferenza vengono terminate.</p></td>
<td><p>Tutte le modalità ora funzionano. Tutti i partecipanti devono fare clic sul pulsante per tornare a partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p>Conferenze in corso organizzate da un utente non interessato</p></td>
<td><p>La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano.</p></td>
<td><p>La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano.</p></td>
</tr>
<tr class="even">
<td><p>Tutte le sessioni peer-to-peer e tutte le modalità</p></td>
<td><p>Disponibili</p></td>
<td><p>Disponibili</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

