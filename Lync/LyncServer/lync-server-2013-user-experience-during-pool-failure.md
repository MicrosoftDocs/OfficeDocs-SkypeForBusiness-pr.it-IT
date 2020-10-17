---
title: Esperienza utente di Lync Server 2013 durante l'errore del pool
description: Esperienza utente di Lync Server 2013 durante l'errore del pool.
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
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569792"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="73321-103">Esperienza utente durante un errore del pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73321-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73321-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="73321-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="73321-105">Se si verifica il il failover di un pool, tutti gli utenti del pool interessato sono obbligati a disconnettersi e quindi a connettersi al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="73321-105">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="73321-106">Per un breve periodo di tempo, gli utenti che si connettono al pool di backup possono trovarsi in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-106">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="73321-107">In modalità di resilienza, gli utenti non sono in grado di eseguire attività che causerebbero una modifica permanente su Lync Server, ad esempio l'aggiunta di un contatto.</span><span class="sxs-lookup"><span data-stu-id="73321-107">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="73321-108">Al termine del failover, tutti gli utenti possono ottenere tutti i servizi dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="73321-108">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="73321-109">Tutte le sessioni in corso per l'utente al momento del failover del pool vengono interrotte e, per proseguire, l'utente deve ristabilirle dopo il failover.</span><span class="sxs-lookup"><span data-stu-id="73321-109">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="73321-p102">Gli utenti non vengono ricollocati durante il failover o il failback. Gli utenti che si trovano in un pool su cui si verifica un problema verranno infatti serviti temporaneamente dal pool di backup. Quando il pool principale viene ripristinato, l'amministratore può eseguire il failback di tali utenti in modo che vengano serviti di nuovo dal rispettivo pool principale originale.</span><span class="sxs-lookup"><span data-stu-id="73321-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="73321-113">Nota in Lync 2013, il database del server delle informazioni percorso non viene replicato nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="73321-113">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="73321-114">Come procedura consigliata, l'amministratore dovrebbe eseguire con regolarità il backup del database LIS e utilizzare la copia di backup più recente per ripristinare tale database nel pool di backup dopo il failover.</span><span class="sxs-lookup"><span data-stu-id="73321-114">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="73321-115">Esperienza utente durante il failover</span><span class="sxs-lookup"><span data-stu-id="73321-115">User Experience During Failover</span></span>

<span data-ttu-id="73321-p104">Quando un utente si trova in un pool su cui si verifica un problema, viene disconnesso. Tutte le sessioni peer-to-peer a cui l'utente stava partecipando vengono terminate, così come le conferenze che ha organizzato. L'utente non può riconnettersi finché non scade il timer di resilienza della funzione di registrazione o finché l'amministratore non avvia le procedure di failover, a seconda di quale di questi eventi avviene per primo. Quando l'utente si riconnette, si riconnetterà al pool di backup. Se si connette prima che il failover sia stato completato, sarà in modalità Resilienza fino al completamento del failover. Solo a quel punto l'utente potrà stabilire nuove sessioni o ristabilire le sessioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="73321-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="73321-121">Esperienza utente durante il failback</span><span class="sxs-lookup"><span data-stu-id="73321-121">User Experience During Failback</span></span>

