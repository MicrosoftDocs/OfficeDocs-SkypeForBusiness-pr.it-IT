---
title: Chiamare il parcheggio e il recupero in Microsoft Teams
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
description: Informazioni su come usare Call Park e retrieve per effettuare una chiamata in attesa in Microsoft teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424594"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="1c32e-103">Chiamare il parcheggio e il recupero in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c32e-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="1c32e-104">Call Park and retrieve è una funzionalità che consente a un utente di effettuare una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="1c32e-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="1c32e-105">Quando una chiamata viene parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1c32e-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="1c32e-106">L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice con un'app o un dispositivo supportato per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c32e-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="1c32e-107">Per informazioni dettagliate, vedere [parcheggiare una chiamata in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .</span><span class="sxs-lookup"><span data-stu-id="1c32e-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="1c32e-108">Alcuni degli scenari comuni per l'uso di Call Park sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c32e-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="1c32e-109">Un receptionist parcheggia una chiamata per qualcuno che lavora in una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="1c32e-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="1c32e-110">L'addetto alla ricezione annuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici.</span><span class="sxs-lookup"><span data-stu-id="1c32e-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="1c32e-111">L'utente a cui è consentita la chiamata può quindi prendere un telefono per le squadre in fabbrica e immettere il codice per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c32e-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="1c32e-112">Un utente parcheggia una chiamata su un dispositivo mobile perché la batteria del dispositivo sta esaurendo la potenza.</span><span class="sxs-lookup"><span data-stu-id="1c32e-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="1c32e-113">L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo teams.</span><span class="sxs-lookup"><span data-stu-id="1c32e-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="1c32e-114">Un supporto rappresentativo parcheggia una chiamata del cliente e invia un annuncio su un canale di teams per un esperto per recuperare la chiamata e aiutare il cliente.</span><span class="sxs-lookup"><span data-stu-id="1c32e-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="1c32e-115">Un esperto immette il codice nei client di teams per recuperare la chiamata</span><span class="sxs-lookup"><span data-stu-id="1c32e-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="1c32e-116">Per parcheggiare e recuperare le chiamate, un utente deve essere un utente di VoIP aziendale e deve essere incluso in un criterio per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1c32e-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="1c32e-117">Call Park and retrieve è disponibile solo in [modalità di distribuzione solo in teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e non è supportato nei telefoni IP Skype for business.</span><span class="sxs-lookup"><span data-stu-id="1c32e-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="1c32e-118">Configurare il parcheggio delle chiamate e il recupero</span><span class="sxs-lookup"><span data-stu-id="1c32e-118">Configure call park and retrieve</span></span>

<span data-ttu-id="1c32e-119">È necessario essere un amministratore di teams per configurare Call Park e retrieve.</span><span class="sxs-lookup"><span data-stu-id="1c32e-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="1c32e-120">È disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1c32e-120">It is disabled by default.</span></span> <span data-ttu-id="1c32e-121">Puoi abilitarlo per gli utenti e creare gruppi di utenti usando i criteri per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1c32e-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="1c32e-122">Quando si applica lo stesso criterio a un set di utenti, è possibile parcheggiare e recuperare le chiamate tra di loro.</span><span class="sxs-lookup"><span data-stu-id="1c32e-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="1c32e-123">Per abilitare un criterio per il parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="1c32e-123">To enable a call park policy</span></span>

1. <span data-ttu-id="1c32e-124">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**accedere ai criteri per il parcheggio per le  >  **chiamate**vocali.</span><span class="sxs-lookup"><span data-stu-id="1c32e-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="1c32e-125">Nella scheda **Gestisci criteri** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1c32e-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="1c32e-126">Assegnare un nome al criterio e quindi passare **Consenti al parcheggio** di chiamata **.**</span><span class="sxs-lookup"><span data-stu-id="1c32e-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Screenshot delle impostazioni dei criteri per il parcheggio delle chiamate](media/call-park-add-policy.png)

4. <span data-ttu-id="1c32e-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1c32e-128">Select **Save**.</span></span>

<span data-ttu-id="1c32e-129">Per modificare il criterio, selezionarlo nell'elenco e fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="1c32e-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="1c32e-130">Affinché il criterio funzioni, deve essere assegnato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1c32e-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="1c32e-131">È possibile [assegnare i criteri agli utenti singolarmente](assign-policies.md) o assegnarli a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="1c32e-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="1c32e-132">Per assegnare un criterio per la parte di chiamata a un gruppo</span><span class="sxs-lookup"><span data-stu-id="1c32e-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="1c32e-133">Nella pagina **criteri di parcheggio chiamata** , nella scheda **assegnazione criteri di gruppo** , fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="1c32e-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="1c32e-134">Cercare il gruppo che si vuole usare e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1c32e-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="1c32e-135">Scegliere un rango rispetto ad altre assegnazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="1c32e-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="1c32e-136">In **selezionare un criterio**scegliere i criteri a cui si vuole assegnare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="1c32e-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="1c32e-137">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="1c32e-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1c32e-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1c32e-138">Related topics</span></span>

[<span data-ttu-id="1c32e-139">Parcheggiare una chiamata in teams</span><span class="sxs-lookup"><span data-stu-id="1c32e-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="1c32e-140">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="1c32e-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="1c32e-141">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="1c32e-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="1c32e-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="1c32e-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="1c32e-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="1c32e-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)