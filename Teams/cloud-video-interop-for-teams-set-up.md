---
title: Configurare l'interoperabilità cloud video per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: Questo articolo illustra come pianificare e configurare l'interoperabilità cloud video per gli utenti dell'organizzazione.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e91b0e25a7844634577083b26d74a48c788bc45b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237053"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="23511-103">Configurare l'interoperabilità cloud video per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23511-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="23511-104">Dopo aver scelto i partner di interoperabilità [cloud video](cloud-video-interop.md), è necessario pianificare la distribuzione, configurare i dettagli di provisioning e la chiave del tenant del partner e acconsentire all'app di interoperabilità video nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23511-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="23511-105">Il diagramma seguente illustra il processo.</span><span class="sxs-lookup"><span data-stu-id="23511-105">The following diagram outlines the process.</span></span> 

![Distribuzione di CVI nell'organizzazione](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="23511-107">Piano</span><span class="sxs-lookup"><span data-stu-id="23511-107">Plan</span></span>

<span data-ttu-id="23511-108">Per informazioni su come identificare un partner o partner da usare nell'organizzazione, vedere interoperabilità [cloud video per Microsoft teams](cloud-video-interop.md) .</span><span class="sxs-lookup"><span data-stu-id="23511-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="23511-109">Per pianificare l'abilitazione per l'utente in base/simultanea/wide site:</span><span class="sxs-lookup"><span data-stu-id="23511-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="23511-110">Selezionare un modello di distribuzione/modello ospitato per l'uso</span><span class="sxs-lookup"><span data-stu-id="23511-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="23511-111">Selezionare il piano di licenza ideale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23511-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="23511-112">Pianificare la capacità delle VM è l'hosting dell'infrastruttura video.</span><span class="sxs-lookup"><span data-stu-id="23511-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="23511-113">Configurare</span><span class="sxs-lookup"><span data-stu-id="23511-113">Configure</span></span> 

<span data-ttu-id="23511-114">Per configurare l'interoperabilità con cloud video, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="23511-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="23511-115">Ottenere le informazioni di configurazione dai partner/partner scelti (chiave del tenant, appId...).</span><span class="sxs-lookup"><span data-stu-id="23511-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="23511-116">È possibile usare uno o più partner di interoperabilità video nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="23511-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="23511-117">Verificare che la rete sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="23511-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="23511-118">Configurare il firewall video basato su standard per l'attraversamento della rete perimetrale per il supporto.</span><span class="sxs-lookup"><span data-stu-id="23511-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="23511-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="23511-119">For example:</span></span> 
    - <span data-ttu-id="23511-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="23511-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="23511-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="23511-121">Polycom RPAD</span></span>

3. <span data-ttu-id="23511-122">Configurare le camere integrate con Exchange e OTD.</span><span class="sxs-lookup"><span data-stu-id="23511-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="23511-123">Nella maggior parte dei casi, è necessario configurare e configurare l'inoltro aggiuntivo nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="23511-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="23511-124">Disposizione</span><span class="sxs-lookup"><span data-stu-id="23511-124">Provision</span></span>
 
<span data-ttu-id="23511-125">La chiave del tenant sarà la chiamata esterna al servizio partner.</span><span class="sxs-lookup"><span data-stu-id="23511-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="23511-126">Nell'esempio seguente, 813878896@t.plcm.vc è la chiave del tenant.</span><span class="sxs-lookup"><span data-stu-id="23511-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Esempio di chiave tenant](media/tenant-key-example.png) 

