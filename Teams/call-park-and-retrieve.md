---
title: Parcheggio di chiamata e recupero in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Informazioni su come usare il parcheggio di chiamata e recuperare per mettere una chiamata in attesa in Microsoft Teams.
ms.openlocfilehash: efc36a2bc90b64abf2e886c5e768a26704bd6550
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102802"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="ebfa1-103">Parcheggio di chiamata e recupero in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ebfa1-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="ebfa1-104">Il parcheggio di chiamata e il recupero è una funzionalità che consente a un utente di mettere una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="ebfa1-105">Quando una chiamata è parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="ebfa1-106">L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice con un'app o un dispositivo supportato per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="ebfa1-107">Per informazioni [dettagliate, vedere Parcheggiare](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) una chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="ebfa1-108">Alcuni degli scenari comuni per l'uso del parcheggio di chiamata sono:</span><span class="sxs-lookup"><span data-stu-id="ebfa1-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="ebfa1-109">Un addetto alla reception parcheggia una chiamata per qualcuno che lavora in una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="ebfa1-110">L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="ebfa1-111">L'utente per cui è stata chiamata può quindi prelevare un telefono Teams nella fabbrica e immettere il codice per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="ebfa1-112">Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo è in esaurimento.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="ebfa1-113">L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo di Teams.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="ebfa1-114">Un rappresentante del supporto parcheggia una chiamata del cliente e invia un annuncio su un canale di Teams per consentire a un esperto di recuperare la chiamata e aiutare il cliente.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="ebfa1-115">Un esperto immette il codice nei client di Teams per recuperare la chiamata</span><span class="sxs-lookup"><span data-stu-id="ebfa1-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="ebfa1-116">Per parcheggiare e recuperare le chiamate, un utente deve essere un VoIP aziendale utente e deve essere incluso in un criterio di parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ebfa1-117">Il parcheggio di chiamata e il recupero sono disponibili solo in [modalità di distribuzione](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Teams Only e non sono supportati nei telefoni IP Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="ebfa1-118">Configurare il parcheggio di chiamata e recuperare</span><span class="sxs-lookup"><span data-stu-id="ebfa1-118">Configure call park and retrieve</span></span>

<span data-ttu-id="ebfa1-119">Per configurare e recuperare il parcheggio di chiamata, è necessario essere un amministratore di Teams.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="ebfa1-120">È disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-120">It is disabled by default.</span></span> <span data-ttu-id="ebfa1-121">È possibile abilitarlo per gli utenti e creare gruppi di utenti usando i criteri di parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="ebfa1-122">Quando si applicano gli stessi criteri a un set di utenti, possono parcheggiare e recuperare le chiamate tra loro.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="ebfa1-123">Per abilitare un criterio di parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="ebfa1-123">To enable a call park policy</span></span>

1. <span data-ttu-id="ebfa1-124">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri  >  **del parco chiamate vocali.**</span><span class="sxs-lookup"><span data-stu-id="ebfa1-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="ebfa1-125">Nella scheda **Gestisci criteri** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="ebfa1-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="ebfa1-126">Assegnare un nome al criterio e quindi impostare **Consenti parcheggio di chiamata** su **Attivata.**</span><span class="sxs-lookup"><span data-stu-id="ebfa1-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Screenshot delle impostazioni dei criteri del parcheggio di chiamata](media/call-park-add-policy.png)

4. <span data-ttu-id="ebfa1-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-128">Select **Save**.</span></span>

<span data-ttu-id="ebfa1-129">È possibile modificare il criterio selezionandolo nell'elenco e facendo clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="ebfa1-130">Per il corretto funzionamento del criterio, è necessario assegnarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="ebfa1-131">È possibile [assegnare il criterio agli utenti singolarmente](assign-policies.md) o assegnarli a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="ebfa1-132">Per assegnare un criterio di parte di chiamata a un gruppo</span><span class="sxs-lookup"><span data-stu-id="ebfa1-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="ebfa1-133">Nella scheda **Assegnazione Criteri di** gruppo della pagina Criteri di parcheggio **di** chiamata fare clic su **Aggiungi gruppo.**</span><span class="sxs-lookup"><span data-stu-id="ebfa1-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="ebfa1-134">Cercare il gruppo da usare e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="ebfa1-135">Scegliere un rango rispetto ad altre assegnazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="ebfa1-136">In **Selezionare un criterio** scegliere il criterio a cui si vuole assegnare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Immagine dei criteri del parco](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="ebfa1-138">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="ebfa1-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ebfa1-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ebfa1-139">Related topics</span></span>

[<span data-ttu-id="ebfa1-140">Parcheggiare una chiamata in Teams</span><span class="sxs-lookup"><span data-stu-id="ebfa1-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="ebfa1-141">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="ebfa1-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="ebfa1-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ebfa1-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="ebfa1-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ebfa1-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="ebfa1-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ebfa1-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)