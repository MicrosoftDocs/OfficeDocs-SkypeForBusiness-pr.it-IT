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

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="d8c78-102">Esperienza utente durante l'errore del pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8c78-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c78-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d8c78-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d8c78-104">Se non è possibile eseguire il failover di un pool, tutti gli utenti del pool interessato saranno costretti a disconnettersi e quindi a eseguire l'accesso al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="d8c78-105">Per un breve periodo gli utenti che accedono al pool di backup potrebbero essere in modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="d8c78-106">In modalità resilienza gli utenti non sono in grado di eseguire attività che causerebbero una modifica persistente in Lync Server, ad esempio l'aggiunta di un contatto.</span><span class="sxs-lookup"><span data-stu-id="d8c78-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="d8c78-107">Al termine del failover, tutti gli utenti possono ottenere tutti i servizi dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="d8c78-108">Tutte le sessioni che un utente ha quando il pool non riesce vengono interrotte e l'utente deve ristabilire tali sessioni dopo il failover per continuare.</span><span class="sxs-lookup"><span data-stu-id="d8c78-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="d8c78-109">Gli utenti non vengono reospitati durante il failover o il failback.</span><span class="sxs-lookup"><span data-stu-id="d8c78-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="d8c78-110">Gli utenti ospitati in un pool che non riesce verranno temporaneamente serviti dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="d8c78-111">Quando il pool Home viene ripristinato, l'amministratore può eseguire il failover di questi utenti per essere serviti dal proprio pool di Home originale.</span><span class="sxs-lookup"><span data-stu-id="d8c78-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="d8c78-112">Nota in Lync 2013 il database del server delle informazioni sulla posizione non viene replicato nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="d8c78-113">Per le procedure consigliate, l'amministratore deve eseguire regolarmente il backup del database LIS e usare la copia di backup più recente per ripristinare il database LIS nel pool di backup dopo il failover.</span><span class="sxs-lookup"><span data-stu-id="d8c78-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="d8c78-114">Esperienza utente durante il failover</span><span class="sxs-lookup"><span data-stu-id="d8c78-114">User Experience During Failover</span></span>

<span data-ttu-id="d8c78-115">Quando un utente si trova in un pool che non riesce, l'utente viene disconnesso. Qualsiasi sessione peer-to-peer a cui l'utente ha partecipato viene terminata, così come le conferenze organizzate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d8c78-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="d8c78-116">L'utente non può eseguire l'accesso finché non scade il timer di resilienza del registrar o l'amministratore avvia procedure di failover, a seconda di quale verrà prima.</span><span class="sxs-lookup"><span data-stu-id="d8c78-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="d8c78-117">Quando l'utente esegue il log-in, eseguirà l'accesso al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="d8c78-118">Se l'accesso è avvenuto prima del completamento del failover, sarà in modalità resilienza fino al completamento del failover.</span><span class="sxs-lookup"><span data-stu-id="d8c78-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="d8c78-119">Solo allora l'utente può stabilire nuove sessioni o ristabilire le sessioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d8c78-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="d8c78-120">Esperienza utente durante il failback</span><span class="sxs-lookup"><span data-stu-id="d8c78-120">User Experience During Failback</span></span>

