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
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Informazioni su come usare Call Park e retrieve per effettuare una chiamata in attesa nel servizio Teams nel cloud.
ms.openlocfilehash: a9518705cd5edff3834be21732f78dd47352cd63
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938535"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="0c377-103">Chiamare il parcheggio e il recupero in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c377-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="0c377-104">Call Park and retrieve è una funzionalità che consente a un utente di inserire una chiamata in attesa nel servizio Teams nel cloud.</span><span class="sxs-lookup"><span data-stu-id="0c377-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="0c377-105">Quando una chiamata viene parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0c377-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="0c377-106">L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice e un'app o un dispositivo supportato per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c377-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="0c377-107">Alcuni degli scenari comuni per l'uso di Call Park sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c377-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="0c377-108">Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="0c377-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="0c377-109">L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici.</span><span class="sxs-lookup"><span data-stu-id="0c377-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="0c377-110">L'utente a cui è consentita la chiamata può quindi prendere un telefono per le squadre in fabbrica e immettere il codice per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c377-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="0c377-111">Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo la potenza.</span><span class="sxs-lookup"><span data-stu-id="0c377-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="0c377-112">L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo teams.</span><span class="sxs-lookup"><span data-stu-id="0c377-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="0c377-113">Un supporto rappresentativo parcheggia una chiamata del cliente e invia un annuncio su un canale di teams per un esperto per recuperare la chiamata e aiutare il cliente.</span><span class="sxs-lookup"><span data-stu-id="0c377-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="0c377-114">Un esperto immette il codice nei client di teams per recuperare la chiamata</span><span class="sxs-lookup"><span data-stu-id="0c377-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c377-115">Questa caratteristica è disponibile solo in modalità di distribuzione solo teams.</span><span class="sxs-lookup"><span data-stu-id="0c377-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="0c377-116">Per altre informazioni sulle modalità di distribuzione dei team, vedere [comprendere la coesistenza e l'interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="0c377-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="0c377-117">Licenza richiesta</span><span class="sxs-lookup"><span data-stu-id="0c377-117">License required</span></span>

<span data-ttu-id="0c377-118">Per parcheggiare e recuperare le chiamate, un utente deve essere un utente di VoIP aziendale e un amministratore deve concedere all'utente un criterio per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0c377-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="0c377-119">Per altre informazioni sul modello di licenza, vedere [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="0c377-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="0c377-120">Chiamare il parcheggio e recuperare la disponibilità delle caratteristiche</span><span class="sxs-lookup"><span data-stu-id="0c377-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="0c377-121">Call Park and retrieve è attualmente supportato dai seguenti client e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0c377-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="0c377-122">(Supportata solo in modalità teams, con o senza connettività PSTN)</span><span class="sxs-lookup"><span data-stu-id="0c377-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="0c377-123">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="0c377-123">Capability</span></span> | <span data-ttu-id="0c377-124">Desktop Teams</span><span class="sxs-lookup"><span data-stu-id="0c377-124">Teams Desktop</span></span> | <span data-ttu-id="0c377-125">App teams Mac</span><span class="sxs-lookup"><span data-stu-id="0c377-125">Teams Mac App</span></span> | <span data-ttu-id="0c377-126">App Web Teams (Edge)</span><span class="sxs-lookup"><span data-stu-id="0c377-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="0c377-127">App teams per dispositivi mobili iOS/Android</span><span class="sxs-lookup"><span data-stu-id="0c377-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="0c377-128">Telefono IP Teams</span><span class="sxs-lookup"><span data-stu-id="0c377-128">Teams IP phone</span></span> | <span data-ttu-id="0c377-129">Telefono IP Skype for business</span><span class="sxs-lookup"><span data-stu-id="0c377-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="0c377-130">Parcheggiare una chiamata</span><span class="sxs-lookup"><span data-stu-id="0c377-130">Park a call</span></span> | <span data-ttu-id="0c377-131">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-131">Yes</span></span> | <span data-ttu-id="0c377-132">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-132">Yes</span></span> | <span data-ttu-id="0c377-133">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-133">Yes</span></span> | <span data-ttu-id="0c377-134">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-134">Yes</span></span> | <span data-ttu-id="0c377-135">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-135">Yes</span></span> | <span data-ttu-id="0c377-136">No</span><span class="sxs-lookup"><span data-stu-id="0c377-136">No</span></span> |
| <span data-ttu-id="0c377-137">Recuperare una chiamata parcheggiata</span><span class="sxs-lookup"><span data-stu-id="0c377-137">Retrieve a parked call</span></span> | <span data-ttu-id="0c377-138">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-138">Yes</span></span> | <span data-ttu-id="0c377-139">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-139">Yes</span></span> | <span data-ttu-id="0c377-140">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-140">Yes</span></span> | <span data-ttu-id="0c377-141">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-141">Yes</span></span> | <span data-ttu-id="0c377-142">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-142">Yes</span></span> | <span data-ttu-id="0c377-143">No</span><span class="sxs-lookup"><span data-stu-id="0c377-143">No</span></span> |
| <span data-ttu-id="0c377-144">Chiamata non recuperata Ring back</span><span class="sxs-lookup"><span data-stu-id="0c377-144">Unretrieved call ring back</span></span> | <span data-ttu-id="0c377-145">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-145">Yes</span></span> | <span data-ttu-id="0c377-146">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-146">Yes</span></span> | <span data-ttu-id="0c377-147">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-147">Yes</span></span> | <span data-ttu-id="0c377-148">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-148">Yes</span></span> | <span data-ttu-id="0c377-149">Sì</span><span class="sxs-lookup"><span data-stu-id="0c377-149">Yes</span></span> | <span data-ttu-id="0c377-150">No</span><span class="sxs-lookup"><span data-stu-id="0c377-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="0c377-151">Configurare il parcheggio delle chiamate e il recupero</span><span class="sxs-lookup"><span data-stu-id="0c377-151">Configure call park and retrieve</span></span>

