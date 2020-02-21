---
title: 'Lync Server 2013: autorizzazioni e prerequisiti per la configurazione di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e27d3495ce2152dee67a5f176c4a0d9f7e7f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="bad02-102">Autorizzazioni e prerequisiti per la configurazione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bad02-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bad02-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="bad02-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bad02-p101">Response Group è una funzionalità di gestione della chiamate VoIP aziendale. In questo argomento vengono indicati i componenti di cui è necessario disporre prima di poter configurare Response Group e le credenziali e le autorizzazioni amministrative richieste per eseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bad02-p101">Response Group is an Enterprise Voice call management feature. This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="bad02-106">In questa sezione si presuppone la lettura della documentazione relativa alla pianificazione correlata a Response Group.</span><span class="sxs-lookup"><span data-stu-id="bad02-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="bad02-107">Per informazioni dettagliate, vedere [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="bad02-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="bad02-108">Strumenti di configurazione e ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="bad02-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="bad02-109">È possibile utilizzare gli strumenti di amministrazione seguenti per configurare Response Group:</span><span class="sxs-lookup"><span data-stu-id="bad02-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="bad02-110">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="bad02-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="bad02-111">Strumento di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="bad02-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="bad02-112">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="bad02-112">Lync Server Management Shell</span></span>

<span data-ttu-id="bad02-113">Per configurare i Response Group, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bad02-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bad02-114"><strong>Gruppo di sicurezza Active Directory (1)</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="bad02-115">Creare flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bad02-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="bad02-116">Assegnare responsabile</span><span class="sxs-lookup"><span data-stu-id="bad02-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="bad02-117">Creare/assegnare agenti, code</span><span class="sxs-lookup"><span data-stu-id="bad02-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="bad02-118">Creare/gestire festività e orari di ufficio</span><span class="sxs-lookup"><span data-stu-id="bad02-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="bad02-119">Attivare/disattivare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="bad02-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="bad02-120">Configurare il flusso di lavoro (IVR o gruppo di risposta)</span><span class="sxs-lookup"><span data-stu-id="bad02-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad02-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="bad02-122">√</span><span class="sxs-lookup"><span data-stu-id="bad02-122">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-123">√</span><span class="sxs-lookup"><span data-stu-id="bad02-123">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-124">√</span><span class="sxs-lookup"><span data-stu-id="bad02-124">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-125">√</span><span class="sxs-lookup"><span data-stu-id="bad02-125">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-126">√</span><span class="sxs-lookup"><span data-stu-id="bad02-126">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-127">√</span><span class="sxs-lookup"><span data-stu-id="bad02-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad02-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="bad02-129">√ (2)</span><span class="sxs-lookup"><span data-stu-id="bad02-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="bad02-130">√ (3)</span><span class="sxs-lookup"><span data-stu-id="bad02-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="bad02-131">√ (3)</span><span class="sxs-lookup"><span data-stu-id="bad02-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="bad02-132">√ (3)</span><span class="sxs-lookup"><span data-stu-id="bad02-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="bad02-133">√ (3)</span><span class="sxs-lookup"><span data-stu-id="bad02-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad02-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="bad02-135">√</span><span class="sxs-lookup"><span data-stu-id="bad02-135">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-136">√</span><span class="sxs-lookup"><span data-stu-id="bad02-136">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-137">√</span><span class="sxs-lookup"><span data-stu-id="bad02-137">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-138">√</span><span class="sxs-lookup"><span data-stu-id="bad02-138">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-139">√</span><span class="sxs-lookup"><span data-stu-id="bad02-139">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-140">√</span><span class="sxs-lookup"><span data-stu-id="bad02-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad02-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="bad02-142">√</span><span class="sxs-lookup"><span data-stu-id="bad02-142">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-143">√</span><span class="sxs-lookup"><span data-stu-id="bad02-143">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-144">√</span><span class="sxs-lookup"><span data-stu-id="bad02-144">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-145">√</span><span class="sxs-lookup"><span data-stu-id="bad02-145">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-146">√</span><span class="sxs-lookup"><span data-stu-id="bad02-146">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-147">√</span><span class="sxs-lookup"><span data-stu-id="bad02-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad02-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="bad02-149">√</span><span class="sxs-lookup"><span data-stu-id="bad02-149">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-150">√</span><span class="sxs-lookup"><span data-stu-id="bad02-150">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-151">√</span><span class="sxs-lookup"><span data-stu-id="bad02-151">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-152">√</span><span class="sxs-lookup"><span data-stu-id="bad02-152">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-153">√</span><span class="sxs-lookup"><span data-stu-id="bad02-153">√</span></span></p></td>
<td><p><span data-ttu-id="bad02-154">√</span><span class="sxs-lookup"><span data-stu-id="bad02-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad02-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="bad02-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="bad02-156">√ (4)</span><span class="sxs-lookup"><span data-stu-id="bad02-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="bad02-157">√ (4)</span><span class="sxs-lookup"><span data-stu-id="bad02-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="bad02-158">√ (4)</span><span class="sxs-lookup"><span data-stu-id="bad02-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="bad02-159">√ (4)</span><span class="sxs-lookup"><span data-stu-id="bad02-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="bad02-160">√ (4)</span><span class="sxs-lookup"><span data-stu-id="bad02-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="bad02-161">√ (4)</span><span class="sxs-lookup"><span data-stu-id="bad02-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bad02-162"><STRONG>(1)</STRONG> un oggetto utente di servizi di dominio Active Directory deve essere membro del gruppo di sicurezza di Active Directory specificato elencato.</span><span class="sxs-lookup"><span data-stu-id="bad02-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="bad02-163">Un amministratore o un altro membro del gruppo di Active Directory delegato con le autorizzazioni appropriate per aggiungere gli utenti a un gruppo di sicurezza (ad esempio, Administrator, account Operators) deve aggiungere un oggetto utente al gruppo o al gruppo di sicurezza elencato affinché l'utente possa eseguire le funzioni elencate.</span><span class="sxs-lookup"><span data-stu-id="bad02-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="bad02-164"><STRONG>(2)</STRONG> solo per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="bad02-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="bad02-165"><STRONG>(3)</STRONG> un responsabile di Response Group può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro che il Manager corrente gestisce già.</span><span class="sxs-lookup"><span data-stu-id="bad02-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="bad02-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator è in grado di eseguire solo i cmdlet "Get" di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bad02-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="bad02-167">Prerequisiti di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="bad02-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="bad02-168">Per Response Group sono necessari i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bad02-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="bad02-169">Servizio applicazione</span><span class="sxs-lookup"><span data-stu-id="bad02-169">Application service</span></span>

  - <span data-ttu-id="bad02-170">Applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="bad02-170">Response Group application</span></span>

  - <span data-ttu-id="bad02-171">Language Pack</span><span class="sxs-lookup"><span data-stu-id="bad02-171">Language packs</span></span>

  - <span data-ttu-id="bad02-172">Archivio file (per gestire i file audio)</span><span class="sxs-lookup"><span data-stu-id="bad02-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="bad02-173">Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)</span><span class="sxs-lookup"><span data-stu-id="bad02-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="bad02-174">Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bad02-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="bad02-175">Prima di configurare Response Group potrebbe essere necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="bad02-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="bad02-176">Abilitare gli utenti per Lync Server 2013 e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bad02-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="bad02-177">Modificare un file di configurazione in modo che sia conforme agli standard FIPS (Federal Information Processing Standard).</span><span class="sxs-lookup"><span data-stu-id="bad02-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="bad02-178">Modificare le regole di confronto del database per supportare caratteri Yi, Meng e Zang per i nomi di code e i nomi dei gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="bad02-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="bad02-179">Abilitazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="bad02-179">Enabling Users</span></span>

