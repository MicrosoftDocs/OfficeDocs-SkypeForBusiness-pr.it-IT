---
title: 'Lync Server 2013: processo di distribuzione per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="06365-102">Processo di distribuzione per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06365-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06365-103">_**Ultimo argomento modificato:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="06365-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="06365-104">In questa sezione viene fornita una panoramica delle fasi e dei passaggi necessari per la distribuzione dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="06365-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="06365-105">Processo di distribuzione di Response Group</span><span class="sxs-lookup"><span data-stu-id="06365-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06365-106">Fase</span><span class="sxs-lookup"><span data-stu-id="06365-106">Phase</span></span></th>
<th><span data-ttu-id="06365-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="06365-107">Steps</span></span></th>
<th><span data-ttu-id="06365-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="06365-108">Permissions</span></span></th>
<th><span data-ttu-id="06365-109">Documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="06365-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06365-110">Installare l'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="06365-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="06365-111">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="06365-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="06365-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="06365-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="06365-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06365-114">Installare i componenti per Response Group</span><span class="sxs-lookup"><span data-stu-id="06365-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="06365-115">I cmdlet di Lync Server, il pannello di controllo di Lync Server, lo strumento di configurazione di Response Group, la console di accesso e disconnessione degli agenti e il servizio Web client Response Group vengono installati come parte dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="06365-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="06365-116">I servizi Web vengono installati quando si distribuisce un pool Enterprise Edition o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="06365-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="06365-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="06365-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="06365-118"><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06365-119">Abilitare gli utenti per Lync 2013 e per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="06365-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="06365-120">Abilitare gli utenti che saranno agenti per Lync Server e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="06365-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="06365-121">Gli utenti devono essere abilitati per poter essere aggiunti a gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="06365-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="06365-122">In genere, gli utenti sono abilitati per Lync Server durante la distribuzione di Enterprise Edition o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="06365-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="06365-123">Gli utenti sono abilitati per VoIP aziendale durante la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="06365-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="06365-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06365-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="06365-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="06365-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="06365-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disabilitare o riabilitare l'account utente per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="06365-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Abilitare gli utenti per VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06365-129">Creazione e configurazione di Response Group, costituiti da gruppi di agenti, code e flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="06365-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="06365-130">Utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="06365-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="06365-131">Creare e configurare gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="06365-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="06365-132">Creare e configurare code.</span><span class="sxs-lookup"><span data-stu-id="06365-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="06365-133">Facoltativamente, utilizzare Lync Server Management Shell per creare l'orario di ufficio e le festività di Response Group predefiniti.</span><span class="sxs-lookup"><span data-stu-id="06365-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="06365-134">Utilizzare lo strumento di configurazione di Response Group o Lync Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), compresi gli orari di ufficio e le festività di Response Group personalizzati.</span><span class="sxs-lookup"><span data-stu-id="06365-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="06365-135">È possibile accedere allo strumento di configurazione di Response Group tramite il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06365-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="06365-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="06365-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="06365-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="06365-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="06365-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="06365-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="06365-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="06365-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="06365-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Creare gruppi di agenti di Response Group Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="06365-143"><a href="lync-server-2013-create-response-group-queues.md">Creare code di Response Group in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="06365-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional Definire l'orario di ufficio di Response Group in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="06365-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional Definire i set di festività di Response Group in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="06365-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Creare o modificare un flusso di lavoro in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06365-147">(Facoltativo) Personalizzazione delle impostazioni a livello di applicazione</span><span class="sxs-lookup"><span data-stu-id="06365-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="06365-148">Utilizzo di Lync Server Management Shell per personalizzare la configurazione predefinita per la musica di attesa, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="06365-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="06365-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="06365-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="06365-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="06365-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="06365-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="06365-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="06365-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestione delle impostazioni dei Response Group a livello di applicazione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06365-155">(Facoltativo) Delega della gestione dei Response Group</span><span class="sxs-lookup"><span data-stu-id="06365-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="06365-156">Assegnare agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="06365-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="06365-157">I responsabili dei Response Group possono quindi configurare i Response Group a loro assegnati.</span><span class="sxs-lookup"><span data-stu-id="06365-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="06365-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="06365-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="06365-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="06365-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="06365-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="06365-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="06365-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="06365-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="06365-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06365-164">Verificare la distribuzione di Response Group</span><span class="sxs-lookup"><span data-stu-id="06365-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="06365-165">Testare la risposta alle chiamate nei flussi di lavoro del gruppo di risposta e del sistema IVR per assicurare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="06365-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

