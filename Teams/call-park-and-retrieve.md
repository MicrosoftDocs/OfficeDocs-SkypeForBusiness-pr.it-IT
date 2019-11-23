---
title: Chiamare il parcheggio e il recupero in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: USA Call Park e recupera per effettuare una chiamata in attesa nel servizio Teams nel cloud.
ms.openlocfilehash: 9a6f5b6a51a0193625ecd2dab294c2cf454cb21f
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209182"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="993d8-103">Chiamare il parcheggio e il recupero in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="993d8-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="993d8-104">Call Park and retrieve è una funzionalità che consente a un utente di inserire una chiamata in attesa nel servizio Teams nel cloud.</span><span class="sxs-lookup"><span data-stu-id="993d8-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="993d8-105">Quando una chiamata viene parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="993d8-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="993d8-106">L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice e un'app o un dispositivo supportato per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="993d8-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="993d8-107">Alcuni degli scenari comuni per l'uso di Call Park sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="993d8-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="993d8-108">Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="993d8-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="993d8-109">L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici.</span><span class="sxs-lookup"><span data-stu-id="993d8-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="993d8-110">L'utente a cui è consentita la chiamata può quindi prendere un telefono per le squadre in fabbrica e immettere il codice per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="993d8-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="993d8-111">Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo la potenza.</span><span class="sxs-lookup"><span data-stu-id="993d8-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="993d8-112">L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo teams.</span><span class="sxs-lookup"><span data-stu-id="993d8-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="993d8-113">Un supporto rappresentativo parcheggia una chiamata del cliente e invia un annuncio su un canale di teams per un esperto per recuperare la chiamata e aiutare il cliente.</span><span class="sxs-lookup"><span data-stu-id="993d8-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="993d8-114">Un esperto immette il codice nei client di teams per recuperare la chiamata</span><span class="sxs-lookup"><span data-stu-id="993d8-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="993d8-115">Questa caratteristica è disponibile solo in modalità di distribuzione solo teams.</span><span class="sxs-lookup"><span data-stu-id="993d8-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="993d8-116">Per altre informazioni sulle modalità di distribuzione dei team, vedere [comprendere la coesistenza e l'interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="993d8-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="993d8-117">Licenza richiesta</span><span class="sxs-lookup"><span data-stu-id="993d8-117">License required</span></span>

