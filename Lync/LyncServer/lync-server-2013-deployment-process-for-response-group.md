---
title: 'Lync Server 2013: processo di distribuzione per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="3491d-102">Processo di distribuzione per il gruppo di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3491d-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3491d-103">_**Argomento Ultima modifica:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="3491d-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="3491d-104">Questa sezione offre una panoramica delle fasi e dei passaggi necessari per la distribuzione dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="3491d-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="3491d-105">Processo di distribuzione di Response Group</span><span class="sxs-lookup"><span data-stu-id="3491d-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3491d-106">Fase</span><span class="sxs-lookup"><span data-stu-id="3491d-106">Phase</span></span></th>
<th><span data-ttu-id="3491d-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="3491d-107">Steps</span></span></th>
<th><span data-ttu-id="3491d-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3491d-108">Permissions</span></span></th>
<th><span data-ttu-id="3491d-109">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="3491d-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3491d-110">Installare l'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="3491d-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="3491d-111">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3491d-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="3491d-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3491d-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3491d-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3491d-114">Installare componenti per il gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="3491d-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="3491d-115">I cmdlet di Lync Server, il pannello di controllo di Lync Server, lo strumento di configurazione dei gruppi di risposta, la console di accesso e di disconnessione degli agenti e il servizio Web client di Response Group vengono installati come parte dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="3491d-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="3491d-116">I servizi Web vengono installati quando si distribuisce un pool di Enterprise Edition o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3491d-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="3491d-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3491d-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3491d-118"><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3491d-119">Abilitare gli utenti per Lync 2013 e per Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3491d-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="3491d-120">Abilitare gli utenti che saranno agenti per Lync Server e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3491d-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="3491d-121">Gli utenti devono essere abilitati prima di poterli aggiungere ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="3491d-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="3491d-122">In genere gli utenti sono abilitati per Lync Server durante la distribuzione di Enterprise Edition o Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="3491d-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="3491d-123">Gli utenti sono abilitati per VoIP aziendale durante la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3491d-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="3491d-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3491d-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="3491d-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="3491d-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3491d-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disabilitare o riattivare l'account utente per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3491d-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Consentire agli utenti di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3491d-129">Creare e configurare Response Groups, costituiti da gruppi di agenti, code e flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="3491d-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3491d-130">Usare il pannello di controllo di Lync Server o Lync Server Management Shell per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3491d-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3491d-131">Creare e configurare gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="3491d-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="3491d-132">Creare e configurare le code.</span><span class="sxs-lookup"><span data-stu-id="3491d-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="3491d-133">Facoltativamente, è possibile usare Lync Server Management Shell per creare orari e festività di un gruppo di risposte predefinito.</span><span class="sxs-lookup"><span data-stu-id="3491d-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="3491d-134">Usare lo strumento di configurazione del gruppo di risposte o Lync Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), inclusi gli orari di lavoro e le festività di Response Group personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3491d-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3491d-135">È possibile accedere allo strumento di configurazione del Response Group tramite il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3491d-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="3491d-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3491d-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3491d-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="3491d-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3491d-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3491d-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="3491d-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="3491d-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="3491d-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Creare gruppi di agenti per Response Group in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3491d-143"><a href="lync-server-2013-create-response-group-queues.md">Creare code di Response Group in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3491d-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3491d-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opzionale Definire set di festività di Response Group in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3491d-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Creare o modificare un flusso di lavoro in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3491d-147">Opzionale Personalizzare le impostazioni a livello di applicazione</span><span class="sxs-lookup"><span data-stu-id="3491d-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="3491d-148">Usare Lync Server Management Shell per personalizzare la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in attesa, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3491d-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="3491d-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3491d-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3491d-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="3491d-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3491d-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3491d-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3491d-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3491d-155">Opzionale Gestione dei delegati di Response Groups</span><span class="sxs-lookup"><span data-stu-id="3491d-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="3491d-156">Assegna agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="3491d-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="3491d-157">I responsabili del gruppo di risposte possono quindi configurare i gruppi di risposte assegnati.</span><span class="sxs-lookup"><span data-stu-id="3491d-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="3491d-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3491d-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3491d-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="3491d-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3491d-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3491d-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3491d-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3491d-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3491d-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3491d-164">Verificare la distribuzione di Response Group</span><span class="sxs-lookup"><span data-stu-id="3491d-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="3491d-165">Provare a rispondere alle chiamate al gruppo di ricerca e ai flussi di lavoro di risposta vocale interattivi per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="3491d-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

