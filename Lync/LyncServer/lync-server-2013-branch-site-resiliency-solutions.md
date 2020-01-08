---
title: 'Lync Server 2013: Soluzioni di resilienza dei siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="9ed30-102">Soluzioni di resilienza dei siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ed30-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ed30-103">_**Argomento Ultima modifica:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="9ed30-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="9ed30-104">Sono evidenti i vantaggi per fornire alla propria organizzazione la resilienza del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="9ed30-105">In particolare, se si perde la connessione al sito centrale, gli utenti del sito di succursale continueranno ad avere il servizio VoIP aziendale e la segreteria telefonica (se si configurano le impostazioni di reinstradamento della segreteria telefonica; per informazioni dettagliate, vedere [requisiti di resilienza dei siti secondari per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="9ed30-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="9ed30-106">Tuttavia, per i siti con meno di 25 utenti, una soluzione di resilienza potrebbe non fornire un rendimento sufficiente per gli investimenti.</span><span class="sxs-lookup"><span data-stu-id="9ed30-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="9ed30-107">Se si decide di specificare la resilienza del sito filiale, sono disponibili tre opzioni.</span><span class="sxs-lookup"><span data-stu-id="9ed30-107">If you decide to provide branch-site resiliency, you have three options.</span></span> <span data-ttu-id="9ed30-108">La tabella seguente può aiutare a determinare l'opzione migliore per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ed30-108">The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ed30-109">Se si...</span><span class="sxs-lookup"><span data-stu-id="9ed30-109">If you…</span></span></th>
<th><span data-ttu-id="9ed30-110">Ti consigliamo di usare un...</span><span class="sxs-lookup"><span data-stu-id="9ed30-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ed30-111">Ospita tra gli utenti di 25 e 1000 nel sito di succursale e se il ritorno sugli investimenti non supporta una distribuzione completa o il supporto amministrativo locale non è disponibile</span><span class="sxs-lookup"><span data-stu-id="9ed30-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9ed30-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="9ed30-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="9ed30-113">Survivable Branch Appliance è un server blade standard del settore con un registrar di Lync Server e Mediation Server in uso in Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="9ed30-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="9ed30-114">Il Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="9ed30-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="9ed30-115">I dispositivi di terze parti qualificati (sviluppati da Microsoft Partners nel programma di qualifica/certificazione di Survivable Branch Appliance (SBA)) garantiscono una connessione PSTN continua in caso di errore WAN, ma questo approccio non offre una presenza resiliente e servizi di conferenza, perché queste funzionalità dipendono dai server front-end del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="9ed30-116">Per informazioni dettagliate sugli elettrodomestici Survivable Branch &quot;, vedere dettagli di Survivable&quot; Branch Appliance, più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9ed30-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="9ed30-117"><strong>Nota:</strong> Se si decide di usare anche un trunk SIP con l'appliance Survivable Branch, contattare il fornitore Survivable Branch Appliance per conoscere il provider di servizi migliore per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ed30-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed30-118">Host tra gli utenti di 1000 e 2000 nel sito di succursale, non ha una connessione WAN resiliente e ha addestrato gli amministratori di Lync Server disponibili</span><span class="sxs-lookup"><span data-stu-id="9ed30-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="9ed30-119">Survivable Branch Server o due Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="9ed30-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="9ed30-120">Survivable Branch Server è una riunione di Windows Server requisiti hardware specificati in cui è installato Lync Server registrar e il software Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9ed30-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="9ed30-121">Deve essere collegato a un gateway PSTN o a un trunk SIP a un provider di servizi telefonici.</span><span class="sxs-lookup"><span data-stu-id="9ed30-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="9ed30-122">Per informazioni dettagliate sui Survivable Branch Server, &quot;vedere dettagli di Survivable Branch&quot; server, più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9ed30-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ed30-123">Se sono necessarie funzionalità di presenza e conferenze oltre alle funzionalità vocali per un massimo di 5000 utenti e sono stati addestrati gli amministratori di Lync Server disponibili</span><span class="sxs-lookup"><span data-stu-id="9ed30-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="9ed30-124">Distribuire come sito centrale con un server Standard Edition anziché come sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="9ed30-125">Una distribuzione su vasta scala di Lync Server offre una connessione PSTN continua e una presenza resiliente e conferenze in caso di errore WAN.</span><span class="sxs-lookup"><span data-stu-id="9ed30-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="9ed30-126">Per informazioni dettagliate sulla preparazione di questa soluzione, vedere <a href="lync-server-2013-planning-for-your-organization.md">pianificazione dell'organizzazione per Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determinare i requisiti di sistema per Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determinare i requisiti di infrastruttura per Lync Server 2013</a>e altre sezioni pertinenti della documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9ed30-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="9ed30-127">Topologie di resilienza</span><span class="sxs-lookup"><span data-stu-id="9ed30-127">Resiliency Topologies</span></span>

