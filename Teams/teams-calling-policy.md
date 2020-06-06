---
title: Criteri di chiamata in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti ai criteri per le chiamate personalizzate in Microsoft teams, nonché varie impostazioni dei criteri di chiamata.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592861"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="d62bc-103">Criteri di chiamata in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d62bc-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="d62bc-104">In Microsoft teams, i criteri di chiamata controllano quali funzionalità di inoltro delle chiamate e di chiamata sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d62bc-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="d62bc-105">I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, inoltrare chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via.</span><span class="sxs-lookup"><span data-stu-id="d62bc-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="d62bc-106">Viene creato automaticamente un criterio globale predefinito, ma gli amministratori possono anche creare e assegnare criteri di chiamata personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d62bc-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="d62bc-107">Creare un criterio di chiamata personalizzato</span><span class="sxs-lookup"><span data-stu-id="d62bc-107">Create a custom calling policy</span></span>

<span data-ttu-id="d62bc-108">Seguire questa procedura per creare un criterio di chiamata personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d62bc-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="d62bc-109">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**scegliere criteri per le  >  **chiamate**vocali.</span><span class="sxs-lookup"><span data-stu-id="d62bc-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="d62bc-110">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-110">Select **Add**.</span></span>
3. <span data-ttu-id="d62bc-111">Attivare o disattivare le caratteristiche che si desidera utilizzare nei criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d62bc-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="d62bc-112">Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **abilitato** o **controllato dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="d62bc-113">Per impedire il routing alla segreteria telefonica, selezionare **disabled**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="d62bc-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="d62bc-115">Modificare un criterio di chiamata esistente</span><span class="sxs-lookup"><span data-stu-id="d62bc-115">Modify an existing calling policy</span></span>

<span data-ttu-id="d62bc-116">Seguire questa procedura per modificare un criterio di chiamata esistente.</span><span class="sxs-lookup"><span data-stu-id="d62bc-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="d62bc-117">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le **Voice**  >  **chiamate**vocali.</span><span class="sxs-lookup"><span data-stu-id="d62bc-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="d62bc-118">Fare clic su accanto al criterio che si vuole modificare e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="d62bc-119">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="d62bc-120">Assegnare un criterio di chiamata personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="d62bc-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="d62bc-121">Per assegnare un criterio a un utente:</span><span class="sxs-lookup"><span data-stu-id="d62bc-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="d62bc-122">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="d62bc-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d62bc-123">Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d62bc-124">In **criteri di chiamata**selezionare il criterio di chiamata che si vuole assegnare e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="d62bc-125">Per assegnare un criterio a più utenti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="d62bc-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d62bc-126">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="d62bc-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d62bc-127">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d62bc-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d62bc-128">Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="d62bc-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d62bc-129">Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="d62bc-130">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d62bc-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d62bc-131">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**scegliere criteri per le  >  **chiamate**vocali.</span><span class="sxs-lookup"><span data-stu-id="d62bc-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="d62bc-132">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="d62bc-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d62bc-133">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="d62bc-134">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d62bc-135">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="d62bc-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d62bc-136">Dopo avere aggiunto gli utenti, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d62bc-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="d62bc-137">Impostazioni dei criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="d62bc-137">Calling policy settings</span></span>

<span data-ttu-id="d62bc-138">Ecco le impostazioni che è possibile configurare per i criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d62bc-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="d62bc-139">Effettuare chiamate private</span><span class="sxs-lookup"><span data-stu-id="d62bc-139">Make private calls</span></span>

<span data-ttu-id="d62bc-140">Questa impostazione controlla tutte le funzionalità di chiamata in teams.</span><span class="sxs-lookup"><span data-stu-id="d62bc-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="d62bc-141">Disattivare questa opzione per disattivare tutte le funzionalità di chiamata in teams.</span><span class="sxs-lookup"><span data-stu-id="d62bc-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="d62bc-142">Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d62bc-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="d62bc-143">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono chiamare un'altra persona contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d62bc-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="d62bc-144">Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni</span><span class="sxs-lookup"><span data-stu-id="d62bc-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="d62bc-145">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono chiamare contemporaneamente un numero esterno.</span><span class="sxs-lookup"><span data-stu-id="d62bc-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="d62bc-146">La segreteria telefonica è disponibile per il routing delle chiamate in ingresso</span><span class="sxs-lookup"><span data-stu-id="d62bc-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="d62bc-147">Questa impostazione consente l'invio di chiamate in ingresso alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="d62bc-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="d62bc-148">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="d62bc-148">Valid options are:</span></span>

- <span data-ttu-id="d62bc-149">**Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d62bc-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="d62bc-150">**Disabilitata**  La segreteria telefonica non è disponibile per le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d62bc-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="d62bc-151">**Utente controllato** Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="d62bc-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="d62bc-152">Le chiamate in ingresso possono essere instradate a gruppi di chiamate</span><span class="sxs-lookup"><span data-stu-id="d62bc-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="d62bc-153">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="d62bc-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="d62bc-154">Consentire la delega per le chiamate in ingresso e in uscita</span><span class="sxs-lookup"><span data-stu-id="d62bc-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="d62bc-155">Questa impostazione consente alle chiamate in ingresso di essere instradate a delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali sono state delegate le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d62bc-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="d62bc-156">Per altre informazioni, vedere [condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="d62bc-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="d62bc-157">Impedire l'esclusione del pedaggio e inviare chiamate tramite la rete PSTN</span><span class="sxs-lookup"><span data-stu-id="d62bc-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="d62bc-158">Se si imposta questa opzione **su** attivato, le chiamate verranno inviate tramite la rete PSTN e incorreremo in spese piuttosto che inviarle tramite il network e aggirare i pedaggi.</span><span class="sxs-lookup"><span data-stu-id="d62bc-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="d62bc-159">La disponibilità di occupato è disponibile durante una chiamata</span><span class="sxs-lookup"><span data-stu-id="d62bc-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="d62bc-160">Occupato in occupato (le opzioni di occupato) è una nuova impostazione che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="d62bc-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="d62bc-161">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato.</span><span class="sxs-lookup"><span data-stu-id="d62bc-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="d62bc-162">È possibile abilitare le opzioni di occupato a livello di tenant o a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="d62bc-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="d62bc-163">Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o di una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="d62bc-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="d62bc-164">Questa impostazione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d62bc-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="d62bc-165">Consenti chiamate PSTN Web</span><span class="sxs-lookup"><span data-stu-id="d62bc-165">Allow web PSTN calling</span></span>

<span data-ttu-id="d62bc-166">Questa impostazione consente agli utenti di chiamare numeri PSTN tramite il client Web teams.</span><span class="sxs-lookup"><span data-stu-id="d62bc-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="d62bc-167">Consenti musica in attesa</span><span class="sxs-lookup"><span data-stu-id="d62bc-167">Allow music on hold</span></span>

<span data-ttu-id="d62bc-168">Questa impostazione consente di attivare o disattivare la musica in attesa quando un chiamante PSTN viene posizionato in attesa.</span><span class="sxs-lookup"><span data-stu-id="d62bc-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="d62bc-169">È attivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d62bc-169">It's turned on by default.</span></span> <span data-ttu-id="d62bc-170">Questa impostazione non si applica alle caratteristiche di Call Park e boss delegate ed è attualmente disponibile solo tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d62bc-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="d62bc-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d62bc-171">See also</span></span>

[<span data-ttu-id="d62bc-172">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="d62bc-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
