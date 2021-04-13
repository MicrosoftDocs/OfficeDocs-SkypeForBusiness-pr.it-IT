---
title: Criteri di chiamata in Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti a criteri di chiamata personalizzati in Microsoft Teams, oltre a varie impostazioni dei criteri di chiamata.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e469cc183134bab35855e83257126029ce78a8cc
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51653944"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="6e944-103">Criteri di chiamata in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e944-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="6e944-104">In Microsoft Teams, i criteri di chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6e944-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="6e944-105">I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, instradare le chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via.</span><span class="sxs-lookup"><span data-stu-id="6e944-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="6e944-106">È possibile usare i criteri globali (predefiniti a livello di organizzazione) creati automaticamente oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6e944-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="6e944-107">Creare criteri di chiamata personalizzati</span><span class="sxs-lookup"><span data-stu-id="6e944-107">Create a custom calling policy</span></span>

<span data-ttu-id="6e944-108">Seguire questa procedura per creare un criterio di chiamata personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e944-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="6e944-109">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Criteri **per le chiamate**  >  **vocali.**</span><span class="sxs-lookup"><span data-stu-id="6e944-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="6e944-110">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6e944-110">Select **Add**.</span></span>
3. <span data-ttu-id="6e944-111">Attivare o disattivare le funzionalità da usare nei criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6e944-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="6e944-112">Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **Abilitato** o **Controllato dall'utente.**</span><span class="sxs-lookup"><span data-stu-id="6e944-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="6e944-113">Per impedire l'instradamento alla segreteria telefonica, selezionare **Disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="6e944-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="6e944-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6e944-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="6e944-115">Modificare un criterio di chiamata</span><span class="sxs-lookup"><span data-stu-id="6e944-115">Edit a calling policy</span></span>

<span data-ttu-id="6e944-116">Seguire questa procedura per modificare un criterio di chiamata esistente.</span><span class="sxs-lookup"><span data-stu-id="6e944-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="6e944-117">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Criteri per le chiamate**  >  **vocali.**</span><span class="sxs-lookup"><span data-stu-id="6e944-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="6e944-118">Fare clic accanto al criterio da modificare e quindi selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="6e944-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="6e944-119">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="6e944-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="6e944-120">Assegnare un criterio di chiamata personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="6e944-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="6e944-121">Impostazioni dei criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="6e944-121">Calling policy settings</span></span>

<span data-ttu-id="6e944-122">Ecco le impostazioni che è possibile configurare per i criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6e944-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="6e944-123">Effettuare chiamate private</span><span class="sxs-lookup"><span data-stu-id="6e944-123">Make private calls</span></span>

<span data-ttu-id="6e944-124">Questa impostazione controlla tutte le funzionalità di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="6e944-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="6e944-125">Disattiva questa opzione per disattivare tutte le funzionalità di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="6e944-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="6e944-126">Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6e944-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="6e944-127">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono squillare contemporaneamente a un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="6e944-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="6e944-128">Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni</span><span class="sxs-lookup"><span data-stu-id="6e944-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="6e944-129">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono squillare contemporaneamente a un numero esterno.</span><span class="sxs-lookup"><span data-stu-id="6e944-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="6e944-130">La segreteria telefonica è disponibile per il routing delle chiamate in ingresso</span><span class="sxs-lookup"><span data-stu-id="6e944-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="6e944-131">Questa impostazione consente di inviare chiamate in ingresso alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="6e944-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="6e944-132">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="6e944-132">Valid options are:</span></span>

- <span data-ttu-id="6e944-133">**Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6e944-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="6e944-134">**Disabilitato**  La segreteria telefonica non è disponibile per le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6e944-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="6e944-135">**Controllato dall'utente** Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="6e944-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="6e944-136">Le chiamate in ingresso possono essere instradati ai gruppi di chiamate</span><span class="sxs-lookup"><span data-stu-id="6e944-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="6e944-137">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="6e944-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="6e944-138">Consentire la delega per le chiamate in ingresso e in uscita</span><span class="sxs-lookup"><span data-stu-id="6e944-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="6e944-139">Questa impostazione consente di instradare le chiamate in ingresso ai delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per cui hanno autorizzazioni delegate.</span><span class="sxs-lookup"><span data-stu-id="6e944-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="6e944-140">Per altre informazioni, vedere [Condividere una linea telefonica con un delegato.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="6e944-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="6e944-141">Evitare il bypass a pedaggio e inviare chiamate tramite PSTN</span><span class="sxs-lookup"><span data-stu-id="6e944-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="6e944-142">Se si imposta questa opzione **su Attivata,** le chiamate verranno inviate tramite PSTN e verranno sostenute spese invece di inviarle tramite la rete e ignorare i pedaggi.</span><span class="sxs-lookup"><span data-stu-id="6e944-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="6e944-143">Occupato su Occupato è disponibile durante una chiamata</span><span class="sxs-lookup"><span data-stu-id="6e944-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="6e944-144">Occupato (Opzioni occupato) è una nuova impostazione che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa.</span><span class="sxs-lookup"><span data-stu-id="6e944-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="6e944-145">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o instradate di conseguenza alle impostazioni senza risposta dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6e944-145">New or incoming calls can be rejected with a busy signal or can be routed accordingly to the user's unanswered settings.</span></span> <span data-ttu-id="6e944-146">È possibile abilitare le opzioni di disponibilità a livello di tenant o a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="6e944-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="6e944-147">Indipendentemente dal modo in cui vengono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o quelli con una chiamata in attesa non possono avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="6e944-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="6e944-148">Questa impostazione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6e944-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="6e944-149">Consenti chiamate PSTN Web</span><span class="sxs-lookup"><span data-stu-id="6e944-149">Allow web PSTN calling</span></span>

<span data-ttu-id="6e944-150">Questa impostazione consente agli utenti di chiamare numeri PSTN usando il client Web di Teams.</span><span class="sxs-lookup"><span data-stu-id="6e944-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="6e944-151">Consentire la musica in attesa</span><span class="sxs-lookup"><span data-stu-id="6e944-151">Allow music on hold</span></span>

<span data-ttu-id="6e944-152">Questa impostazione consente di attivare o disattivare il blocco della musica quando un chiamante PSTN viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="6e944-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="6e944-153">È attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6e944-153">It's turned on by default.</span></span> <span data-ttu-id="6e944-154">Questa impostazione non si applica alle funzionalità di parcheggio di chiamata e delegato del responsabile ed è attualmente disponibile solo tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e944-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e944-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6e944-155">Related topics</span></span>

[<span data-ttu-id="6e944-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="6e944-156">Set-CSTeamsCallingPolicy</span></span>](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="6e944-157">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="6e944-157">Assign policies to your users in Teams</span></span>](assign-policies.md)