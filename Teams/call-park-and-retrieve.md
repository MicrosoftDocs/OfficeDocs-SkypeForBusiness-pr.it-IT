---
title: Chiamare il parco e recuperare in Microsoft Teams
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
description: Informazioni su come usare il parco chiamate e recuperare per mettere una chiamata in attesa in Microsoft Teams.
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278716"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="35500-103">Chiamare il parco e recuperare in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35500-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="35500-104">Il "call park and retrieve" è una funzionalità che consente a un utente di mettere in attesa una chiamata.</span><span class="sxs-lookup"><span data-stu-id="35500-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="35500-105">Quando una chiamata è in stato di parked, il servizio genera un codice univoco per il recupero delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="35500-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="35500-106">L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare quel codice con un'app o un dispositivo supportato per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35500-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="35500-107">Per informazioni [dettagliate, vedere "Parco di](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) una chiamata in Teams".</span><span class="sxs-lookup"><span data-stu-id="35500-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="35500-108">Di seguito sono riportati alcuni degli scenari comuni in cui viene utilizzato il parco delle chiamate:</span><span class="sxs-lookup"><span data-stu-id="35500-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="35500-109">Un addetto alla reception può chiamare qualcuno che lavora in una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="35500-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="35500-110">L'addetto della reception enuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici.</span><span class="sxs-lookup"><span data-stu-id="35500-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="35500-111">L'utente a cui è stata chiamata può quindi prelevare un telefono Teams nell'area di produzione e immettere il codice per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35500-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="35500-112">Un utente può eseguire una chiamata su un dispositivo mobile perché la batteria del dispositivo sta per esaurimento.</span><span class="sxs-lookup"><span data-stu-id="35500-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="35500-113">L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo di Teams.</span><span class="sxs-lookup"><span data-stu-id="35500-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="35500-114">Un rappresentante del supporto ha chiamato una cliente e invia un annuncio su un canale di Teams a un esperto per recuperare la chiamata e aiutare il cliente.</span><span class="sxs-lookup"><span data-stu-id="35500-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="35500-115">Un esperto immette il codice nei client di Teams per recuperare la chiamata</span><span class="sxs-lookup"><span data-stu-id="35500-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="35500-116">Per poter effettuare e recuperare chiamate, è necessario che l'utente sia VoIP aziendale un utente specifico e che sia incluso nei criteri per il parco chiamate.</span><span class="sxs-lookup"><span data-stu-id="35500-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="35500-117">Il parco chiamate e il recupero sono disponibili solo in modalità [di distribuzione di Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e non sono supportati sui telefoni IP di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="35500-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="35500-118">Configurare il parco chiamate e recuperarlo</span><span class="sxs-lookup"><span data-stu-id="35500-118">Configure call park and retrieve</span></span>

<span data-ttu-id="35500-119">È necessario essere un amministratore di Teams per configurare il parco chiamate e recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="35500-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="35500-120">Per impostazione predefinita, l'opzione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="35500-120">It is disabled by default.</span></span> <span data-ttu-id="35500-121">È possibile abilitarla per gli utenti e creare gruppi di utenti usando i criteri per il parco chiamate.</span><span class="sxs-lookup"><span data-stu-id="35500-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="35500-122">Quando si applicano gli stessi criteri a un set di utenti, questi possono effettuare un parco e recuperare le chiamate tra loro.</span><span class="sxs-lookup"><span data-stu-id="35500-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="35500-123">Per abilitare i criteri di un parco chiamate</span><span class="sxs-lookup"><span data-stu-id="35500-123">To enable a call park policy</span></span>

1. <span data-ttu-id="35500-124">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa ai **criteri di** parco delle  >  **chiamate vocali.**</span><span class="sxs-lookup"><span data-stu-id="35500-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="35500-125">Nella scheda **Gestisci criteri** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="35500-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="35500-126">Assegnare un nome al criterio e quindi attivare Consenti il **parco** **chiamate.**</span><span class="sxs-lookup"><span data-stu-id="35500-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Schermata delle impostazioni dei criteri di parco chiamate](media/call-park-add-policy.png)

4. <span data-ttu-id="35500-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35500-128">Select **Save**.</span></span>

<span data-ttu-id="35500-129">È possibile modificare il criterio selezionandolo nell'elenco e facendo clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="35500-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="35500-130">Per il funzionamento, il criterio deve essere assegnato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="35500-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="35500-131">È possibile [assegnare il criterio agli utenti singolarmente](assign-policies.md) o assegnarli a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="35500-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="35500-132">Per assegnare criteri per le parti di chiamata a un gruppo</span><span class="sxs-lookup"><span data-stu-id="35500-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="35500-133">Nella pagina Criteri per il  parco **chiamate** fare clic su Aggiungi gruppo nella scheda Assegnazione di Criteri di **gruppo.**</span><span class="sxs-lookup"><span data-stu-id="35500-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="35500-134">Cercare il gruppo da usare e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="35500-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="35500-135">Scegliere un rango rispetto alle altre assegnazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="35500-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="35500-136">In **Seleziona un criterio** scegliere il criterio a cui assegnare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="35500-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![park policies image](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="35500-138">Selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="35500-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35500-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="35500-139">Related topics</span></span>

[<span data-ttu-id="35500-140">Parco di una chiamata in Teams</span><span class="sxs-lookup"><span data-stu-id="35500-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="35500-141">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="35500-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="35500-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="35500-142">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="35500-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="35500-143">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="35500-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="35500-144">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
