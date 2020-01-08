---
title: 'Lync Server 2013: Autorizzazioni e prerequisiti per la configurazione di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="80493-102">Autorizzazioni e prerequisiti per la configurazione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80493-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80493-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="80493-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="80493-104">Response Group è una caratteristica di gestione delle chiamate vocali aziendali.</span><span class="sxs-lookup"><span data-stu-id="80493-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="80493-105">Questo argomento descrive le informazioni necessarie per configurare Response Group e le credenziali amministrative e le autorizzazioni necessarie per eseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="80493-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="80493-106">Questa sezione presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="80493-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="80493-107">Per informazioni dettagliate, vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="80493-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="80493-108">Strumenti di configurazione e ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="80493-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="80493-109">È possibile usare gli strumenti di amministrazione seguenti per configurare Response Group:</span><span class="sxs-lookup"><span data-stu-id="80493-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="80493-110">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="80493-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="80493-111">Strumento di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="80493-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="80493-112">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="80493-112">Lync Server Management Shell</span></span>

<span data-ttu-id="80493-113">Per configurare i Response Groups, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80493-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


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
<td><p><span data-ttu-id="80493-114"><strong>Gruppo di sicurezza di Active Directory (1)</strong></span><span class="sxs-lookup"><span data-stu-id="80493-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="80493-115">Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="80493-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="80493-116">Assegna Manager</span><span class="sxs-lookup"><span data-stu-id="80493-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="80493-117">Creare agenti/Assign, code</span><span class="sxs-lookup"><span data-stu-id="80493-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="80493-118">Creare/gestire le festività e le ore lavorative</span><span class="sxs-lookup"><span data-stu-id="80493-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="80493-119">Attivare/disattivare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="80493-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="80493-120">Configurare il flusso di lavoro (IVR o gruppo di caccia)</span><span class="sxs-lookup"><span data-stu-id="80493-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80493-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="80493-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="80493-122">√</span><span class="sxs-lookup"><span data-stu-id="80493-122">√</span></span></p></td>
<td><p><span data-ttu-id="80493-123">√</span><span class="sxs-lookup"><span data-stu-id="80493-123">√</span></span></p></td>
<td><p><span data-ttu-id="80493-124">√</span><span class="sxs-lookup"><span data-stu-id="80493-124">√</span></span></p></td>
<td><p><span data-ttu-id="80493-125">√</span><span class="sxs-lookup"><span data-stu-id="80493-125">√</span></span></p></td>
<td><p><span data-ttu-id="80493-126">√</span><span class="sxs-lookup"><span data-stu-id="80493-126">√</span></span></p></td>
<td><p><span data-ttu-id="80493-127">√</span><span class="sxs-lookup"><span data-stu-id="80493-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80493-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="80493-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="80493-129">√ (2)</span><span class="sxs-lookup"><span data-stu-id="80493-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="80493-130">√ (3)</span><span class="sxs-lookup"><span data-stu-id="80493-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="80493-131">√ (3)</span><span class="sxs-lookup"><span data-stu-id="80493-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="80493-132">√ (3)</span><span class="sxs-lookup"><span data-stu-id="80493-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="80493-133">√ (3)</span><span class="sxs-lookup"><span data-stu-id="80493-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80493-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="80493-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="80493-135">√</span><span class="sxs-lookup"><span data-stu-id="80493-135">√</span></span></p></td>
<td><p><span data-ttu-id="80493-136">√</span><span class="sxs-lookup"><span data-stu-id="80493-136">√</span></span></p></td>
<td><p><span data-ttu-id="80493-137">√</span><span class="sxs-lookup"><span data-stu-id="80493-137">√</span></span></p></td>
<td><p><span data-ttu-id="80493-138">√</span><span class="sxs-lookup"><span data-stu-id="80493-138">√</span></span></p></td>
<td><p><span data-ttu-id="80493-139">√</span><span class="sxs-lookup"><span data-stu-id="80493-139">√</span></span></p></td>
<td><p><span data-ttu-id="80493-140">√</span><span class="sxs-lookup"><span data-stu-id="80493-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80493-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="80493-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="80493-142">√</span><span class="sxs-lookup"><span data-stu-id="80493-142">√</span></span></p></td>
<td><p><span data-ttu-id="80493-143">√</span><span class="sxs-lookup"><span data-stu-id="80493-143">√</span></span></p></td>
<td><p><span data-ttu-id="80493-144">√</span><span class="sxs-lookup"><span data-stu-id="80493-144">√</span></span></p></td>
<td><p><span data-ttu-id="80493-145">√</span><span class="sxs-lookup"><span data-stu-id="80493-145">√</span></span></p></td>
<td><p><span data-ttu-id="80493-146">√</span><span class="sxs-lookup"><span data-stu-id="80493-146">√</span></span></p></td>
<td><p><span data-ttu-id="80493-147">√</span><span class="sxs-lookup"><span data-stu-id="80493-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80493-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="80493-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="80493-149">√</span><span class="sxs-lookup"><span data-stu-id="80493-149">√</span></span></p></td>
<td><p><span data-ttu-id="80493-150">√</span><span class="sxs-lookup"><span data-stu-id="80493-150">√</span></span></p></td>
<td><p><span data-ttu-id="80493-151">√</span><span class="sxs-lookup"><span data-stu-id="80493-151">√</span></span></p></td>
<td><p><span data-ttu-id="80493-152">√</span><span class="sxs-lookup"><span data-stu-id="80493-152">√</span></span></p></td>
<td><p><span data-ttu-id="80493-153">√</span><span class="sxs-lookup"><span data-stu-id="80493-153">√</span></span></p></td>
<td><p><span data-ttu-id="80493-154">√</span><span class="sxs-lookup"><span data-stu-id="80493-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80493-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="80493-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="80493-156">√ (4)</span><span class="sxs-lookup"><span data-stu-id="80493-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="80493-157">√ (4)</span><span class="sxs-lookup"><span data-stu-id="80493-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="80493-158">√ (4)</span><span class="sxs-lookup"><span data-stu-id="80493-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="80493-159">√ (4)</span><span class="sxs-lookup"><span data-stu-id="80493-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="80493-160">√ (4)</span><span class="sxs-lookup"><span data-stu-id="80493-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="80493-161">√ (4)</span><span class="sxs-lookup"><span data-stu-id="80493-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="80493-162"><STRONG>(1)</STRONG> un oggetto utente di servizi di dominio Active Directory deve essere un membro del gruppo di sicurezza Active Directory specificato elencato.</span><span class="sxs-lookup"><span data-stu-id="80493-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="80493-163">Un amministratore o un altro membro del gruppo di Active Directory delegato con le autorizzazioni appropriate per aggiungere utenti a un gruppo di sicurezza, ad esempio Administrator, account Operators, deve aggiungere un oggetto utente al gruppo di sicurezza o al gruppo di protezione elencato per consentire all'utente di eseguire le funzioni elencate.</span><span class="sxs-lookup"><span data-stu-id="80493-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="80493-164"><STRONG>(2)</STRONG> solo per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="80493-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="80493-165"><STRONG>(3)</STRONG> un responsabile del gruppo di risposte può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro già gestito da gestione corrente.</span><span class="sxs-lookup"><span data-stu-id="80493-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="80493-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator può eseguire solo il verbo "ottenere" i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="80493-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="80493-167">Prerequisiti per la configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="80493-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="80493-168">Response Group richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="80493-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="80493-169">Servizio applicazione</span><span class="sxs-lookup"><span data-stu-id="80493-169">Application service</span></span>

  - <span data-ttu-id="80493-170">Response Group Application</span><span class="sxs-lookup"><span data-stu-id="80493-170">Response Group application</span></span>

  - <span data-ttu-id="80493-171">Language Pack</span><span class="sxs-lookup"><span data-stu-id="80493-171">Language packs</span></span>

  - <span data-ttu-id="80493-172">Archivio file (per contenere i file audio)</span><span class="sxs-lookup"><span data-stu-id="80493-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="80493-173">Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)</span><span class="sxs-lookup"><span data-stu-id="80493-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="80493-174">Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="80493-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="80493-175">Potrebbe essere necessario eseguire le attività seguenti prima di configurare Response Group:</span><span class="sxs-lookup"><span data-stu-id="80493-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="80493-176">Consentire agli utenti di Lync Server 2013 e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="80493-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="80493-177">Modificare un file di configurazione per essere conforme alle norme FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="80493-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="80493-178">Modificare le regole di confronto del database per supportare i caratteri Yi, Meng e Zang per i nomi delle code e i nomi dei gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="80493-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="80493-179">Abilitazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="80493-179">Enabling Users</span></span>