<span data-ttu-id="73321-p105">Il failback del pool può avvenire mentre un utente interessato è connesso al pool di backup. L'utente rimane connesso e operativo durante il failback. Tale processo viene completato nel giro di diversi minuti. Come riferimento, è previsto che il failback richieda fino a 60 minuti per un pool di 20.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="73321-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="73321-125">Nelle tabelle riportate di seguito vengono illustrati ulteriori dettagli sul modo in cui un utente con un client Lync 2013 o un client Microsoft Lync 2010 viene influenzato durante e dopo il failback e in che modo gli utenti in altri pool visualizzano e interagiscono con un utente in un pool di cui non è stato eseguito il failover.</span><span class="sxs-lookup"><span data-stu-id="73321-125">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="73321-126">Gli utenti che dispongono di client Microsoft Office Communicator 2007 R2 non possono accedere fino a quando non è stato completamente eseguito il failover del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="73321-126">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="73321-p107">Con il termine *utente interessato* viene indicato qualsiasi utente di cui sia stato eseguito il failover dal pool principale e che venga servito dal pool di backup. Per definizione, gli utenti che si trovavano originariamente nel pool di backup non sono utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="73321-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="73321-129">Esperienza utente per un utente interessato in un pool in corso di failback</span><span class="sxs-lookup"><span data-stu-id="73321-129">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73321-130">Stato o attività dell'utente</span><span class="sxs-lookup"><span data-stu-id="73321-130">User state or task</span></span></th>
<th><span data-ttu-id="73321-131">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="73321-131">During failback</span></span></th>
<th><span data-ttu-id="73321-132">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="73321-132">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73321-133">Utente già connesso</span><span class="sxs-lookup"><span data-stu-id="73321-133">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="73321-p108">L'utente resta connesso al pool di backup. A un certo punto l'utente verrà disconnesso e riconnesso al pool principale originale, in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="73321-136">L'utente rimane connesso e passa alla modalità normale.</span><span class="sxs-lookup"><span data-stu-id="73321-136">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73321-137">Nuova connessione dell'utente</span><span class="sxs-lookup"><span data-stu-id="73321-137">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="73321-138">L'utente può connettersi al pool principale in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-138">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="73321-139">L'utente può connettersi al pool principale originale in modalità normale.</span><span class="sxs-lookup"><span data-stu-id="73321-139">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73321-140">Conferenze in corso organizzate dall'utente interessato</span><span class="sxs-lookup"><span data-stu-id="73321-140">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="73321-p109">Tutte le modalità di conferenza vengono terminate. Viene visualizzato il pulsante Torna a partecipare, ma nessun utente può ripartecipare alla conferenza mentre l'utente interessato è in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="73321-p110">Tutte le modalità ora funzionano. Tutti i partecipanti devono fare clic sul pulsante per tornare a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="73321-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73321-145">Conferenze in corso organizzate da un utente non interessato</span><span class="sxs-lookup"><span data-stu-id="73321-145">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="73321-p111">La conferenza prosegue e l'utente interessato può continuare a parteciparvi, ma può eseguire esclusivamente le operazioni consentite in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="73321-148">La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano dopo che l'utente esce dalla modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-148">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73321-149">Pianificazione o modifica delle riunioni pianificate, creazione di conferenze ad hoc</span><span class="sxs-lookup"><span data-stu-id="73321-149">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="73321-150">Attività impossibili mentre l'utente è in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-150">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="73321-151">Attività disponibili per tutte le modalità.</span><span class="sxs-lookup"><span data-stu-id="73321-151">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73321-152">Presenza come viene visualizzata da altri utenti dello stesso pool</span><span class="sxs-lookup"><span data-stu-id="73321-152">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="73321-153">Presenza sconosciuta mentre l'utente è connesso al pool di backup in modalità Resilienza.</span><span class="sxs-lookup"><span data-stu-id="73321-153">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="73321-154">Viene visualizzato l'ultimo stato di presenza impostato dall'utente. Le eventuali variazioni di tale stato ora saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="73321-154">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73321-155">Disponibilità dell'Elenco contatti e del Servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="73321-155">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="73321-156">Non disponibili</span><span class="sxs-lookup"><span data-stu-id="73321-156">Not available</span></span></p></td>
<td><p><span data-ttu-id="73321-157">Disponibili</span><span class="sxs-lookup"><span data-stu-id="73321-157">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73321-158">Tutte le sessioni peer-to-peer e tutte le modalità</span><span class="sxs-lookup"><span data-stu-id="73321-158">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="73321-159">Disponibili</span><span class="sxs-lookup"><span data-stu-id="73321-159">Available</span></span></p></td>
<td><p><span data-ttu-id="73321-160">Disponibili</span><span class="sxs-lookup"><span data-stu-id="73321-160">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="73321-161">Esperienza utente di un utente che si trova in un pool non interessato durante il failback di un altro pool</span><span class="sxs-lookup"><span data-stu-id="73321-161">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73321-162">Attività dell'utente</span><span class="sxs-lookup"><span data-stu-id="73321-162">User task</span></span></th>
<th><span data-ttu-id="73321-163">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="73321-163">During failback</span></span></th>
<th><span data-ttu-id="73321-164">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="73321-164">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73321-165">Visualizzazione della presenza dell'utente interessato</span><span class="sxs-lookup"><span data-stu-id="73321-165">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="73321-166">Viene visualizzato l'ultimo stato di presenza impostato dall'utente interessato.</span><span class="sxs-lookup"><span data-stu-id="73321-166">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="73321-p112">Funzionante. Gli utenti non interessati vedono le modifiche apportate dagli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="73321-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73321-169">Conferenze in corso organizzate dall'utente interessato</span><span class="sxs-lookup"><span data-stu-id="73321-169">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="73321-170">Tutte le modalità di conferenza vengono terminate.</span><span class="sxs-lookup"><span data-stu-id="73321-170">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="73321-p113">Tutte le modalità ora funzionano. Tutti i partecipanti devono fare clic sul pulsante per tornare a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="73321-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73321-173">Conferenze in corso organizzate da un utente non interessato</span><span class="sxs-lookup"><span data-stu-id="73321-173">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="73321-174">La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano.</span><span class="sxs-lookup"><span data-stu-id="73321-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="73321-175">La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano.</span><span class="sxs-lookup"><span data-stu-id="73321-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73321-176">Tutte le sessioni peer-to-peer e tutte le modalità</span><span class="sxs-lookup"><span data-stu-id="73321-176">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="73321-177">Disponibili</span><span class="sxs-lookup"><span data-stu-id="73321-177">Available</span></span></p></td>
<td><p><span data-ttu-id="73321-178">Disponibili</span><span class="sxs-lookup"><span data-stu-id="73321-178">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