<span data-ttu-id="bad02-180">Il primo passaggio per la configurazione di Response Group consiste nella creazione di gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="bad02-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="bad02-181">Prima di poter creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti di Response Group per Lync Server 2013 e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bad02-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="bad02-182">L'abilitazione degli utenti per Lync Server 2013 è in genere un passaggio del server Enterprise Edition o della distribuzione del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bad02-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="bad02-183">Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riabilitare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="bad02-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="bad02-184">L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio della distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bad02-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="bad02-185">Per ulteriori informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="bad02-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="bad02-186">Conformità ai requisiti FIPS</span><span class="sxs-lookup"><span data-stu-id="bad02-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="bad02-187">Fare riferimento a questa sezione solo se l'organizzazione deve essere conforme agli standard FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="bad02-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="bad02-188">Per essere conformi a FIPS, è necessario modificare il file Web.config a livello dell'applicazione in modo da usare un algoritmo di crittografia diverso dopo aver installato Servizi Web.</span><span class="sxs-lookup"><span data-stu-id="bad02-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="bad02-189">È necessario specificare l'uso dell'algoritmo 3DES (Triple Data Encryption Standard) per ASP.NET per l'elaborazione dei dati sugli stati di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bad02-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="bad02-190">Per l'applicazione Response Group, questo requisito si applica allo strumento di configurazione di Response Group e alla console di accesso e disconnessione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="bad02-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="bad02-191">Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "è possibile che venga visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET che dispongono di ViewState abilitato dopo l'aggiornamento da ASP.NET [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)1,1 a ASP.NET 2,0" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="bad02-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="bad02-192">Per modificare il file Web.config, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bad02-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="bad02-193">In un editor di testo come Blocco note aprire il file Web.config a livello dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bad02-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="bad02-194">Nel file Web. config individuare la `<system.web>` sezione.</span><span class="sxs-lookup"><span data-stu-id="bad02-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="bad02-195">Aggiungere la sezione `<machineKey>` seguente alla `<system.web>` sezione:</span><span class="sxs-lookup"><span data-stu-id="bad02-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="bad02-196">Salvare il file Web.config.</span><span class="sxs-lookup"><span data-stu-id="bad02-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="bad02-197">Riavviare il servizio Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="bad02-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="bad02-198">Supporto di caratteri Yi, Meng e Zang</span><span class="sxs-lookup"><span data-stu-id="bad02-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="bad02-199">Fare riferimento a questa sezione solo se l'organizzazione richiede il supporto di caratteri Yi, Meng o Zang.</span><span class="sxs-lookup"><span data-stu-id="bad02-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bad02-200">Per informazioni su ciò che sono i caratteri Yi, Meng e Zang e il motivo per cui possono essere importanti per la distribuzione, vedere le informazioni sui set <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>di caratteri di GB18030.</span><span class="sxs-lookup"><span data-stu-id="bad02-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="bad02-p106">Per il supporto di caratteri Yi, Meng o Zang è necessario modificare le regole di confronto del database Rgsconfig. Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti di ogni database Rgsconfig:</span><span class="sxs-lookup"><span data-stu-id="bad02-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="bad02-203">dbo. AgentGroups</span><span class="sxs-lookup"><span data-stu-id="bad02-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="bad02-204">dbo. BusinessHours</span><span class="sxs-lookup"><span data-stu-id="bad02-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="bad02-205">dbo. HolidaySets</span><span class="sxs-lookup"><span data-stu-id="bad02-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="bad02-206">dbo. Code</span><span class="sxs-lookup"><span data-stu-id="bad02-206">dbo.Queues</span></span>

  - <span data-ttu-id="bad02-207">dbo. Flussi</span><span class="sxs-lookup"><span data-stu-id="bad02-207">dbo.Workflows</span></span>

