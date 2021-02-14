---
title: Configurare l'interoperabilità dei video cloud per Microsoft Teams
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
description: Questo articolo spiega come pianificare e configurare Cloud Video Interoperabilità per gli utenti dell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582633"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="23abf-103">Configurare l'interoperabilità dei video cloud per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23abf-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="23abf-104">Dopo aver scelto i partner di interoperabilità di [Cloud Video,](cloud-video-interop.md)sarà necessario pianificare la distribuzione, configurare i dettagli di provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23abf-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="23abf-105">Il diagramma seguente illustra il processo.</span><span class="sxs-lookup"><span data-stu-id="23abf-105">The following diagram outlines the process.</span></span> 

![Distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="23abf-107">Piano</span><span class="sxs-lookup"><span data-stu-id="23abf-107">Plan</span></span>

<span data-ttu-id="23abf-108">Vedere [l'interoperabilità dei video cloud](cloud-video-interop.md) per Microsoft Teams per informazioni su come identificare un partner o partner da usare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23abf-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="23abf-109">Per pianificare l'abilitazione basata su utente/simultaneo/a livello di sito:</span><span class="sxs-lookup"><span data-stu-id="23abf-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="23abf-110">Scegliere un modello di distribuzione/modello ospitato per l'uso</span><span class="sxs-lookup"><span data-stu-id="23abf-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="23abf-111">Selezionare il piano di licenza ideale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23abf-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="23abf-112">Pianificare la capacità delle macchine virtuali è ospitare l'infrastruttura video.</span><span class="sxs-lookup"><span data-stu-id="23abf-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="23abf-113">Configura</span><span class="sxs-lookup"><span data-stu-id="23abf-113">Configure</span></span> 

<span data-ttu-id="23abf-114">Per configurare l'interoperabilità dei video nel cloud, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="23abf-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="23abf-115">Ottenere informazioni di configurazione dal partner/partner scelto (chiave tenant, id app...).</span><span class="sxs-lookup"><span data-stu-id="23abf-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="23abf-116">È possibile usare uno o più partner di interoperabilità video nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="23abf-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="23abf-117">Verificare che la rete sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="23abf-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="23abf-118">Configurare il firewall video basato su standard per il supporto della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="23abf-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="23abf-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23abf-119">For example:</span></span> 
    - <span data-ttu-id="23abf-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="23abf-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="23abf-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="23abf-121">Polycom RPAD</span></span>

3. <span data-ttu-id="23abf-122">Configurare sale integrate con Exchange e OTD.</span><span class="sxs-lookup"><span data-stu-id="23abf-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="23abf-123">Nella maggior parte dei casi, è necessario configurare e configurare l'inoltro aggiuntivo nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="23abf-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="23abf-124">Provisioning</span><span class="sxs-lookup"><span data-stu-id="23abf-124">Provision</span></span>
 
<span data-ttu-id="23abf-125">Il codice tenant sarà la chiamata esterna al servizio partner.</span><span class="sxs-lookup"><span data-stu-id="23abf-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="23abf-126">Nell'esempio seguente 813878896@t.plcm.vc chiave del tenant.</span><span class="sxs-lookup"><span data-stu-id="23abf-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Esempio di chiave tenant](media/tenant-key-example.png) 

<span data-ttu-id="23abf-128">Per effettuare il provisioning della chiave del tenant, è necessario eseguire i cmdlet seguenti e anche consentire a utenti selezionati o all'intera organizzazione di creare riunioni con coordinate di interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="23abf-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="23abf-129">**[Get-CsTeamsVideoInteropServicepolicy:](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)** Microsoft fornisce criteri predefiniti per ognuno dei nostri partner supportati, che consentono di designare i partner da usare per l'interoperabilità dei video nel cloud.</span><span class="sxs-lookup"><span data-stu-id="23abf-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="23abf-130">Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23abf-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="23abf-131">È possibile assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy locale.</span><span class="sxs-lookup"><span data-stu-id="23abf-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="23abf-132">**[Grant-CsTeamsVideoInteropServicePolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare criteri predefiniti da usare nell'organizzazione o di assegnarli a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="23abf-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="23abf-133">**[New-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)** Usare le New-CsVideoInteropServiceProvider per specificare informazioni su un partner CVI supportato che l'organizzazione vuole usare.</span><span class="sxs-lookup"><span data-stu-id="23abf-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="23abf-134">**[Set-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)** Usare le Set-CsVideoInteropServiceProvider per aggiornare le informazioni su un partner CVI supportato utilizzato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23abf-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="23abf-135">**[Get-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)** Ottenere tutti i provider configurati per l'uso all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23abf-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="23abf-136">**[Remove-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)** Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni sul provider relative a un provider che l'organizzazione non usa più.</span><span class="sxs-lookup"><span data-stu-id="23abf-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="23abf-137">Consenso</span><span class="sxs-lookup"><span data-stu-id="23abf-137">Consent</span></span>

<span data-ttu-id="23abf-138">Devi fornire il consenso per i dispositivi di teleconferenza video (VCS) per partecipare alle riunioni della tua organizzazione tramite il servizio partner.</span><span class="sxs-lookup"><span data-stu-id="23abf-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="23abf-139">Questo collegamento per il consenso verrà fornito anche dal tuo partner.</span><span class="sxs-lookup"><span data-stu-id="23abf-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="23abf-140">Una volta completata questa procedura, gli utenti abilitati singolarmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno le coordinate VTC in tutte le riunioni di Teams che pianificano.</span><span class="sxs-lookup"><span data-stu-id="23abf-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="23abf-141">Qualsiasi VTC può partecipare a queste riunioni tramite queste coordinate.</span><span class="sxs-lookup"><span data-stu-id="23abf-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="23abf-142">Nome</span><span class="sxs-lookup"><span data-stu-id="23abf-142">Name</span></span>|<span data-ttu-id="23abf-143">Descrizione breve delle autorizzazioni per le applicazioni</span><span class="sxs-lookup"><span data-stu-id="23abf-143">Application Permission Short Description</span></span>| <span data-ttu-id="23abf-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23abf-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="23abf-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="23abf-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="23abf-146">Partecipare a chiamate e riunioni di gruppo come app (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23abf-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="23abf-147">Consente all'app di partecipare alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23abf-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="23abf-148">L'app verrà unita alle riunioni del tenant con i privilegi di un utente della directory.</span><span class="sxs-lookup"><span data-stu-id="23abf-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="23abf-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="23abf-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="23abf-150">Partecipare a chiamate e riunioni di gruppo come utente guest (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23abf-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="23abf-151">Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23abf-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="23abf-152">L'app verrà unita come guest alle riunioni nel tenant.</span><span class="sxs-lookup"><span data-stu-id="23abf-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="23abf-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="23abf-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="23abf-154">Accedere ai flussi multimediali in una chiamata come app (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23abf-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="23abf-155">Consente all'app di ottenere l'accesso diretto ai flussi multimediali in una chiamata, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23abf-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="23abf-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="23abf-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="23abf-157">Leggere i dettagli della riunione online (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23abf-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="23abf-158">Consente all'app di leggere i dettagli della riunione online nell'organizzazione, senza che sia stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="23abf-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="23abf-159">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="23abf-159">Schedule</span></span>

<span data-ttu-id="23abf-160">Pianificare quindi la riunione di Teams con le coordinate di interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="23abf-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="23abf-161">L'utente abilitato può pianificare le riunioni dei team tramite:</span><span class="sxs-lookup"><span data-stu-id="23abf-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="23abf-162">Componente aggiuntivo Riunione di Teams per Outlook</span><span class="sxs-lookup"><span data-stu-id="23abf-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="23abf-163">Client Teams per desktop e dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="23abf-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="23abf-164">Partecipa</span><span class="sxs-lookup"><span data-stu-id="23abf-164">Join</span></span>

<span data-ttu-id="23abf-165">È possibile partecipare alle riunioni di Teams con i dispositivi VTC nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23abf-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="23abf-166">IVR (Risposta vocale interattiva)</span><span class="sxs-lookup"><span data-stu-id="23abf-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="23abf-167">È possibile chiamare l'IVR del partner usando il tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="23abf-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="23abf-168">Nel partner IVR verrà richiesto di immettere il valore VTC conferenceId, che consente di connettersi alla riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="23abf-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="23abf-169">Chiamata diretta</span><span class="sxs-lookup"><span data-stu-id="23abf-169">Direct dial</span></span>
    - <span data-ttu-id="23abf-170">Puoi accedere direttamente alla riunione di Teams senza interagire con l'IVR del partner utilizzando la funzione di chiamata diretta utilizzando la stringa completa di tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="23abf-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="23abf-171">Chiamata con un solo tocco</span><span class="sxs-lookup"><span data-stu-id="23abf-171">One-touch dial</span></span>
    - <span data-ttu-id="23abf-172">Se si dispone di una sala di Teams integrata, è possibile usare le funzionalità di chiamata con un solo tocco offerte dal partner (senza dover digitare alcuna stringa di composizione).</span><span class="sxs-lookup"><span data-stu-id="23abf-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="23abf-173">Infine, interagire con gli utenti di Teams nelle riunioni con audio, video e condivisione di contenuti.</span><span class="sxs-lookup"><span data-stu-id="23abf-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
