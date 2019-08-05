---
title: Criteri di chiamata in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Informazioni sulle impostazioni dei criteri di chiamata in Microsoft teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c35c2455c3164f04dd9fdbbb210e20809a719bc6
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2019
ms.locfileid: "36182062"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="a9941-103">Criteri di chiamata in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a9941-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="a9941-104">In Microsoft teams, i criteri di chiamata controllano quali funzionalità di inoltro delle chiamate e di chiamata sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a9941-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="a9941-105">I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, inoltrare chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via.</span><span class="sxs-lookup"><span data-stu-id="a9941-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="a9941-106">Viene creato automaticamente un criterio globale predefinito, ma gli amministratori possono anche creare e assegnare criteri di chiamata personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a9941-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="a9941-107">Creare un criterio di chiamata personalizzato</span><span class="sxs-lookup"><span data-stu-id="a9941-107">Create a custom calling policy</span></span>

<span data-ttu-id="a9941-108">Seguire questa procedura per creare un criterio di chiamata personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a9941-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="a9941-109">Nell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le**chiamate** **vocali** > .</span><span class="sxs-lookup"><span data-stu-id="a9941-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="a9941-110">Selezionare **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="a9941-110">Select **New policy**.</span></span>
3. <span data-ttu-id="a9941-111">Attivare le funzionalità che si desidera utilizzare nei criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9941-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="a9941-112">Tutte le selezioni sono \*\*\*\* disattivate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9941-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="a9941-113">Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **sempre abilitato** o **controllato dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="a9941-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="a9941-114">Per impedire il routing alla segreteria telefonica, selezionare **sempre disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="a9941-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="a9941-115">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a9941-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="a9941-116">Modificare un criterio di chiamata esistente</span><span class="sxs-lookup"><span data-stu-id="a9941-116">Modify an existing calling policy</span></span>

<span data-ttu-id="a9941-117">Seguire questa procedura per modificare un criterio di chiamata esistente.</span><span class="sxs-lookup"><span data-stu-id="a9941-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="a9941-118">Nell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le**chiamate** **vocali** > .</span><span class="sxs-lookup"><span data-stu-id="a9941-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="a9941-119">Fare clic su accanto al criterio che si vuole modificare e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a9941-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="a9941-120">Attivare le funzionalità che si desidera utilizzare nei criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9941-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="a9941-121">Tutte le selezioni sono \*\*\*\* disattivate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9941-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="a9941-122">Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **sempre abilitato** o **controllato dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="a9941-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="a9941-123">Per impedire il routing alla segreteria telefonica, selezionare **sempre disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="a9941-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="a9941-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a9941-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="a9941-125">Assegnare un criterio di chiamata a un utente</span><span class="sxs-lookup"><span data-stu-id="a9941-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="a9941-126">Seguire questa procedura per assegnare un criterio di chiamata personalizzato a un utente.</span><span class="sxs-lookup"><span data-stu-id="a9941-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="a9941-127">Nell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le**chiamate** **vocali** > .</span><span class="sxs-lookup"><span data-stu-id="a9941-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="a9941-128">Fare clic su accanto al nome del criterio per selezionarlo e quindi selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="a9941-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="a9941-129">Nel riquadro **Gestisci utenti** cercare il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a9941-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="a9941-130">È necessario immettere almeno tre caratteri.</span><span class="sxs-lookup"><span data-stu-id="a9941-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="a9941-131">Selezionare il nome dell'utente e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a9941-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="a9941-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a9941-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="a9941-133">Impostazioni dei criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="a9941-133">Calling policy settings</span></span>

<span data-ttu-id="a9941-134">Usare le impostazioni seguenti per creare criteri di chiamata personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a9941-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="a9941-135">L'utente può effettuare chiamate private</span><span class="sxs-lookup"><span data-stu-id="a9941-135">User can make private calls</span></span>

<span data-ttu-id="a9941-136">Questa impostazione controlla tutte le funzionalità di chiamata in teams.</span><span class="sxs-lookup"><span data-stu-id="a9941-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="a9941-137">Disattivare questa opzione per disattivare tutte le funzionalità di chiamata in teams.</span><span class="sxs-lookup"><span data-stu-id="a9941-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="a9941-138">Inoltro di chiamata e squillo simultaneo ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="a9941-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="a9941-139">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono chiamare un'altra persona contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a9941-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="a9941-140">Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni</span><span class="sxs-lookup"><span data-stu-id="a9941-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="a9941-141">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono chiamare contemporaneamente un numero esterno.</span><span class="sxs-lookup"><span data-stu-id="a9941-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="a9941-142">La segreteria telefonica è disponibile per il routing delle chiamate in ingresso agli utenti</span><span class="sxs-lookup"><span data-stu-id="a9941-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="a9941-143">Questa impostazione consente l'invio di chiamate in ingresso alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="a9941-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="a9941-144">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="a9941-144">Valid options are:</span></span>

   - <span data-ttu-id="a9941-145">**Sempre abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a9941-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="a9941-146">**Sempre disabilitato**  La segreteria telefonica non è disponibile per le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a9941-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="a9941-147">**Utente controllato**.</span><span class="sxs-lookup"><span data-stu-id="a9941-147">**User controlled**.</span></span> <span data-ttu-id="a9941-148">Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9941-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="a9941-149">Le chiamate in ingresso possono essere instradate a gruppi di chiamate</span><span class="sxs-lookup"><span data-stu-id="a9941-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="a9941-150">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="a9941-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="a9941-151">Consentire la delega per le chiamate in ingresso e in uscita</span><span class="sxs-lookup"><span data-stu-id="a9941-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="a9941-152">Questa impostazione consente alle chiamate in ingresso di essere instradate a delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali sono state delegate le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a9941-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="a9941-153">Per altre informazioni, vedere [condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="a9941-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="a9941-154">Impedire l'esclusione del pedaggio e inviare chiamate tramite la rete PSTN</span><span class="sxs-lookup"><span data-stu-id="a9941-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="a9941-155">Se si imposta questa opzione **su** attivato, le chiamate verranno inviate tramite la rete PSTN e incorreremo in spese piuttosto che inviarle tramite il network e aggirare i pedaggi.</span><span class="sxs-lookup"><span data-stu-id="a9941-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="a9941-156">La disponibilità di occupato è disponibile durante una chiamata</span><span class="sxs-lookup"><span data-stu-id="a9941-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="a9941-157">Occupato in occupato (opzioni di occupato)) è una nuova impostazione nei criteri di chiamata dei team che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="a9941-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="a9941-158">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato.</span><span class="sxs-lookup"><span data-stu-id="a9941-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="a9941-159">È possibile abilitare le opzioni di occupato a livello di tenant o a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="a9941-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="a9941-160">Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o di una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="a9941-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="a9941-161">Questa impostazione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9941-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9941-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9941-162">See also</span></span>

[<span data-ttu-id="a9941-163">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9941-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)