<span data-ttu-id="80493-180">Il primo passaggio della configurazione di Response Group consiste nel creare gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="80493-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="80493-181">Prima di poter creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti per Response Group per Lync Server 2013 e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="80493-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="80493-182">L'abilitazione degli utenti per Lync Server 2013 è in genere un passaggio nel server Enterprise Edition o nella distribuzione di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="80493-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="80493-183">Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riattivare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="80493-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="80493-184">L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio nella distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="80493-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="80493-185">Per informazioni dettagliate, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="80493-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="80493-186">Conformità ai requisiti FIPS</span><span class="sxs-lookup"><span data-stu-id="80493-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="80493-187">Questa sezione si applica solo se l'organizzazione deve essere conforme alle norme FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="80493-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="80493-188">Per essere conformi con FIPS, è necessario modificare il file Web. config a livello di applicazione per usare un algoritmo di crittografia diverso dopo l'installazione dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="80493-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="80493-189">Devi specificare che ASP.NET usa l'algoritmo 3DES (Triple Data Encryption Standard) per elaborare i dati sullo stato di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="80493-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="80493-190">Per l'applicazione Response Group, questo requisito si applica allo strumento di configurazione dei gruppi di risposta e alla console di accesso e disconnessione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="80493-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="80493-191">Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "potrebbe essere visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET che hanno ViewState abilitato dopo l'aggiornamento da ASP.NET 1,1 a ASP.NET [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)2,0".</span><span class="sxs-lookup"><span data-stu-id="80493-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="80493-192">Per modificare il file Web. config, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80493-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="80493-193">In un editor di testo, ad esempio Blocco note, aprire il file Web. config a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="80493-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="80493-194">Nel file Web. config individuare la `<system.web>` sezione.</span><span class="sxs-lookup"><span data-stu-id="80493-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="80493-195">Aggiungere la sezione `<machineKey>` seguente alla `<system.web>` sezione:</span><span class="sxs-lookup"><span data-stu-id="80493-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="80493-196">Salvare il file Web. config.</span><span class="sxs-lookup"><span data-stu-id="80493-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="80493-197">Riavviare il servizio Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="80493-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="80493-198">Supporto di caratteri Yi, Meng e Zang</span><span class="sxs-lookup"><span data-stu-id="80493-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="80493-199">Questa sezione si applica solo se l'organizzazione deve supportare i caratteri Yi, Meng o Zang.</span><span class="sxs-lookup"><span data-stu-id="80493-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80493-200">Per informazioni sui caratteri di Yi, Meng e Zang e sul motivo per cui potrebbero essere importanti per la distribuzione, vedere le informazioni sui set <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>di caratteri GB18030.</span><span class="sxs-lookup"><span data-stu-id="80493-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="80493-201">Per supportare i caratteri Yi, Meng o Zang, è necessario modificare le regole di confronto per il database rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="80493-201">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database.</span></span> <span data-ttu-id="80493-202">Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti in ogni database di rgsconfig:</span><span class="sxs-lookup"><span data-stu-id="80493-202">Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="80493-203">dbo. AgentGroups</span><span class="sxs-lookup"><span data-stu-id="80493-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="80493-204">dbo. BusinessHours</span><span class="sxs-lookup"><span data-stu-id="80493-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="80493-205">dbo. HolidaySets</span><span class="sxs-lookup"><span data-stu-id="80493-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="80493-206">dbo. Code</span><span class="sxs-lookup"><span data-stu-id="80493-206">dbo.Queues</span></span>

  - <span data-ttu-id="80493-207">dbo. Flussi</span><span class="sxs-lookup"><span data-stu-id="80493-207">dbo.Workflows</span></span>

