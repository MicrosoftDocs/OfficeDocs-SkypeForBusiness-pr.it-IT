---
title: Configurare Cloud Video Interop per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Questo articolo spiega come pianificare e configurare Cloud Video Interop per gli utenti dell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102602"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="e68f9-103">Configurare Cloud Video Interop per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e68f9-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="e68f9-104">Dopo aver scelto i partner cloud [Video Interop,](cloud-video-interop.md)è necessario pianificare la distribuzione, configurare i dettagli del provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="e68f9-105">Il diagramma seguente illustra il processo.</span><span class="sxs-lookup"><span data-stu-id="e68f9-105">The following diagram outlines the process.</span></span> 

![Distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="e68f9-107">Piano</span><span class="sxs-lookup"><span data-stu-id="e68f9-107">Plan</span></span>

<span data-ttu-id="e68f9-108">Vedere [Cloud Video Interop per Microsoft Teams](cloud-video-interop.md) informazioni sull'identificazione di un partner o di un partner da usare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="e68f9-109">Per pianificare l'abilitazione basata su utenti/simultanei/a livello di sito:</span><span class="sxs-lookup"><span data-stu-id="e68f9-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="e68f9-110">Scegliere un modello di distribuzione/modello ospitato per l'uso</span><span class="sxs-lookup"><span data-stu-id="e68f9-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="e68f9-111">Selezionare il piano di licenza ideale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="e68f9-112">Pianificare la capacità delle macchine virtuali è ospitare l'infrastruttura video.</span><span class="sxs-lookup"><span data-stu-id="e68f9-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="e68f9-113">Configurare</span><span class="sxs-lookup"><span data-stu-id="e68f9-113">Configure</span></span> 

<span data-ttu-id="e68f9-114">Per configurare Cloud Video Interop, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e68f9-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="e68f9-115">Ottenere informazioni di configurazione dal partner/partner scelto (chiave tenant, appIds...).</span><span class="sxs-lookup"><span data-stu-id="e68f9-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="e68f9-116">È possibile usare uno o più partner di interoperabilità video nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e68f9-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="e68f9-117">Verificare che la rete sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e68f9-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="e68f9-118">Configurare il firewall video basato su standard per il supporto dell'attraversamento della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e68f9-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="e68f9-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e68f9-119">For example:</span></span> 
    - <span data-ttu-id="e68f9-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="e68f9-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="e68f9-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="e68f9-121">Polycom RPAD</span></span>

3. <span data-ttu-id="e68f9-122">Configurare le chat room integrate con Exchange e OTD.</span><span class="sxs-lookup"><span data-stu-id="e68f9-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="e68f9-123">Nella maggior parte dei casi, l'inoltro aggiuntivo deve essere configurato e configurato nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e68f9-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="e68f9-124">Provisioning</span><span class="sxs-lookup"><span data-stu-id="e68f9-124">Provision</span></span>
 
<span data-ttu-id="e68f9-125">La chiave del tenant sarà la connessione remota al servizio partner.</span><span class="sxs-lookup"><span data-stu-id="e68f9-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="e68f9-126">Nell'esempio seguente, 813878896@t.plcm.vc è la chiave del tenant.</span><span class="sxs-lookup"><span data-stu-id="e68f9-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Esempio di chiave tenant](media/tenant-key-example.png) 

<span data-ttu-id="e68f9-128">Per eseguire il provisioning della chiave del tenant, è necessario eseguire i cmdlet seguenti e consentire anche a utenti selezionati o all'intera organizzazione di creare riunioni con coordinate di interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="e68f9-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="e68f9-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fornisce criteri predefiniti per ognuno dei partner supportati che consentono di designare i partner da usare per l'interoperabilità video nel cloud.</span><span class="sxs-lookup"><span data-stu-id="e68f9-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="e68f9-130">Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="e68f9-131">È possibile assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="e68f9-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="e68f9-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare criteri predefiniti da usare nell'organizzazione o di assegnarli a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="e68f9-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="e68f9-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Usare il New-CsVideoInteropServiceProvider per specificare le informazioni su un partner CVI supportato che l'organizzazione vuole usare.</span><span class="sxs-lookup"><span data-stu-id="e68f9-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="e68f9-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Usare il Set-CsVideoInteropServiceProvider per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="e68f9-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="e68f9-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.</span><span class="sxs-lookup"><span data-stu-id="e68f9-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="e68f9-137">Consenso</span><span class="sxs-lookup"><span data-stu-id="e68f9-137">Consent</span></span>