<span data-ttu-id="bad02-208">Per SQL Server 2008 R2 e SQL Server 2012, utilizzare le regole\_di\_confronto per la lingua latina generale 100 (accento sensibile).</span><span class="sxs-lookup"><span data-stu-id="bad02-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="bad02-209">Se si utilizzano queste regole di confronto, la distinzione tra maiuscole e minuscole non viene applicata ad alcun nome di oggetto.</span><span class="sxs-lookup"><span data-stu-id="bad02-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="bad02-210">È possibile modificare le regole di confronto utilizzando Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bad02-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="bad02-211">Per informazioni dettagliate sull'utilizzo di questo strumento, vedere "using SQL Server Management Studio [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="bad02-211">For details about using this tool, see "Using SQL Server Management Studio" at [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="bad02-212">Per modificare le regole di confronto, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bad02-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="bad02-213">Verificare che SQL Server Management Studio sia configurato per consentire modifiche che richiedono la ricreazione di tabelle.</span><span class="sxs-lookup"><span data-stu-id="bad02-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="bad02-214">Per informazioni dettagliate, vedere la finestra di dialogo "Salva (non consentita)" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186).</span><span class="sxs-lookup"><span data-stu-id="bad02-214">For details, see "Save (Not Permitted) Dialog Box" at [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="bad02-215">Per informazioni dettagliate sull'impostazione di una regola di confronto delle colonne, vedere "procedura: impostare le regole di confronto delle colonne ( [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185)Visual Database Tools)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="bad02-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="bad02-216">Utilizzando Microsoft SQL Server Management Studio connettersi al database Rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="bad02-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="bad02-217">Trovare la tabella che si desidera modificare nel database Rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e quindi scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="bad02-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="bad02-218">Modificare le regole di confronto della colonna **Name** e salvare la tabella.</span><span class="sxs-lookup"><span data-stu-id="bad02-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