<span data-ttu-id="0c377-152">È necessario essere un amministratore per configurare il parcheggio delle chiamate e il recupero e la caratteristica è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0c377-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="0c377-153">Puoi abilitarlo per gli utenti e creare gruppi di utenti usando i criteri per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0c377-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="0c377-154">Quando si applica lo stesso criterio a un set di utenti, è possibile parcheggiare e recuperare le chiamate tra di loro.</span><span class="sxs-lookup"><span data-stu-id="0c377-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="0c377-155">Per configurare Call Park per gli utenti e creare gruppi di utenti di Call Park, seguire la procedura di [assegnazione di un parcheggio](#assign-a-call-park-policy) di chiamata seguente.</span><span class="sxs-lookup"><span data-stu-id="0c377-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="0c377-156">Per informazioni su come usare la funzionalità chiama parcheggio e recupera, vedere [parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0c377-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="0c377-157">Abilitare un criterio per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0c377-157">Enable a call park policy</span></span>

1. <span data-ttu-id="0c377-158">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**accedere ai criteri per il parcheggio per le  >  **chiamate**vocali.</span><span class="sxs-lookup"><span data-stu-id="0c377-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="0c377-159">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c377-159">Select **Add**.</span></span>
3. <span data-ttu-id="0c377-160">Assegnare un nome al criterio e quindi passare **Consenti al parcheggio** di chiamata **.**</span><span class="sxs-lookup"><span data-stu-id="0c377-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="0c377-161">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c377-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="0c377-162">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c377-162">Using PowerShell</span></span>

<span data-ttu-id="0c377-163">Vedere [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0c377-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="0c377-164">Modificare un criterio per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0c377-164">Edit a call park policy</span></span>

1. <span data-ttu-id="0c377-165">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**accedere ai criteri per il parcheggio per le  >  **chiamate**vocali.</span><span class="sxs-lookup"><span data-stu-id="0c377-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="0c377-166">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="0c377-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0c377-167">Opzione **Consenti parcheggio chiamate** su **disattivato** o **su**.</span><span class="sxs-lookup"><span data-stu-id="0c377-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="0c377-168">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c377-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="0c377-169">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c377-169">Using PowerShell</span></span>

<span data-ttu-id="0c377-170">Vedere [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0c377-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="0c377-171">Ad esempio, per modificare l'impostazione predefinita, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c377-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="0c377-172">Assegnare un criterio per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0c377-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="0c377-173">Vedere anche [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0c377-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0c377-174">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0c377-174">Troubleshooting</span></span>

<span data-ttu-id="0c377-175">Se gli utenti non riescono a visualizzare il pulsante parcheggia o Recupera:</span><span class="sxs-lookup"><span data-stu-id="0c377-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="0c377-176">Verificare che l'utente disponga dei criteri di parcheggio delle chiamate abilitati.</span><span class="sxs-lookup"><span data-stu-id="0c377-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="0c377-177">Se un utente tenta di recuperare una chiamata e non riesce, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0c377-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="0c377-178">Verificare che l'utente stia usando il client teams o un dispositivo/telefono abilitato per Teams</span><span class="sxs-lookup"><span data-stu-id="0c377-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="0c377-179">Raggruppamento: l'utente è un membro del gruppo Call Park, che si basa sull'assegnazione di criteri di parcheggio per le chiamate a teams.</span><span class="sxs-lookup"><span data-stu-id="0c377-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="0c377-180">Modalità Isola-Call Park and retrieve non è disponibile nella modalità Isola di teams.</span><span class="sxs-lookup"><span data-stu-id="0c377-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="0c377-181">La chiamata è già stata recuperata o terminata.</span><span class="sxs-lookup"><span data-stu-id="0c377-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c377-182">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0c377-182">Related topics</span></span>

[<span data-ttu-id="0c377-183">Parcheggiare una chiamata in teams</span><span class="sxs-lookup"><span data-stu-id="0c377-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="0c377-184">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="0c377-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