<span data-ttu-id="23511-128">Sarà necessario eseguire i cmdlet seguenti per provisionare la chiave del tenant e consentire anche agli utenti selezionati o all'intera organizzazione di creare riunioni con le coordinate di interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="23511-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="23511-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft fornisce criteri predefiniti per ogni partner supportato che consente di designare i partner da usare per l'interoperabilità video cloud.</span><span class="sxs-lookup"><span data-stu-id="23511-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="23511-130">Questo cmdlet consente di identificare i criteri predefiniti che è possibile usare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23511-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="23511-131">Puoi assegnare questo criterio a uno o più utenti sfruttando il cmdlet Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="23511-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="23511-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* Il cmdlet Grant-CsTeamsVideoInteropServicePolicy consente di assegnare un criterio precostruito per l'uso nell'organizzazione o di assegnare il criterio a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="23511-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="23511-133">\*\* [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Usa il nuovo-CsVideoInteropServiceProvider per specificare le informazioni su un partner CVI supportato che l'organizzazione vuole usare.</span><span class="sxs-lookup"><span data-stu-id="23511-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="23511-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Usa il set-CsVideoInteropServiceProvider per aggiornare le informazioni relative a un partner CVI supportato usato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23511-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="23511-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Ottenere tutti i provider configurati per l'utilizzo all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23511-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="23511-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Usare Remove-CsVideoInteropServiceProvider per rimuovere tutte le informazioni del provider relative a un provider che l'organizzazione non usa più.</span><span class="sxs-lookup"><span data-stu-id="23511-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="23511-137">Consenso</span><span class="sxs-lookup"><span data-stu-id="23511-137">Consent</span></span>

<span data-ttu-id="23511-138">È necessario fornire il consenso per i dispositivi di teleconferenza video (VTCs) per partecipare alle riunioni delle organizzazioni tramite il servizio partner.</span><span class="sxs-lookup"><span data-stu-id="23511-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="23511-139">Questo collegamento di consenso verrà fornito anche dal partner.</span><span class="sxs-lookup"><span data-stu-id="23511-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="23511-140">Al termine di questa procedura, gli utenti abilitati individualmente tramite il cmdlet Grant precedente o tutti gli utenti dell'organizzazione, se il tenant è abilitato, avranno Coordinate VTC in tutte le riunioni di team che pianificano.</span><span class="sxs-lookup"><span data-stu-id="23511-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="23511-141">Qualsiasi VTC può partecipare a queste riunioni tramite le coordinate.</span><span class="sxs-lookup"><span data-stu-id="23511-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="23511-142">Nome</span><span class="sxs-lookup"><span data-stu-id="23511-142">Name</span></span>|<span data-ttu-id="23511-143">Descrizione breve dell'autorizzazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="23511-143">Application Permission Short Description</span></span>| <span data-ttu-id="23511-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23511-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="23511-145">Chiamate. JoinGroupCall. All</span><span class="sxs-lookup"><span data-stu-id="23511-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="23511-146">Partecipare a chiamate di gruppo e riunioni come app (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23511-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="23511-147">Consente all'app di partecipare alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23511-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="23511-148">L'app verrà unita ai privilegi di un utente della directory per le riunioni nel tenant.</span><span class="sxs-lookup"><span data-stu-id="23511-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="23511-149">Chiamate. JoinGroupCallasGuest. All</span><span class="sxs-lookup"><span data-stu-id="23511-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="23511-150">Partecipare a chiamate di gruppo e riunioni come utente Guest (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23511-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="23511-151">Consente all'app di partecipare in forma anonima alle chiamate di gruppo e alle riunioni pianificate nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23511-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="23511-152">L'app verrà unita come guest alle riunioni nel tenant.</span><span class="sxs-lookup"><span data-stu-id="23511-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="23511-153">Chiamate. AccessMedia. All</span><span class="sxs-lookup"><span data-stu-id="23511-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="23511-154">Accedere ai flussi multimediali in una chiamata come app (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23511-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="23511-155">Consente all'app di accedere direttamente ai flussi multimediali in una chiamata, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23511-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="23511-156">OnlineMeetings. Read. All</span><span class="sxs-lookup"><span data-stu-id="23511-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="23511-157">Leggere i dettagli delle riunioni online (anteprima)</span><span class="sxs-lookup"><span data-stu-id="23511-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="23511-158">Consente all'app di leggere i dettagli delle riunioni online nell'organizzazione, senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="23511-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="23511-159">Pianificare</span><span class="sxs-lookup"><span data-stu-id="23511-159">Schedule</span></span>

<span data-ttu-id="23511-160">Pianificare quindi la riunione teams con le coordinate di interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="23511-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="23511-161">L'utente abilitato può pianificare le riunioni di teams tramite:</span><span class="sxs-lookup"><span data-stu-id="23511-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="23511-162">Componente aggiuntivo riunione teams per Outlook</span><span class="sxs-lookup"><span data-stu-id="23511-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="23511-163">Desktop e dispositivi mobili del client Teams</span><span class="sxs-lookup"><span data-stu-id="23511-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="23511-164">Partecipare a</span><span class="sxs-lookup"><span data-stu-id="23511-164">Join</span></span>

<span data-ttu-id="23511-165">Puoi partecipare alle riunioni di teams con i tuoi dispositivi VTC nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23511-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="23511-166">IVR (risposta vocale interattiva)</span><span class="sxs-lookup"><span data-stu-id="23511-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="23511-167">Puoi effettuare la chiamata al IVR del partner usando il tenantkey @ Domain.</span><span class="sxs-lookup"><span data-stu-id="23511-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="23511-168">Una volta entrati nell'IVR del partner, verrà richiesto di immettere il VTC conferenceId, che consentirà quindi di connettersi alla riunione teams.</span><span class="sxs-lookup"><span data-stu-id="23511-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="23511-169">Chiamata diretta</span><span class="sxs-lookup"><span data-stu-id="23511-169">Direct dial</span></span>
    - <span data-ttu-id="23511-170">Puoi effettuare direttamente la chiamata alla riunione teams senza interagire con il IVR del partner usando la funzionalità di chiamata diretta usando la stringa completa di tenantkey. VTC ConferenceId @ Domain.</span><span class="sxs-lookup"><span data-stu-id="23511-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="23511-171">Dial-One-Touch</span><span class="sxs-lookup"><span data-stu-id="23511-171">One-touch dial</span></span>
    - <span data-ttu-id="23511-172">Se si dispone di una sala teams integrata, è possibile usare le funzionalità di dial-up con un solo tocco offerte dal partner (senza dover digitare una stringa di chiamata).</span><span class="sxs-lookup"><span data-stu-id="23511-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="23511-173">Infine, Coinvolgi gli utenti di teams nelle tue riunioni usando audio, video e condivisione di contenuti.</span><span class="sxs-lookup"><span data-stu-id="23511-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 