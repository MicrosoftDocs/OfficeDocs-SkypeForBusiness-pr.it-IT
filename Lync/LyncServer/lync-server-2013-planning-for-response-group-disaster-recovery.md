---
title: 'Lync Server 2013: pianificazione per il ripristino di emergenza di Response Group'
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
ms.openlocfilehash: 049e07e72efba508add2135c6b77aebed2c38954
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="5a9a0-102">Pianificazione del ripristino di emergenza di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a9a0-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a9a0-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5a9a0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5a9a0-104">In questa sezione vengono illustrati alcuni modi per preparare i Response Group per ripristini di emergenza e fornita una panoramica del processo di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="5a9a0-105">Preparazione per il ripristino di emergenza di Response Group</span><span class="sxs-lookup"><span data-stu-id="5a9a0-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="5a9a0-106">Durante la preparazione e l'esecuzione delle procedure di ripristino di emergenza, tenere presente quanto segue.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a9a0-107">In un ambiente di coesistenza, solo i Response Group di Lync Server 2013 sono supportati per le procedure di ripristino di emergenza descritte in questo documento.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="5a9a0-108">Pianificare il ripristino di emergenza durante la pianificazione delle capacità.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="5a9a0-109">Per le capacità del ripristino di emergenza, ogni pool appartenente a una coppia deve essere in grado di gestire i carichi di lavoro di tutti i Response Group di entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="5a9a0-110">Per informazioni dettagliate sulla pianificazione della capacità dei Response Group, vedere [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="5a9a0-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="5a9a0-111">Eseguire regolarmente copie di backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui è stata distribuita l'applicazione Response Group utilizzando la procedura di esportazione descritta in questo documento.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="5a9a0-112">Per ulteriori informazioni, vedere [procedure di ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5a9a0-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="5a9a0-113">Conservare le copie di backup in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="5a9a0-114">Mantenere una copia di backup distinta di tutti i file audio originali utilizzati per l'applicazione Response Group, incluse le registrazioni e i file musicali in attesa.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="5a9a0-115">Conservare le copie di backup in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="5a9a0-116">Per il ripristino di emergenza di Lync Server 2013, tutte le impostazioni di Response Group devono avere nomi univoci nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="5a9a0-117">Questo requisito si applica a flussi di lavoro, code, gruppi di agenti, set di festività e orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="5a9a0-118">È opportuno verificare che questo requisito sia soddisfatto quando i pool principale e di backup sono ancora attivi e prima di avviare una procedura di failover.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="5a9a0-119">Se vengono rilevati conflitti di nome durante l'importazione dei dati dei Response Group al pool di backup, l'importazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="5a9a0-120">Per completare l'importazione e la procedura di failover, è necessario risolvere i conflitti di nome rinominando l'oggetto Response Group nel pool di backup o utilizzando il cmdlet **Import-CsRgsConfiguration** con il parametro –ResolveNameConflicts affinché risolva automaticamente il conflitto aggiungendo un numero di identificazione univoco all'oggetto Response Group.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="5a9a0-p105">In generale, è consigliabile eseguire backup giornalieri, ma in presenza di un volume elevato di modifiche è possibile pianificare backup più frequenti. La quantità di informazioni che è possibile perdere in caso di emergenza varia in base alla frequenza dei backup, oltre che alla frequenza e al volume di modifiche.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="5a9a0-123">È possibile importare i Response Group in un pool di backup prima di un'operazione di failover o di una situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="5a9a0-124">L'importazione anticipata dei Response Group consente di ridurre i tempi di inattività, poiché il servizio di risposta di Lync Server può essere ripristinato nel pool di backup non appena le chiamate vengono instradate al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a9a0-125">L'applicazione Response Group non è in grado di raggiungere gli agenti ospitati in un pool inattivo finché non è stato completato il failover.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="5a9a0-126">Durante questo periodo, l'applicazione Response Group elabora le chiamate come se tali agenti non fossero disponibili.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="5a9a0-127">Processo di ripristino di emergenza dei Response Group</span><span class="sxs-lookup"><span data-stu-id="5a9a0-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="5a9a0-128">In caso di emergenza, è possibile ripristinare i Response Group utilizzando uno dei seguenti metodi di ripristino:</span><span class="sxs-lookup"><span data-stu-id="5a9a0-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="5a9a0-129">Eseguire il failover su un pool di backup e quindi il failback sul pool originale.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="5a9a0-130">Eseguire il failover su un pool di backup, creare un nuovo pool con un nome di dominio completo (FQDN) differente, quindi importare i Response Group nel nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="5a9a0-p108">Durante la fase di failover del ripristino di emergenza, i Response Group risiedono sia nel pool principale (non disponibile) che in quello di backup. Tali Response Group hanno lo stesso nome e lo stesso proprietario (il pool principale), ma padri diversi.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="5a9a0-133">Quando si esegue il ripristino creando un nuovo pool con un FQDN diverso, è necessario assegnare il nuovo pool come proprietario dei Response Group al momento dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="5a9a0-134">La proprietà dei Response Group rimane nel pool originale se non viene esplicitamente riassegnata dall'utente utilizzando il parametro –OverwriteOwner con il cmdlet **Import-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a9a0-135">È inoltre necessario utilizzare il parametro – OverwriteOwner se il pool è stato ricreato durante il ripristino (ovvero se il database di Response Group è vuoto), indipendentemente dal fatto che si utilizzi o meno lo stesso nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="5a9a0-136">Non è necessario utilizzare il parametro –OverwriteOwner se non si ricostruisce il pool, ma è possibile utilizzarlo ogniqualvolta si reimportano i Response Group nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="5a9a0-137">È possibile definire un solo set di impostazioni di configurazione dei Response Group a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="5a9a0-138">Le impostazioni includono la configurazione di musica di attesa predefinita, il file audio di musica di attesa predefinita, il periodo di tolleranza di richiamata agente e la configurazione del contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="5a9a0-139">Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="5a9a0-140">Per informazioni dettagliate sul cmdlet **Get-CsRgsConfiguration** , vedere [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="5a9a0-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="5a9a0-141">È possibile trasferire queste impostazioni a livello di applicazione da un pool a un altro utilizzando il cmdlet **Import-CsRgsConfiguration** con parametro –ReplaceExistingSettings. L'operazione tuttavia sostituisce le impostazioni nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a9a0-p112">Il vincolo sul trasferimento di impostazioni a un altro pool è valido solo per le impostazioni a livello di applicazione e per il file audio della musica di attesa predefinita. Non si applica a gruppi di agenti, code, flussi di lavoro, orario di ufficio e set di festività.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="5a9a0-p113">Se non si desidera sostituire le impostazioni a livello di applicazione nel pool di backup in caso di emergenza e il pool principale non può essere ripristinato, le impostazioni a livello di applicazione nel pool principale saranno perse. Se durante il ripristino è necessario creare un nuovo pool in sostituzione del pool principale con lo stesso FQDN o un FQDN diverso, non è possibile ripristinare le impostazioni a livello di applicazione originali. In questo caso, è necessario configurare il nuovo pool con queste impostazioni e includere il file audio di musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="5a9a0-147">Se in caso di emergenza si decide di trasferire le impostazioni a livello di applicazione dal pool principale a quello di backup utilizzando il cmdlet **Import-CsRgsConfiguration**, è possibile trasferire le impostazioni dal pool di backup al nuovo pool durante il ripristino nello stesso modo in cui le si è trasferite dal pool principale a quello di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="5a9a0-148">Nella tabella seguente viene fornita una panoramica dei passaggi del processo di ripristino dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="5a9a0-149">Per informazioni dettagliate sull'esecuzione di questi passaggi, vedere [procedure di ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5a9a0-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="5a9a0-150">Procedura di ripristino di emergenza dei Response Group</span><span class="sxs-lookup"><span data-stu-id="5a9a0-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a9a0-151">Fase</span><span class="sxs-lookup"><span data-stu-id="5a9a0-151">Phase</span></span></th>
<th><span data-ttu-id="5a9a0-152">Passaggi</span><span class="sxs-lookup"><span data-stu-id="5a9a0-152">Steps</span></span></th>
<th><span data-ttu-id="5a9a0-153">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="5a9a0-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a9a0-154">Prima dell'interruzione</span><span class="sxs-lookup"><span data-stu-id="5a9a0-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="5a9a0-155">In base alla routine, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> per creare backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui viene distribuita l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="5a9a0-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5a9a0-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5a9a0-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5a9a0-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a9a0-158">Durante l'interruzione</span><span class="sxs-lookup"><span data-stu-id="5a9a0-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="5a9a0-159">Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare la configurazione del servizio di Response Group del backup di Lync Server dal pool primario al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5a9a0-160">Utilizzare il parametro – ReplaceExistingSettings se si desidera sostituire le impostazioni del gruppo di risposta a livello di applicazione nel pool di backup con le impostazioni del pool primario.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="5a9a0-161">Se le impostazioni a livello di applicazione del pool principale non vengono trasferite al pool di backup e il pool principale non può essere ripristinato, le impostazioni del pool principale andranno perse.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="5a9a0-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5a9a0-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5a9a0-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5a9a0-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a9a0-164">Dopo l'importazione</span><span class="sxs-lookup"><span data-stu-id="5a9a0-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="5a9a0-165">Eseguire i cmdlet di Response Group con il parametro – ShowAll (per visualizzare tutti i Response Group) o il parametro – Owner (per visualizzare solo i Response Group importati) per verificare che tutte le configurazioni dei gruppi di risposta siano state importate nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5a9a0-166">Senza il parametro –ShowAll o –Owner, i Response Group importati nel pool di backup non saranno elencati nei risultati restituiti dai cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="5a9a0-167">Eseguire i seguenti cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5a9a0-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a9a0-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a9a0-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5a9a0-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5a9a0-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5a9a0-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a9a0-175">Dopo il failover</span><span class="sxs-lookup"><span data-stu-id="5a9a0-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5a9a0-176">Effettuare una chiamata di prova a un Response Group importato nel pool di backup e verificare che sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="5a9a0-177">Tutti gli agenti formali devono effettuare di nuovo l'accesso ai propri gruppi formali nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="5a9a0-178">Gestire le modifiche di configurazione:</span><span class="sxs-lookup"><span data-stu-id="5a9a0-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="5a9a0-179">I Response Group contenuti nel pool di backup possono essere modificati come al solito durante l'interruzione, a prescindere se siano importati o di proprietà nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5a9a0-180">È necessario utilizzare Lync Server Management Shell per gestire i Response Group importati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="5a9a0-181">Non è possibile utilizzare il pannello di controllo di Lync Server per gestire questi Response Group mentre si trovano nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="5a9a0-182">N/D</span><span class="sxs-lookup"><span data-stu-id="5a9a0-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a9a0-183">Dopo il ripristino e prima del failback</span><span class="sxs-lookup"><span data-stu-id="5a9a0-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="5a9a0-184">Eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> specificando il parametro -Source come pool di backup e il parametro –Owner come pool principale per esportare i Response Group di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="5a9a0-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5a9a0-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5a9a0-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5a9a0-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a9a0-187">Dopo il failback</span><span class="sxs-lookup"><span data-stu-id="5a9a0-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5a9a0-188">Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare di nuovo i Response Group nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5a9a0-p116">Se il pool principale non è ripristinabile e in sostituzione viene distribuito un nuovo pool, utilizzare il parametro –ReplaceExistingSettings per trasferire le impostazione a livello di applicazione dal pool di backup al nuovo pool. In caso contrario, il nuovo pool utilizzerà le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="5a9a0-191">Eseguire i cmdlet riportati di seguito con il parametro –ShowAll, se si desidera visualizzare tutti i Response Group, o il parametro –Owner, se si desidera visualizzare solo i Response Group importati, per verificare che tutte le configurazioni dei Response Group siano state reimportate correttamente nel pool principale:</span><span class="sxs-lookup"><span data-stu-id="5a9a0-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a9a0-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="5a9a0-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="5a9a0-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="5a9a0-197">Effettuare una chiamata di prova a un Response Group reimportato nel pool principale e verificare che sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="5a9a0-198">Facoltativamente, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> nel pool di backup con il parametro –RemoveExportedConfiguration per rimuovere i Response Group di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5a9a0-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a9a0-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5a9a0-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5a9a0-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5a9a0-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