<span data-ttu-id="9ed30-128">La figura seguente mostra le topologie consigliate per la resilienza del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="9ed30-129">**Opzioni di resilienza del sito filiale**</span><span class="sxs-lookup"><span data-stu-id="9ed30-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="9ed30-130">![](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opzioni di") resilienza del ramo vocale</span><span class="sxs-lookup"><span data-stu-id="9ed30-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="9ed30-131">Dettagli Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="9ed30-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="9ed30-132">Il Survivable Branch Appliance di Lync Server include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ed30-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="9ed30-133">Registrar per l'autenticazione utente, la registrazione e il routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="9ed30-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="9ed30-134">Un Mediation Server per la gestione della segnalazione tra il registrar e un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="9ed30-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="9ed30-135">Gateway PSTN per il routing delle chiamate alla rete PSTN come trasporto di fallback in caso di interruzioni WAN</span><span class="sxs-lookup"><span data-stu-id="9ed30-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="9ed30-136">SQL Server Express per l'archiviazione dei dati dell'utente locale</span><span class="sxs-lookup"><span data-stu-id="9ed30-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="9ed30-137">Il Survivable Branch Appliance include anche trunk PSTN, porte analogiche e una scheda Ethernet.</span><span class="sxs-lookup"><span data-stu-id="9ed30-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="9ed30-138">Se la connessione WAN del sito della filiale a un sito centrale diventa non disponibile, gli utenti di Branch interni continuano a essere registrati presso il registrar Survivable Branch Appliance e a ottenere il servizio vocale ininterrotto usando la connessione Survivable Branch Appliance alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ed30-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="9ed30-139">Gli utenti del sito della filiale che si connettono da una sede o da altre posizioni remote potranno eseguire la registrazione presso un server di registrazione in un sito centrale se il collegamento WAN al sito della filiale non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="9ed30-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="9ed30-140">Questi utenti avranno la funzionalità di comunicazioni unificate completa, con l'unica eccezione che le chiamate in ingresso al sito della filiale andranno alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9ed30-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="9ed30-141">Quando la connessione WAN diventa disponibile, la funzionalità completa deve essere ripristinata agli utenti del sito succursale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="9ed30-142">Né il failover per il Survivable Branch Appliance né il ripristino del servizio richiedono la presenza di un amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="9ed30-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="9ed30-143">Lync Server supporta fino a due Survivable Branch Appliance in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ed30-144">Gli utenti ospitati in un dispositivo Survivable Branch di Lync Server non riescono a creare nuove chat room o a visualizzare la scheda della sala per le camere esistenti.</span><span class="sxs-lookup"><span data-stu-id="9ed30-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="9ed30-145">Panoramica della distribuzione Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="9ed30-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="9ed30-146">Il Survivable Branch Appliance è prodotto da produttori di apparecchiature originali in collaborazione con Microsoft e distribuito per loro conto da rivenditori a valore aggiunto.</span><span class="sxs-lookup"><span data-stu-id="9ed30-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="9ed30-147">Questa distribuzione deve essere eseguita solo dopo la distribuzione di Lync Server presso il sito centrale, una connessione WAN al sito di succursale e gli utenti del sito di succursale sono abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="9ed30-148">Per informazioni dettagliate su queste fasi, vedere [distribuzione di un Survivable Branch Appliance o server con Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9ed30-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ed30-149">Fase</span><span class="sxs-lookup"><span data-stu-id="9ed30-149">Phase</span></span></th>
<th><span data-ttu-id="9ed30-150">Passaggi</span><span class="sxs-lookup"><span data-stu-id="9ed30-150">Steps</span></span></th>
<th><span data-ttu-id="9ed30-151">Diritti utente</span><span class="sxs-lookup"><span data-stu-id="9ed30-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ed30-152">Configurare servizi di dominio Active Directory per Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="9ed30-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="9ed30-153"><strong>Nel sito centrale:</strong></span><span class="sxs-lookup"><span data-stu-id="9ed30-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="9ed30-154">Creare un account utente di dominio (o un'identità aziendale) per il tecnico che installerà e attiverà il Survivable Branch Appliance presso il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="9ed30-155">Creare un account del computer (con il nome di dominio completo applicabile) per Survivable Branch Appliance in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ed30-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="9ed30-156">In Generatore di topologie creare e pubblicare l'appliance Survivable Branch.</span><span class="sxs-lookup"><span data-stu-id="9ed30-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9ed30-157">L'account utente tecnico deve essere un membro di RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="9ed30-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="9ed30-158">Il Survivable Branch Appliance deve appartenere al gruppo RTCSBAUniversalServices, che si verifica automaticamente quando si usa generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9ed30-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed30-159">Installare e attivare Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="9ed30-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="9ed30-160"><strong>Nel sito della filiale:</strong></span><span class="sxs-lookup"><span data-stu-id="9ed30-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="9ed30-161">Connettere il Survivable Branch Appliance a una porta Ethernet e a una porta PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ed30-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="9ed30-162">Avviare Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="9ed30-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="9ed30-163">Aggiungere il Survivable Branch Appliance al dominio usando l'account utente di dominio creato per Survivable Branch Appliance nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9ed30-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="9ed30-164">Impostare il nome di dominio completo e l'indirizzo IP in base al nome di dominio completo creato nell'account del computer.</span><span class="sxs-lookup"><span data-stu-id="9ed30-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="9ed30-165">Configurare l'appliance Survivable Branch utilizzando l'interfaccia utente OEM.</span><span class="sxs-lookup"><span data-stu-id="9ed30-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="9ed30-166">Testare la connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ed30-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9ed30-167">L'account utente tecnico deve essere un membro di RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="9ed30-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="9ed30-168">Dettagli Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9ed30-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="9ed30-169">In Generatore di topologia creare il sito della filiale, aggiungere il Survivable Branch Server a tale sito e quindi eseguire la distribuzione guidata di Lync Server nel computer in cui si vuole installare il ruolo.</span><span class="sxs-lookup"><span data-stu-id="9ed30-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ed30-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed30-170">See Also</span></span>


[<span data-ttu-id="9ed30-171">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ed30-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

