---
title: Esperienza utente di Lync Server 2013 durante l'errore del pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca33dc8f77ac697b7eea9cc89fee9aa401318566
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Esperienza utente durante l'errore del pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Se non è possibile eseguire il failover di un pool, tutti gli utenti del pool interessato saranno costretti a disconnettersi e quindi a eseguire l'accesso al pool di backup. Per un breve periodo gli utenti che accedono al pool di backup potrebbero essere in modalità resilienza. In modalità resilienza gli utenti non sono in grado di eseguire attività che causerebbero una modifica persistente in Lync Server, ad esempio l'aggiunta di un contatto. Al termine del failover, tutti gli utenti possono ottenere tutti i servizi dal pool di backup.

Tutte le sessioni che un utente ha quando il pool non riesce vengono interrotte e l'utente deve ristabilire tali sessioni dopo il failover per continuare.

Gli utenti non vengono reospitati durante il failover o il failback. Gli utenti ospitati in un pool che non riesce verranno temporaneamente serviti dal pool di backup. Quando il pool Home viene ripristinato, l'amministratore può eseguire il failover di questi utenti per essere serviti dal proprio pool di Home originale.

Nota in Lync 2013 il database del server delle informazioni sulla posizione non viene replicato nel pool di backup. Per le procedure consigliate, l'amministratore deve eseguire regolarmente il backup del database LIS e usare la copia di backup più recente per ripristinare il database LIS nel pool di backup dopo il failover.

<div>

## <a name="user-experience-during-failover"></a>Esperienza utente durante il failover

Quando un utente si trova in un pool che non riesce, l'utente viene disconnesso. Qualsiasi sessione peer-to-peer a cui l'utente ha partecipato viene terminata, così come le conferenze organizzate dall'utente. L'utente non può eseguire l'accesso finché non scade il timer di resilienza del registrar o l'amministratore avvia procedure di failover, a seconda di quale verrà prima. Quando l'utente esegue il log-in, eseguirà l'accesso al pool di backup. Se l'accesso è avvenuto prima del completamento del failover, sarà in modalità resilienza fino al completamento del failover. Solo allora l'utente può stabilire nuove sessioni o ristabilire le sessioni precedenti.

</div>

<div>

## <a name="user-experience-during-failback"></a>Esperienza utente durante il failback

Il failback del pool può verificarsi mentre un utente interessato ha effettuato l'accesso al pool di backup e l'utente rimane connesso e sta lavorando durante il failback. Tieni presente che il processo di failback richiede diversi minuti per il completamento.Per riferimento, si prevede di richiedere fino a 60 minuti per un pool di utenti di 20.000.

Nelle tabelle seguenti sono illustrati altri dettagli sul modo in cui un utente con un client Lync 2013 o un client di Microsoft Lync 2010 è interessato durante e dopo il failback e anche in che modo gli utenti di altri pool possono vedere e interagire con un utente in un pool di cui non è stato eseguito il failover. Gli utenti con client Microsoft Office Communicator 2007 R2 non riescono ad accedere fino a quando il pool Front-end non viene completamente eseguito.

Il termine *utente interessato* si riferisce a qualsiasi utente che non ha eseguito il failover dal pool Home e viene gestito dal pool di backup. Per definizione, qualsiasi utente originariamente ospitato nel pool di backup non è un utente interessato.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Esperienza utente per un utente interessato in un pool in failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Stato utente o attività</th>
<th>Durante il failback</th>
<th>Dopo il completamento del failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stato utente dell'utente già connesso</p></td>
<td><p>L'utente rimane connesso e collegato al pool di backup. Ad un certo punto l'utente verrà disconnesso e si riaccederà al pool di Home originale, in modalità resilienza.</p></td>
<td><p>L'utente rimane connesso e passa alla modalità normale.</p></td>
</tr>
<tr class="even">
<td><p>Registrazione di un nuovo utente</p></td>
<td><p>L'utente può accedere al pool Home in modalità resilienza.</p></td>
<td><p>L'utente può accedere al pool di Home originale in modalità normale.</p></td>
</tr>
<tr class="odd">
<td><p>Conferenze in corso organizzate da un utente interessato</p></td>
<td><p>Tutte le modalità di conferenza vengono terminate. Viene visualizzato il pulsante Riunisci, ma non è possibile partecipare alla riunione quando l'utente interessato è in modalità di resilienza.</p></td>
<td><p>Tutte le modalità funzionano ora. Ogni partecipante deve fare clic per tornare a partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p>Conferenze in corso organizzate da un utente non interessato</p></td>
<td><p>La conferenza continua e l'utente interessato può rimanere nella conferenza. L'utente interessato si limita a ciò che può fare in modalità resilienza.</p></td>
<td><p>La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano dopo l'uscita dalla modalità resilienza.</p></td>
</tr>
<tr class="odd">
<td><p>Pianificazione o modifica delle riunioni pianificate, creazione di conferenze ad hoc</p></td>
<td><p>Non è possibile mentre l'utente è in modalità di resilienza.</p></td>
<td><p>Disponibile per tutte le modalità.</p></td>
</tr>
<tr class="even">
<td><p>Presenza visualizzata da altri utenti nello stesso pool</p></td>
<td><p>Presenza sconosciuta mentre l'utente ha eseguito l'accesso al pool di backup durante la modalità resilienza.</p></td>
<td><p>Mostra lo stato dell'ultima presenza impostato dall'utente e le modifiche alla presenza verranno riflesse.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilità del servizio elenco contatti e Rubrica</p></td>
<td><p>Non disponibile</p></td>
<td><p>Disponibili</p></td>
</tr>
<tr class="even">
<td><p>Tutte le sessioni e le modalità peer-to-peer</p></td>
<td><p>Disponibili</p></td>
<td><p>Disponibili</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Esperienza utente per un utente ospitato in un pool non interessato durante il failback di un altro pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attività utente</th>
<th>Durante il failback</th>
<th>Dopo il completamento del failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Visualizzazione della presenza dell'utente interessato</p></td>
<td><p>Mostra lo stato dell'ultima presenza impostato dall'utente interessato.</p></td>
<td><p>Uso. Gli utenti inalterati vedono gli aggiornamenti apportati dagli utenti interessati.</p></td>
</tr>
<tr class="even">
<td><p>Conferenze in corso organizzate da un utente interessato</p></td>
<td><p>Tutte le modalità di conferenza vengono terminate.</p></td>
<td><p>Tutte le modalità funzionano ora. Ogni partecipante deve fare clic per tornare a partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p>Conferenze in corso organizzate da un utente non interessato</p></td>
<td><p>La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano.</p></td>
<td><p>La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano.</p></td>
</tr>
<tr class="even">
<td><p>Tutte le sessioni e le modalità peer-to-peer</p></td>
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