<span data-ttu-id="80493-208">Per SQL Server 2008 R2 e SQL Server 2012, usare le regole\_di\_confronto in latino generale 100 (accento sensibile).</span><span class="sxs-lookup"><span data-stu-id="80493-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="80493-209">Se si usano queste regole di confronto, tutti i nomi degli oggetti non saranno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="80493-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="80493-210">È possibile modificare le regole di confronto tramite Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="80493-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="80493-211">Per informazioni dettagliate sull'uso di questo strumento, vedere "utilizzo di SQL Server Management [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)studio" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="80493-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="80493-212">Seguire questa procedura per modificare le regole di confronto:</span><span class="sxs-lookup"><span data-stu-id="80493-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="80493-213">Verificare che SQL Server Management Studio sia configurato in modo da consentire la ricreazione delle modifiche che richiedono le tabelle.</span><span class="sxs-lookup"><span data-stu-id="80493-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="80493-214">Per informazioni dettagliate, vedere la finestra di dialogo "Salva (non consentita)" in [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span><span class="sxs-lookup"><span data-stu-id="80493-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="80493-215">Per informazioni dettagliate sull'impostazione di regole di confronto delle colonne, vedere "procedura: impostare le regole di confronto delle colonne (Visual [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)Database Tools)" at.</span><span class="sxs-lookup"><span data-stu-id="80493-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="80493-216">Con Microsoft SQL Server Management Studio connettersi al database di rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="80493-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="80493-217">Individuare la tabella che si vuole modificare nel database di rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e scegliere **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="80493-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="80493-218">Modificare le regole di confronto della colonna **nome** e salvare la tabella.</span><span class="sxs-lookup"><span data-stu-id="80493-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