<span data-ttu-id="993d8-118">Per parcheggiare e recuperare le chiamate, un utente deve essere un utente di VoIP aziendale e un amministratore deve concedere all'utente un criterio per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="993d8-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="993d8-119">Per altre informazioni sul modello di licenza, vedere [licenze di Office 365 per Microsoft teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="993d8-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="993d8-120">Chiamare il parcheggio e recuperare la disponibilità delle caratteristiche</span><span class="sxs-lookup"><span data-stu-id="993d8-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="993d8-121">Call Park and retrieve è attualmente supportato dai seguenti client e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="993d8-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="993d8-122">(Supportata solo in modalità teams, con o senza connettività PSTN)</span><span class="sxs-lookup"><span data-stu-id="993d8-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="993d8-123">Capacità</span><span class="sxs-lookup"><span data-stu-id="993d8-123">Capability</span></span> | <span data-ttu-id="993d8-124">Desktop Teams</span><span class="sxs-lookup"><span data-stu-id="993d8-124">Teams Desktop</span></span> | <span data-ttu-id="993d8-125">App teams Mac</span><span class="sxs-lookup"><span data-stu-id="993d8-125">Teams Mac App</span></span> | <span data-ttu-id="993d8-126">App Web Teams (Edge)</span><span class="sxs-lookup"><span data-stu-id="993d8-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="993d8-127">App teams per dispositivi mobili iOS/Android</span><span class="sxs-lookup"><span data-stu-id="993d8-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="993d8-128">Telefono IP Teams</span><span class="sxs-lookup"><span data-stu-id="993d8-128">Teams IP phone</span></span> | <span data-ttu-id="993d8-129">Telefono IP Skype for business</span><span class="sxs-lookup"><span data-stu-id="993d8-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="993d8-130">Parcheggiare una chiamata</span><span class="sxs-lookup"><span data-stu-id="993d8-130">Park a call</span></span> | <span data-ttu-id="993d8-131">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-131">Yes</span></span> | <span data-ttu-id="993d8-132">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-132">Yes</span></span> | <span data-ttu-id="993d8-133">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-133">Yes</span></span> | <span data-ttu-id="993d8-134">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-134">Yes</span></span> | <span data-ttu-id="993d8-135">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="993d8-135">Coming soon</span></span>| <span data-ttu-id="993d8-136">No</span><span class="sxs-lookup"><span data-stu-id="993d8-136">No</span></span> |
| <span data-ttu-id="993d8-137">Recuperare una chiamata parcheggiata</span><span class="sxs-lookup"><span data-stu-id="993d8-137">Retrieve a parked call</span></span> | <span data-ttu-id="993d8-138">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-138">Yes</span></span> | <span data-ttu-id="993d8-139">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-139">Yes</span></span> | <span data-ttu-id="993d8-140">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-140">Yes</span></span> | <span data-ttu-id="993d8-141">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-141">Yes</span></span> | <span data-ttu-id="993d8-142">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="993d8-142">Coming soon</span></span>| <span data-ttu-id="993d8-143">No</span><span class="sxs-lookup"><span data-stu-id="993d8-143">No</span></span> |
| <span data-ttu-id="993d8-144">Chiamata non recuperata Ring back</span><span class="sxs-lookup"><span data-stu-id="993d8-144">Unretrieved call ring back</span></span> | <span data-ttu-id="993d8-145">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-145">Yes</span></span> | <span data-ttu-id="993d8-146">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-146">Yes</span></span> | <span data-ttu-id="993d8-147">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-147">Yes</span></span> | <span data-ttu-id="993d8-148">Sì</span><span class="sxs-lookup"><span data-stu-id="993d8-148">Yes</span></span> | <span data-ttu-id="993d8-149">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="993d8-149">Coming soon</span></span>| <span data-ttu-id="993d8-150">No</span><span class="sxs-lookup"><span data-stu-id="993d8-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="993d8-151">Configurazione di Call Park e recupero</span><span class="sxs-lookup"><span data-stu-id="993d8-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="993d8-152">È necessario essere un amministratore per configurare il parcheggio delle chiamate e il recupero e la caratteristica è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="993d8-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="993d8-153">Puoi abilitarlo per gli utenti e creare gruppi di utenti usando i criteri per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="993d8-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="993d8-154">Quando si applica lo stesso criterio a un set di utenti, è possibile parcheggiare e recuperare le chiamate tra di loro.</span><span class="sxs-lookup"><span data-stu-id="993d8-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="993d8-155">Per configurare Call Park per gli utenti e creare gruppi di utenti di Call Park, seguire la procedura di [assegnazione di un parcheggio](#assign-a-call-park-policy) di chiamata seguente.</span><span class="sxs-lookup"><span data-stu-id="993d8-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="993d8-156">Per informazioni su come usare la funzionalità chiama parcheggio e recupera, vedere [parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="993d8-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="993d8-157">Abilitare un criterio per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="993d8-157">Enable a call park policy</span></span>

<span data-ttu-id="993d8-158">Seguire questa procedura per abilitare un criterio per il parcheggio delle chiamate:</span><span class="sxs-lookup"><span data-stu-id="993d8-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="993d8-159">Accedere ai criteri per il\*\*\*\* > **parcheggio**dell'interfaccia di amministrazione > di **Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="993d8-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="993d8-160">Selezionare **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="993d8-160">Select **New policy**.</span></span>
3. <span data-ttu-id="993d8-161">Assegnare un nome al criterio e quindi passare **Consenti al parcheggio** di chiamata **.**</span><span class="sxs-lookup"><span data-stu-id="993d8-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="993d8-162">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="993d8-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="993d8-163">Assegnare un criterio per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="993d8-163">Assign a call park policy</span></span>

<span data-ttu-id="993d8-164">Seguire questa procedura per assegnare un criterio di parcheggio di chiamata a uno o più utenti:</span><span class="sxs-lookup"><span data-stu-id="993d8-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="993d8-165">Accedere ai criteri per il\*\*\*\* > **parcheggio**dell'interfaccia di amministrazione > di **Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="993d8-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="993d8-166">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="993d8-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="993d8-167">Selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="993d8-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="993d8-168">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="993d8-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="993d8-169">Ripetere questo passaggio per ogni utente che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="993d8-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="993d8-170">Al termine dell'aggiunta di utenti, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="993d8-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="993d8-171">Configurare il parcheggio delle chiamate e il recupero con PowerShell</span><span class="sxs-lookup"><span data-stu-id="993d8-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="993d8-172">Usa il cmdlet di PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) per creare un criterio per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="993d8-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="993d8-173">Usare il cmdlet di PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) per concedere un criterio per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="993d8-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="993d8-174">È possibile modificare l'impostazione predefinita usando [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="993d8-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="993d8-175">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="993d8-175">Troubleshooting</span></span>

<span data-ttu-id="993d8-176">Se gli utenti non riescono a visualizzare il pulsante parcheggia o Recupera:</span><span class="sxs-lookup"><span data-stu-id="993d8-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="993d8-177">Verificare che l'utente disponga dei criteri di parcheggio delle chiamate abilitati.</span><span class="sxs-lookup"><span data-stu-id="993d8-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="993d8-178">Se un utente tenta di recuperare una chiamata e non riesce, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="993d8-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="993d8-179">Verificare che l'utente stia usando il client teams o un dispositivo/telefono abilitato per Teams</span><span class="sxs-lookup"><span data-stu-id="993d8-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="993d8-180">Raggruppamento: l'utente è un membro del gruppo Call Park, che si basa sull'assegnazione di criteri di parcheggio per le chiamate a teams.</span><span class="sxs-lookup"><span data-stu-id="993d8-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="993d8-181">Modalità Isola-Call Park and retrieve non è disponibile nella modalità Isola di teams.</span><span class="sxs-lookup"><span data-stu-id="993d8-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="993d8-182">La chiamata è già stata recuperata o terminata.</span><span class="sxs-lookup"><span data-stu-id="993d8-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="993d8-183">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="993d8-183">More information</span></span>

<span data-ttu-id="993d8-184">[Parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="993d8-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
