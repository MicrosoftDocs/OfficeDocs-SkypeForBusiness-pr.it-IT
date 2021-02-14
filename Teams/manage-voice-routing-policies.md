---
title: Gestire i criteri di routing vocale in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come creare e gestire i criteri di routing vocale in Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802556"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="4c6f6-103">Gestire i criteri di routing vocale in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c6f6-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="4c6f6-104">Se hai distribuito [](direct-routing-landing-page.md) il routing diretto del sistema telefonico nella tua organizzazione, utilizzi i criteri di routing vocale per consentire agli utenti di Teams e Skype for Business online di ricevere ed effettuare chiamate alla rete PSTN (Public Switched Telephone Network) utilizzando l'infrastruttura di telefonia locale.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="4c6f6-105">Un criterio di routing vocale è un contenitore per i record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="4c6f6-106">Per creare e gestire i criteri di routing vocale, è possibile accedere ai criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams o tramite  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="4c6f6-107">È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4c6f6-108">Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="4c6f6-109">Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="4c6f6-110">È importante sapere che l'assegnazione di criteri di routing vocale a un utente non gli consente di effettuare chiamate PSTN in Teams.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="4c6f6-111">Dovrai anche abilitare l'utente per l'instradamento diretto del sistema telefonico ed eseguire altri passaggi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="4c6f6-112">Per altre informazioni, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="4c6f6-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="4c6f6-113">Creare criteri di routing vocale personalizzati</span><span class="sxs-lookup"><span data-stu-id="4c6f6-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c6f6-114">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4c6f6-115">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Criteri  >  **di instradamento vocale,** quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="4c6f6-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="4c6f6-116">![Screenshot della pagina Aggiungi criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="4c6f6-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="4c6f6-117">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="4c6f6-118">In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN** e quindi selezionare i record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="4c6f6-119">Se è necessario creare un nuovo record di utilizzo PSTN, fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="4c6f6-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="4c6f6-120">Se sono stati aggiunti più record di utilizzo PSTN, disporli nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="4c6f6-121">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="4c6f6-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="4c6f6-122">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c6f6-123">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c6f6-123">Using PowerShell</span></span>

<span data-ttu-id="4c6f6-124">Vedi [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="4c6f6-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="4c6f6-125">Modificare un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="4c6f6-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c6f6-126">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4c6f6-127">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="4c6f6-128">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Criteri**  >  **di instradamento vocale.**</span><span class="sxs-lookup"><span data-stu-id="4c6f6-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="4c6f6-129">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c6f6-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4c6f6-130">Fare **clic su Aggiungi/rimuovi record** di utilizzo PSTN, apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="4c6f6-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c6f6-131">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c6f6-131">Using PowerShell</span></span>

<span data-ttu-id="4c6f6-132">Vedi [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="4c6f6-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="4c6f6-133">Assegnare un criterio di routing vocale personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="4c6f6-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="4c6f6-134">Vedere anche [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="4c6f6-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c6f6-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4c6f6-135">Related topics</span></span>

[<span data-ttu-id="4c6f6-136">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="4c6f6-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="4c6f6-137">Configurare il routing vocale per l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4c6f6-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="4c6f6-138">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4c6f6-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="4c6f6-139">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="4c6f6-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
