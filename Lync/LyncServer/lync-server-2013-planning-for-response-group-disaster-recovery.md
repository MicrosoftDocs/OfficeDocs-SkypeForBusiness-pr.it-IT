---
title: 'Lync Server 2013: pianificazione per il ripristino di emergenza di Response Group'
description: 'Lync Server 2013: pianificazione per il ripristino di emergenza di Response Group.'
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
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549262"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="40294-103">Pianificazione del ripristino di emergenza di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40294-103">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40294-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40294-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40294-105">In questa sezione vengono illustrati alcuni modi per preparare i Response Group per ripristini di emergenza e fornita una panoramica del processo di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="40294-105">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="40294-106">Preparazione per il ripristino di emergenza di Response Group</span><span class="sxs-lookup"><span data-stu-id="40294-106">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="40294-107">Durante la preparazione e l'esecuzione delle procedure di ripristino di emergenza, tenere presente quanto segue.</span><span class="sxs-lookup"><span data-stu-id="40294-107">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40294-108">In un ambiente di coesistenza, solo i Response Group di Lync Server 2013 sono supportati per le procedure di ripristino di emergenza descritte in questo documento.</span><span class="sxs-lookup"><span data-stu-id="40294-108">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="40294-109">Pianificare il ripristino di emergenza durante la pianificazione delle capacità.</span><span class="sxs-lookup"><span data-stu-id="40294-109">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="40294-110">Per le capacità del ripristino di emergenza, ogni pool appartenente a una coppia deve essere in grado di gestire i carichi di lavoro di tutti i Response Group di entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="40294-110">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="40294-111">Per informazioni dettagliate sulla pianificazione della capacità dei Response Group, vedere [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="40294-111">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="40294-112">Eseguire regolarmente copie di backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui è stata distribuita l'applicazione Response Group utilizzando la procedura di esportazione descritta in questo documento.</span><span class="sxs-lookup"><span data-stu-id="40294-112">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="40294-113">Per ulteriori informazioni, vedere [procedure di ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40294-113">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="40294-114">Conservare le copie di backup in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="40294-114">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="40294-115">Mantenere una copia di backup distinta di tutti i file audio originali utilizzati per l'applicazione Response Group, incluse le registrazioni e i file musicali in attesa.</span><span class="sxs-lookup"><span data-stu-id="40294-115">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="40294-116">Conservare le copie di backup in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="40294-116">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="40294-117">Per il ripristino di emergenza di Lync Server 2013, tutte le impostazioni di Response Group devono avere nomi univoci nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40294-117">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="40294-118">Questo requisito si applica a flussi di lavoro, code, gruppi di agenti, set di festività e orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="40294-118">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="40294-119">È opportuno verificare che questo requisito sia soddisfatto quando i pool principale e di backup sono ancora attivi e prima di avviare una procedura di failover.</span><span class="sxs-lookup"><span data-stu-id="40294-119">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="40294-120">Se vengono rilevati conflitti di nome durante l'importazione dei dati dei Response Group al pool di backup, l'importazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="40294-120">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="40294-121">Per completare l'importazione e la procedura di failover, è necessario risolvere i conflitti di nome rinominando l'oggetto Response Group nel pool di backup o utilizzando il cmdlet **Import-CsRgsConfiguration** con il parametro –ResolveNameConflicts affinché risolva automaticamente il conflitto aggiungendo un numero di identificazione univoco all'oggetto Response Group.</span><span class="sxs-lookup"><span data-stu-id="40294-121">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="40294-p105">In generale, è consigliabile eseguire backup giornalieri, ma in presenza di un volume elevato di modifiche è possibile pianificare backup più frequenti. La quantità di informazioni che è possibile perdere in caso di emergenza varia in base alla frequenza dei backup, oltre che alla frequenza e al volume di modifiche.</span><span class="sxs-lookup"><span data-stu-id="40294-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="40294-124">È possibile importare i Response Group in un pool di backup prima di un'operazione di failover o di una situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="40294-124">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="40294-125">L'importazione anticipata dei Response Group consente di ridurre i tempi di inattività, poiché il servizio di risposta di Lync Server può essere ripristinato nel pool di backup non appena le chiamate vengono instradate al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-125">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40294-126">L'applicazione Response Group non è in grado di raggiungere gli agenti ospitati in un pool inattivo finché non è stato completato il failover.</span><span class="sxs-lookup"><span data-stu-id="40294-126">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="40294-127">Durante questo periodo, l'applicazione Response Group elabora le chiamate come se tali agenti non fossero disponibili.</span><span class="sxs-lookup"><span data-stu-id="40294-127">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="40294-128">Processo di ripristino di emergenza dei Response Group</span><span class="sxs-lookup"><span data-stu-id="40294-128">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="40294-129">In caso di emergenza, è possibile ripristinare i Response Group utilizzando uno dei seguenti metodi di ripristino:</span><span class="sxs-lookup"><span data-stu-id="40294-129">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="40294-130">Eseguire il failover su un pool di backup e quindi il failback sul pool originale.</span><span class="sxs-lookup"><span data-stu-id="40294-130">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="40294-131">Eseguire il failover su un pool di backup, creare un nuovo pool con un nome di dominio completo (FQDN) differente, quindi importare i Response Group nel nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="40294-131">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="40294-p108">Durante la fase di failover del ripristino di emergenza, i Response Group risiedono sia nel pool principale (non disponibile) che in quello di backup. Tali Response Group hanno lo stesso nome e lo stesso proprietario (il pool principale), ma padri diversi.</span><span class="sxs-lookup"><span data-stu-id="40294-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="40294-134">Quando si esegue il ripristino creando un nuovo pool con un FQDN diverso, è necessario assegnare il nuovo pool come proprietario dei Response Group al momento dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="40294-134">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="40294-135">La proprietà dei Response Group rimane nel pool originale se non viene esplicitamente riassegnata dall'utente utilizzando il parametro –OverwriteOwner con il cmdlet **Import-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="40294-135">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40294-136">È inoltre necessario utilizzare il parametro – OverwriteOwner se il pool è stato ricreato durante il ripristino (ovvero se il database di Response Group è vuoto), indipendentemente dal fatto che si utilizzi o meno lo stesso nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="40294-136">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="40294-137">Non è necessario utilizzare il parametro –OverwriteOwner se non si ricostruisce il pool, ma è possibile utilizzarlo ogniqualvolta si reimportano i Response Group nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="40294-137">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="40294-138">È possibile definire un solo set di impostazioni di configurazione dei Response Group a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="40294-138">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="40294-139">Le impostazioni includono la configurazione di musica di attesa predefinita, il file audio di musica di attesa predefinita, il periodo di tolleranza di richiamata agente e la configurazione del contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="40294-139">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="40294-140">Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="40294-140">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="40294-141">Per informazioni dettagliate sul cmdlet **Get-CsRgsConfiguration** , vedere [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="40294-141">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="40294-142">È possibile trasferire queste impostazioni a livello di applicazione da un pool a un altro utilizzando il cmdlet **Import-CsRgsConfiguration** con parametro –ReplaceExistingSettings. L'operazione tuttavia sostituisce le impostazioni nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40294-142">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="40294-p112">Il vincolo sul trasferimento di impostazioni a un altro pool è valido solo per le impostazioni a livello di applicazione e per il file audio della musica di attesa predefinita. Non si applica a gruppi di agenti, code, flussi di lavoro, orario di ufficio e set di festività.</span><span class="sxs-lookup"><span data-stu-id="40294-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="40294-p113">Se non si desidera sostituire le impostazioni a livello di applicazione nel pool di backup in caso di emergenza e il pool principale non può essere ripristinato, le impostazioni a livello di applicazione nel pool principale saranno perse. Se durante il ripristino è necessario creare un nuovo pool in sostituzione del pool principale con lo stesso FQDN o un FQDN diverso, non è possibile ripristinare le impostazioni a livello di applicazione originali. In questo caso, è necessario configurare il nuovo pool con queste impostazioni e includere il file audio di musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="40294-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="40294-148">Se in caso di emergenza si decide di trasferire le impostazioni a livello di applicazione dal pool principale a quello di backup utilizzando il cmdlet **Import-CsRgsConfiguration**, è possibile trasferire le impostazioni dal pool di backup al nuovo pool durante il ripristino nello stesso modo in cui le si è trasferite dal pool principale a quello di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-148">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="40294-149">Nella tabella seguente viene fornita una panoramica dei passaggi del processo di ripristino dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="40294-149">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="40294-150">Per informazioni dettagliate sull'esecuzione di questi passaggi, vedere [procedure di ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40294-150">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="40294-151">Procedura di ripristino di emergenza dei Response Group</span><span class="sxs-lookup"><span data-stu-id="40294-151">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40294-152">Fase</span><span class="sxs-lookup"><span data-stu-id="40294-152">Phase</span></span></th>
<th><span data-ttu-id="40294-153">Passaggi</span><span class="sxs-lookup"><span data-stu-id="40294-153">Steps</span></span></th>
<th><span data-ttu-id="40294-154">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="40294-154">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40294-155">Prima dell'interruzione</span><span class="sxs-lookup"><span data-stu-id="40294-155">Before outage</span></span></p></td>
<td><p><span data-ttu-id="40294-156">In base alla routine, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> per creare backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui viene distribuita l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="40294-156">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="40294-157">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40294-157">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40294-158">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40294-158">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40294-159">Durante l'interruzione</span><span class="sxs-lookup"><span data-stu-id="40294-159">During outage</span></span></p></td>
<td><p><span data-ttu-id="40294-160">Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare la configurazione del servizio di Response Group del backup di Lync Server dal pool primario al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-160">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40294-161">Utilizzare il parametro – ReplaceExistingSettings se si desidera sostituire le impostazioni del gruppo di risposta a livello di applicazione nel pool di backup con le impostazioni del pool primario.</span><span class="sxs-lookup"><span data-stu-id="40294-161">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="40294-162">Se le impostazioni a livello di applicazione del pool principale non vengono trasferite al pool di backup e il pool principale non può essere ripristinato, le impostazioni del pool principale andranno perse.</span><span class="sxs-lookup"><span data-stu-id="40294-162">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="40294-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40294-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40294-164">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40294-164">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40294-165">Dopo l'importazione</span><span class="sxs-lookup"><span data-stu-id="40294-165">After importing</span></span></p></td>
<td><p><span data-ttu-id="40294-166">Eseguire i cmdlet di Response Group con il parametro – ShowAll (per visualizzare tutti i Response Group) o il parametro – Owner (per visualizzare solo i Response Group importati) per verificare che tutte le configurazioni dei gruppi di risposta siano state importate nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-166">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="40294-167">Senza il parametro –ShowAll o –Owner, i Response Group importati nel pool di backup non saranno elencati nei risultati restituiti dai cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40294-167">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="40294-168">Eseguire i seguenti cmdlet:</span><span class="sxs-lookup"><span data-stu-id="40294-168">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="40294-169"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="40294-169"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-170"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="40294-170"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-171"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="40294-171"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-172"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="40294-172"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-173"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="40294-173"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="40294-174">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40294-174">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40294-175">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40294-175">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40294-176">Dopo il failover</span><span class="sxs-lookup"><span data-stu-id="40294-176">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="40294-177">Effettuare una chiamata di prova a un Response Group importato nel pool di backup e verificare che sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="40294-177">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="40294-178">Tutti gli agenti formali devono effettuare di nuovo l'accesso ai propri gruppi formali nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-178">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="40294-179">Gestire le modifiche di configurazione:</span><span class="sxs-lookup"><span data-stu-id="40294-179">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="40294-180">I Response Group contenuti nel pool di backup possono essere modificati come al solito durante l'interruzione, a prescindere se siano importati o di proprietà nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-180">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="40294-181">È necessario utilizzare Lync Server Management Shell per gestire i Response Group importati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-181">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="40294-182">Non è possibile utilizzare il pannello di controllo di Lync Server per gestire questi Response Group mentre si trovano nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-182">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="40294-183">N/D</span><span class="sxs-lookup"><span data-stu-id="40294-183">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40294-184">Dopo il ripristino e prima del failback</span><span class="sxs-lookup"><span data-stu-id="40294-184">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="40294-185">Eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> specificando il parametro -Source come pool di backup e il parametro –Owner come pool principale per esportare i Response Group di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-185">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="40294-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40294-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40294-187">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40294-187">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40294-188">Dopo il failback</span><span class="sxs-lookup"><span data-stu-id="40294-188">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="40294-189">Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare di nuovo i Response Group nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="40294-189">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40294-p116">Se il pool principale non è ripristinabile e in sostituzione viene distribuito un nuovo pool, utilizzare il parametro –ReplaceExistingSettings per trasferire le impostazione a livello di applicazione dal pool di backup al nuovo pool. In caso contrario, il nuovo pool utilizzerà le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="40294-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="40294-192">Eseguire i cmdlet riportati di seguito con il parametro –ShowAll, se si desidera visualizzare tutti i Response Group, o il parametro –Owner, se si desidera visualizzare solo i Response Group importati, per verificare che tutte le configurazioni dei Response Group siano state reimportate correttamente nel pool principale:</span><span class="sxs-lookup"><span data-stu-id="40294-192">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="40294-193"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="40294-193"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-194"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="40294-194"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-195"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="40294-195"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-196"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="40294-196"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="40294-197"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="40294-197"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="40294-198">Effettuare una chiamata di prova a un Response Group reimportato nel pool principale e verificare che sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="40294-198">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="40294-199">Facoltativamente, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> nel pool di backup con il parametro –RemoveExportedConfiguration per rimuovere i Response Group di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="40294-199">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="40294-200">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="40294-200">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="40294-201">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="40294-201">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

