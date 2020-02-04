---
title: 'Lync Server 2013: Pianificazione per il ripristino di emergenza dei Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="40966-102">Pianificazione per il ripristino di emergenza dei Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40966-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40966-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40966-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40966-104">In questa sezione vengono illustrati alcuni modi per preparare i gruppi di risposte per il ripristino di emergenza e viene fornita una panoramica del processo di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="40966-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="40966-105">Preparazione per il ripristino di emergenza di Response Group</span><span class="sxs-lookup"><span data-stu-id="40966-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="40966-106">Quando si preparano ed eseguono procedure di ripristino di emergenza, tenere presente quanto segue.</span><span class="sxs-lookup"><span data-stu-id="40966-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40966-107">In un ambiente di coesistenza sono supportati solo i gruppi di risposta di Lync Server 2013 per le procedure di ripristino di emergenza descritte in questo documento.</span><span class="sxs-lookup"><span data-stu-id="40966-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="40966-108">Pianificare il ripristino di emergenza quando si esegue la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="40966-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="40966-109">Per la capacità di ripristino di emergenza, ogni pool in un pool associato deve essere in grado di gestire i carichi di lavoro di tutti i gruppi di risposta in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="40966-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="40966-110">Per informazioni dettagliate sulla pianificazione della capacità dei gruppi di risposta, vedere [pianificazione della capacità per il gruppo di risposte in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="40966-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="40966-111">È possibile eseguire copie di backup regolari di tutte le configurazioni di Response Group in tutti i pool Front end in cui è stata distribuita l'applicazione Response Group usando la procedura di esportazione descritta in questo documento.</span><span class="sxs-lookup"><span data-stu-id="40966-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="40966-112">Per informazioni dettagliate, vedere procedure per il [ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40966-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="40966-113">Conservare le copie di backup in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="40966-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="40966-114">Mantenere una copia di backup separata di tutti i file audio originali usati per l'applicazione Response Group, incluse le registrazioni e i file di musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="40966-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="40966-115">Conservare i file di backup in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="40966-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="40966-116">Per il ripristino di emergenza di Lync Server 2013, tutte le impostazioni del gruppo di risposte devono avere nomi univoci nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40966-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="40966-117">Questo requisito si applica ai flussi di lavoro, alle code, ai gruppi di agenti, ai set di festività e alle ore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="40966-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="40966-118">Devi verificare che questo requisito venga soddisfatto quando i pool primari e di backup sono ancora attivi e prima di iniziare qualsiasi procedura di failover.</span><span class="sxs-lookup"><span data-stu-id="40966-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="40966-119">Se si verificano conflitti di nome durante l'importazione di dati di Response Group nel pool di backup, l'importazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="40966-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="40966-120">Per completare la procedura di importazione e failover, è necessario risolvere i conflitti di nome rinominando l'oggetto Response Group nel pool di backup oppure usando il cmdlet **Import-CsRgsConfiguration** con il parametro – ResolveNameConflicts per risolvere automaticamente il conflitto aggiungendo un numero identificativo univoco all'oggetto Response Group.</span><span class="sxs-lookup"><span data-stu-id="40966-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="40966-121">In generale, ti consigliamo di eseguire backup giornalieri, ma se hai un volume elevato di modifiche, potresti voler pianificare backup più frequenti.</span><span class="sxs-lookup"><span data-stu-id="40966-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="40966-122">La quantità di informazioni che è possibile perdere in caso di emergenza dipende dalla frequenza dei backup, nonché dalla frequenza e dal volume delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="40966-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="40966-123">È possibile importare gruppi di risposte in un pool di backup prima che si verifichi un'operazione di emergenza o failover.</span><span class="sxs-lookup"><span data-stu-id="40966-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="40966-124">L'importazione dei gruppi di risposta in anticipo riduce i tempi di inattività, perché il servizio di Response Group di Lync Server può essere ripristinato nel pool di backup non appena le chiamate vengono instradate al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40966-125">L'applicazione Response Group non può raggiungere gli agenti ospitati in un pool inattivo fino al completamento del failover.</span><span class="sxs-lookup"><span data-stu-id="40966-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="40966-126">Durante questo periodo, l'applicazione Response Group elabora le chiamate come se tali agenti non fossero disponibili.</span><span class="sxs-lookup"><span data-stu-id="40966-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="40966-127">Processo di ripristino di emergenza di Response Group</span><span class="sxs-lookup"><span data-stu-id="40966-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="40966-128">In caso di emergenza, è possibile recuperare i gruppi di risposte usando uno dei metodi di ripristino seguenti:</span><span class="sxs-lookup"><span data-stu-id="40966-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="40966-129">Eseguire il failover in un pool di backup e quindi eseguire il failback nel pool originale.</span><span class="sxs-lookup"><span data-stu-id="40966-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="40966-130">Eseguire il failover in un pool di backup, creare un nuovo pool con un nome di dominio completo diverso (FQDN) e quindi importare i gruppi di risposta nel nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="40966-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="40966-131">Durante la fase di failover del ripristino di emergenza, i gruppi di risposte si trovano in più pool: nel pool principale (non disponibile) e nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="40966-132">I gruppi di risposte in entrambi i pool hanno lo stesso nome e lo stesso proprietario (il pool principale), ma hanno genitori diversi.</span><span class="sxs-lookup"><span data-stu-id="40966-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="40966-133">Quando si recupera creando un nuovo pool con un nome di dominio completo diverso, è necessario assegnare il nuovo pool come proprietario dei gruppi di risposta durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="40966-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="40966-134">La proprietà dei gruppi di risposte rimane con il pool originale, a meno che non si riassegni esplicitamente la proprietà usando il parametro – OverwriteOwner con il cmdlet **Import-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="40966-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40966-135">Devi anche usare il parametro – OverwriteOwner se hai ricostruito il pool durante il ripristino (ovvero il database del gruppo di risposte è vuoto), indipendentemente dal fatto che tu usi o meno lo stesso nome FQDN.</span><span class="sxs-lookup"><span data-stu-id="40966-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="40966-136">Non è necessario usare il parametro – OverwriteOwner se non è stato ricostruito il pool, ma è possibile usare questo parametro ogni volta che si importano i gruppi di risposte nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="40966-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="40966-137">Puoi definire solo un set di impostazioni di configurazione per il gruppo di risposte a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="40966-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="40966-138">Queste impostazioni includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="40966-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="40966-139">Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="40966-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="40966-140">Per informazioni dettagliate sul cmdlet **Get-CsRgsConfiguration** , vedere [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="40966-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="40966-141">Puoi trasferire queste impostazioni a livello di applicazione da un pool a un altro usando il cmdlet **Import-CsRgsConfiguration** con il parametro – ReplaceExistingSettings, ma in questo modo le impostazioni vengono ignorate nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40966-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="40966-142">Questo vincolo relativo al trasferimento delle impostazioni in un altro pool è vero solo per le impostazioni a livello di applicazione e per il file audio predefinito per la musica in blocco.</span><span class="sxs-lookup"><span data-stu-id="40966-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="40966-143">Non si applica a gruppi di agenti, code, flussi di lavoro, orari di ufficio e set di festività.</span><span class="sxs-lookup"><span data-stu-id="40966-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="40966-144">Se non si vuole sostituire le impostazioni a livello di applicazione nel pool di backup durante una catastrofe e il pool principale non può essere recuperato, le impostazioni a livello di applicazione del pool primario andranno perse.</span><span class="sxs-lookup"><span data-stu-id="40966-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="40966-145">Se è necessario creare un nuovo pool per sostituire il pool principale durante il ripristino, con lo stesso nome di dominio completo o con un nome di dominio completo diverso, non è possibile recuperare le impostazioni originali a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="40966-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="40966-146">In questo caso, devi configurare il nuovo pool con queste impostazioni e includere il file audio per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="40966-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="40966-147">Se si decide di usare il cmdlet **Import-CsRgsConfiguration** per trasferire le impostazioni a livello di applicazione dal pool principale al pool di backup durante un periodo di emergenza, è possibile trasferire le impostazioni dal pool di backup al nuovo pool durante il ripristino nello stesso modo in cui sono state trasferite dal pool principale al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="40966-148">La tabella seguente illustra una panoramica dei passaggi necessari per recuperare i Response Group.</span><span class="sxs-lookup"><span data-stu-id="40966-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="40966-149">Per informazioni dettagliate sull'esecuzione di questa procedura, vedere procedure per il [ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40966-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="40966-150">Passaggi per il ripristino di emergenza di Response Group</span><span class="sxs-lookup"><span data-stu-id="40966-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40966-151">Fase</span><span class="sxs-lookup"><span data-stu-id="40966-151">Phase</span></span></th>
<th><span data-ttu-id="40966-152">Passaggi</span><span class="sxs-lookup"><span data-stu-id="40966-152">Steps</span></span></th>
<th><span data-ttu-id="40966-153">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="40966-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40966-154">Prima dell'interruzione</span><span class="sxs-lookup"><span data-stu-id="40966-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="40966-155">In base a una routine, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> per creare backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui viene distribuita l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="40966-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="40966-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40966-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40966-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40966-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40966-158">Durante l'interruzione</span><span class="sxs-lookup"><span data-stu-id="40966-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="40966-159">Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare la configurazione del servizio di risposta di Lync Server dal pool primario al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40966-160">Usa il parametro – ReplaceExistingSettings se vuoi sostituire le impostazioni del gruppo di risposta a livello di applicazione nel pool di backup con le impostazioni del pool principale.</span><span class="sxs-lookup"><span data-stu-id="40966-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="40966-161">Se non si trasferiscono le impostazioni a livello di applicazione dal pool principale al pool di backup e il pool principale non può essere recuperato, le impostazioni verranno perse dal pool principale.</span><span class="sxs-lookup"><span data-stu-id="40966-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="40966-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40966-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40966-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40966-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40966-164">Dopo l'importazione</span><span class="sxs-lookup"><span data-stu-id="40966-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="40966-165">Eseguire i cmdlet di Response Group con il parametro – ShowAll (per visualizzare tutti i gruppi di risposta) o il parametro – Owner (per visualizzare solo i gruppi di risposta importati) per verificare che tutte le configurazioni di Response Group siano state importate nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="40966-166">Se non si usa il parametro – ShowAll o il parametro – Owner, i gruppi di risposta importati nel pool di backup non verranno elencati nei risultati restituiti dai cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40966-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="40966-167">Eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="40966-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="40966-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="40966-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="40966-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="40966-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="40966-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="40966-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="40966-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40966-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40966-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40966-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40966-175">Dopo il failover</span><span class="sxs-lookup"><span data-stu-id="40966-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="40966-176">Effettuare una chiamata di prova a un gruppo di risposte importato nel pool di backup e verificare che la chiamata sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="40966-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="40966-177">Tutti gli agenti formali devono accedere di nuovo ai loro gruppi formali nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="40966-178">Gestire le modifiche alla configurazione:</span><span class="sxs-lookup"><span data-stu-id="40966-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="40966-179">I gruppi di risposta nel pool di backup, se importati nel pool di backup o di proprietà del pool di backup, possono essere modificati come di consueto durante l'interruzione.</span><span class="sxs-lookup"><span data-stu-id="40966-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="40966-180">Per gestire i gruppi di risposta importati nel pool di backup, è necessario usare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="40966-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="40966-181">Non è possibile usare il pannello di controllo di Lync Server per gestire questi gruppi di risposta mentre si trovano nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="40966-182">N/D</span><span class="sxs-lookup"><span data-stu-id="40966-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40966-183">Dopo il ripristino, prima di failback</span><span class="sxs-lookup"><span data-stu-id="40966-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="40966-184">Eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> specificando il parametro-source come pool di backup e il parametro – Owner come pool principale per esportare i gruppi di risposte di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="40966-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40966-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40966-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40966-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40966-187">Dopo il failback</span><span class="sxs-lookup"><span data-stu-id="40966-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="40966-188">Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare di nuovo i gruppi di risposte nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="40966-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40966-189">Se il pool principale non può essere recuperato e si distribuisce un nuovo pool per sostituirlo, usare il parametro – ReplaceExistingSettings per trasferire le impostazioni a livello di applicazione dal pool di backup al nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="40966-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="40966-190">Se non si trasferiscono le impostazioni dal pool di backup, il nuovo pool utilizzerà le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="40966-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="40966-191">Eseguire i cmdlet seguenti con il parametro – ShowAll (per visualizzare tutti i gruppi di risposta) o il parametro – Owner (per visualizzare solo i gruppi di risposta importati) per verificare che tutte le configurazioni di Response Group siano state correttamente importate nel pool principale:</span><span class="sxs-lookup"><span data-stu-id="40966-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="40966-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="40966-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="40966-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="40966-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="40966-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="40966-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="40966-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="40966-197">Eseguire una chiamata di prova a un gruppo di risposte importato di nuovo nel pool principale e verificare che la chiamata sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="40966-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="40966-198">Facoltativamente, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> nel pool di backup con il parametro – RemoveExportedConfiguration per rimuovere i gruppi di risposte di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40966-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="40966-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40966-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40966-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40966-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