<span data-ttu-id="d8c78-121">Il failback del pool può verificarsi mentre un utente interessato ha effettuato l'accesso al pool di backup e l'utente rimane connesso e sta lavorando durante il failback.</span><span class="sxs-lookup"><span data-stu-id="d8c78-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="d8c78-122">Tieni presente che il processo di failback richiede diversi minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="d8c78-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="d8c78-123">Per riferimento, si prevede di richiedere fino a 60 minuti per un pool di utenti di 20.000.</span><span class="sxs-lookup"><span data-stu-id="d8c78-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="d8c78-124">Nelle tabelle seguenti sono illustrati altri dettagli sul modo in cui un utente con un client Lync 2013 o un client di Microsoft Lync 2010 è interessato durante e dopo il failback e anche in che modo gli utenti di altri pool possono vedere e interagire con un utente in un pool di cui non è stato eseguito il failover.</span><span class="sxs-lookup"><span data-stu-id="d8c78-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="d8c78-125">Gli utenti con client Microsoft Office Communicator 2007 R2 non riescono ad accedere fino a quando il pool Front-end non viene completamente eseguito.</span><span class="sxs-lookup"><span data-stu-id="d8c78-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="d8c78-126">Il termine *utente interessato* si riferisce a qualsiasi utente che non ha eseguito il failover dal pool Home e viene gestito dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="d8c78-127">Per definizione, qualsiasi utente originariamente ospitato nel pool di backup non è un utente interessato.</span><span class="sxs-lookup"><span data-stu-id="d8c78-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="d8c78-128">Esperienza utente per un utente interessato in un pool in failback</span><span class="sxs-lookup"><span data-stu-id="d8c78-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c78-129">Stato utente o attività</span><span class="sxs-lookup"><span data-stu-id="d8c78-129">User state or task</span></span></th>
<th><span data-ttu-id="d8c78-130">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="d8c78-130">During failback</span></span></th>
<th><span data-ttu-id="d8c78-131">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="d8c78-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c78-132">Stato utente dell'utente già connesso</span><span class="sxs-lookup"><span data-stu-id="d8c78-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="d8c78-133">L'utente rimane connesso e collegato al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d8c78-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="d8c78-134">Ad un certo punto l'utente verrà disconnesso e si riaccederà al pool di Home originale, in modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-135">L'utente rimane connesso e passa alla modalità normale.</span><span class="sxs-lookup"><span data-stu-id="d8c78-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c78-136">Registrazione di un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="d8c78-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="d8c78-137">L'utente può accedere al pool Home in modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-138">L'utente può accedere al pool di Home originale in modalità normale.</span><span class="sxs-lookup"><span data-stu-id="d8c78-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c78-139">Conferenze in corso organizzate da un utente interessato</span><span class="sxs-lookup"><span data-stu-id="d8c78-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="d8c78-140">Tutte le modalità di conferenza vengono terminate.</span><span class="sxs-lookup"><span data-stu-id="d8c78-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="d8c78-141">Viene visualizzato il pulsante Riunisci, ma non è possibile partecipare alla riunione quando l'utente interessato è in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-142">Tutte le modalità funzionano ora.</span><span class="sxs-lookup"><span data-stu-id="d8c78-142">All modalities now work.</span></span> <span data-ttu-id="d8c78-143">Ogni partecipante deve fare clic per tornare a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c78-144">Conferenze in corso organizzate da un utente non interessato</span><span class="sxs-lookup"><span data-stu-id="d8c78-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="d8c78-145">La conferenza continua e l'utente interessato può rimanere nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="d8c78-146">L'utente interessato si limita a ciò che può fare in modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-147">La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano dopo l'uscita dalla modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c78-148">Pianificazione o modifica delle riunioni pianificate, creazione di conferenze ad hoc</span><span class="sxs-lookup"><span data-stu-id="d8c78-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="d8c78-149">Non è possibile mentre l'utente è in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-150">Disponibile per tutte le modalità.</span><span class="sxs-lookup"><span data-stu-id="d8c78-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c78-151">Presenza visualizzata da altri utenti nello stesso pool</span><span class="sxs-lookup"><span data-stu-id="d8c78-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="d8c78-152">Presenza sconosciuta mentre l'utente ha eseguito l'accesso al pool di backup durante la modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-153">Mostra lo stato dell'ultima presenza impostato dall'utente e le modifiche alla presenza verranno riflesse.</span><span class="sxs-lookup"><span data-stu-id="d8c78-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c78-154">Disponibilità del servizio elenco contatti e Rubrica</span><span class="sxs-lookup"><span data-stu-id="d8c78-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="d8c78-155">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="d8c78-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="d8c78-156">Disponibili</span><span class="sxs-lookup"><span data-stu-id="d8c78-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c78-157">Tutte le sessioni e le modalità peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="d8c78-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="d8c78-158">Disponibili</span><span class="sxs-lookup"><span data-stu-id="d8c78-158">Available</span></span></p></td>
<td><p><span data-ttu-id="d8c78-159">Disponibili</span><span class="sxs-lookup"><span data-stu-id="d8c78-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="d8c78-160">Esperienza utente per un utente ospitato in un pool non interessato durante il failback di un altro pool</span><span class="sxs-lookup"><span data-stu-id="d8c78-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c78-161">Attività utente</span><span class="sxs-lookup"><span data-stu-id="d8c78-161">User task</span></span></th>
<th><span data-ttu-id="d8c78-162">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="d8c78-162">During failback</span></span></th>
<th><span data-ttu-id="d8c78-163">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="d8c78-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c78-164">Visualizzazione della presenza dell'utente interessato</span><span class="sxs-lookup"><span data-stu-id="d8c78-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="d8c78-165">Mostra lo stato dell'ultima presenza impostato dall'utente interessato.</span><span class="sxs-lookup"><span data-stu-id="d8c78-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-166">Uso.</span><span class="sxs-lookup"><span data-stu-id="d8c78-166">Working.</span></span> <span data-ttu-id="d8c78-167">Gli utenti inalterati vedono gli aggiornamenti apportati dagli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="d8c78-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c78-168">Conferenze in corso organizzate da un utente interessato</span><span class="sxs-lookup"><span data-stu-id="d8c78-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="d8c78-169">Tutte le modalità di conferenza vengono terminate.</span><span class="sxs-lookup"><span data-stu-id="d8c78-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-170">Tutte le modalità funzionano ora.</span><span class="sxs-lookup"><span data-stu-id="d8c78-170">All modalities now work.</span></span> <span data-ttu-id="d8c78-171">Ogni partecipante deve fare clic per tornare a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="d8c78-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c78-172">Conferenze in corso organizzate da un utente non interessato</span><span class="sxs-lookup"><span data-stu-id="d8c78-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="d8c78-173">La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano.</span><span class="sxs-lookup"><span data-stu-id="d8c78-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="d8c78-174">La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano.</span><span class="sxs-lookup"><span data-stu-id="d8c78-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c78-175">Tutte le sessioni e le modalità peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="d8c78-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="d8c78-176">Disponibili</span><span class="sxs-lookup"><span data-stu-id="d8c78-176">Available</span></span></p></td>
<td><p><span data-ttu-id="d8c78-177">Disponibili</span><span class="sxs-lookup"><span data-stu-id="d8c78-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