<span data-ttu-id="e68f9-138">Sarà necessario fornire il consenso per l'autorizzazione per i dispositivi di teleconferenza video (VTC) per partecipare alle riunioni delle organizzazioni tramite il servizio partner.</span><span class="sxs-lookup"><span data-stu-id="e68f9-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="e68f9-139">Questo collegamento di consenso verrà fornito anche dal partner.</span><span class="sxs-lookup"><span data-stu-id="e68f9-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="e68f9-140">Al termine di questi passaggi, gli utenti abilitati singolarmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno le coordinate VTC in tutte le riunioni Teams pianificate.</span><span class="sxs-lookup"><span data-stu-id="e68f9-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="e68f9-141">Qualsiasi VTC può partecipare a queste riunioni tramite queste coordinate.</span><span class="sxs-lookup"><span data-stu-id="e68f9-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="e68f9-142">Nome</span><span class="sxs-lookup"><span data-stu-id="e68f9-142">Name</span></span>|<span data-ttu-id="e68f9-143">Descrizione breve dell'autorizzazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="e68f9-143">Application Permission Short Description</span></span>| <span data-ttu-id="e68f9-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e68f9-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="e68f9-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="e68f9-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="e68f9-146">Partecipare a chiamate e riunioni di gruppo come app (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e68f9-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="e68f9-147">Consente all'app di partecipare alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="e68f9-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="e68f9-148">L'app verrà unita con i privilegi di un utente della directory alle riunioni nel tenant.</span><span class="sxs-lookup"><span data-stu-id="e68f9-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="e68f9-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="e68f9-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="e68f9-150">Partecipare a chiamate e riunioni di gruppo come utente guest (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e68f9-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="e68f9-151">Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="e68f9-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="e68f9-152">L'app verrà unita come guest alle riunioni nel tenant.</span><span class="sxs-lookup"><span data-stu-id="e68f9-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="e68f9-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="e68f9-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="e68f9-154">Accedere ai flussi multimediali in una chiamata come app (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e68f9-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="e68f9-155">Consente all'app di ottenere l'accesso diretto ai flussi multimediali in una chiamata, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="e68f9-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="e68f9-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="e68f9-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="e68f9-157">Leggere i dettagli della riunione online (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e68f9-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="e68f9-158">Consente all'app di leggere i dettagli della riunione online nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="e68f9-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="e68f9-159">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="e68f9-159">Schedule</span></span>

<span data-ttu-id="e68f9-160">Pianificare quindi una Teams riunione con coordinate di interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="e68f9-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="e68f9-161">L'utente abilitato può pianificare le riunioni dei team tramite:</span><span class="sxs-lookup"><span data-stu-id="e68f9-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="e68f9-162">Teams Componente aggiuntivo Riunione per Outlook</span><span class="sxs-lookup"><span data-stu-id="e68f9-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="e68f9-163">Teams client desktop e mobile</span><span class="sxs-lookup"><span data-stu-id="e68f9-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="e68f9-164">Partecipa</span><span class="sxs-lookup"><span data-stu-id="e68f9-164">Join</span></span>

<span data-ttu-id="e68f9-165">È possibile partecipare Teams riunioni con i dispositivi VTC nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e68f9-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="e68f9-166">IVR (Risposta vocale interattiva)</span><span class="sxs-lookup"><span data-stu-id="e68f9-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="e68f9-167">È possibile accedere all'IVR del partner usando il tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="e68f9-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="e68f9-168">Una volta che sei nell'IVR del partner, ti verrà chiesto di immettere l'ID conferenza VTC, che ti connetterà alla riunione Teams riunione.</span><span class="sxs-lookup"><span data-stu-id="e68f9-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="e68f9-169">Chiamata diretta</span><span class="sxs-lookup"><span data-stu-id="e68f9-169">Direct dial</span></span>
    - <span data-ttu-id="e68f9-170">È possibile accedere direttamente alla riunione Teams senza interagire con l'IVR del partner usando la funzione di chiamata diretta usando la stringa completa di tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="e68f9-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="e68f9-171">Chiamata con un solo tocco</span><span class="sxs-lookup"><span data-stu-id="e68f9-171">One-touch dial</span></span>
    - <span data-ttu-id="e68f9-172">Se si ha una sala Teams integrata, è possibile usare le funzionalità di composizione con un solo tocco offerte dal partner (senza bisogno di digitare alcuna stringa di chiamata).</span><span class="sxs-lookup"><span data-stu-id="e68f9-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="e68f9-173">Infine, è possibile coinvolgere Teams utenti nelle riunioni usando audio, video e condivisione di contenuti.</span><span class="sxs-lookup"><span data-stu-id="e68f9-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>