---
title: Criteri per le chiamate in Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti a criteri di chiamata personalizzati in Microsoft Teams, nonché varie impostazioni dei criteri di chiamata.
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
ms.openlocfilehash: 6cfa0043b4da6c3087c0e144bb0759ed5b87f01c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50465296"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="e173f-103">Criteri per le chiamate in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e173f-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="e173f-104">In Microsoft Teams, i criteri di chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e173f-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="e173f-105">I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, instradare le chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamata, utilizzare la delega per le chiamate in entrata e in uscita e così via.</span><span class="sxs-lookup"><span data-stu-id="e173f-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="e173f-106">È possibile usare il criterio globale (impostazione predefinita a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e173f-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="e173f-107">Creare un criterio di chiamata personalizzato</span><span class="sxs-lookup"><span data-stu-id="e173f-107">Create a custom calling policy</span></span>

<span data-ttu-id="e173f-108">Seguire questa procedura per creare un criterio di chiamata personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e173f-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="e173f-109">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Criteri per le chiamate**  >  **vocali.**</span><span class="sxs-lookup"><span data-stu-id="e173f-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e173f-110">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e173f-110">Select **Add**.</span></span>
3. <span data-ttu-id="e173f-111">Attivare o disattivare le funzionalità da usare nel criterio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e173f-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="e173f-112">Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, seleziona **Abilitato** o **Controllato dall'utente.**</span><span class="sxs-lookup"><span data-stu-id="e173f-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="e173f-113">Per impedire l'instradamento alla segreteria telefonica, seleziona **Disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="e173f-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="e173f-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e173f-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="e173f-115">Modificare un criterio di chiamata</span><span class="sxs-lookup"><span data-stu-id="e173f-115">Edit a calling policy</span></span>

<span data-ttu-id="e173f-116">Seguire questa procedura per modificare un criterio di chiamata esistente.</span><span class="sxs-lookup"><span data-stu-id="e173f-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="e173f-117">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, seleziona **Criteri per le chiamate**  >  **vocali.**</span><span class="sxs-lookup"><span data-stu-id="e173f-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e173f-118">Fare clic accanto al criterio da modificare e quindi selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e173f-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="e173f-119">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="e173f-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="e173f-120">Assegnare un criterio di chiamata personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="e173f-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="e173f-121">Impostazioni dei criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="e173f-121">Calling policy settings</span></span>

<span data-ttu-id="e173f-122">Ecco le impostazioni che è possibile configurare per i criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e173f-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="e173f-123">Effettuare chiamate private</span><span class="sxs-lookup"><span data-stu-id="e173f-123">Make private calls</span></span>

<span data-ttu-id="e173f-124">Questa impostazione controlla tutte le funzionalità di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="e173f-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="e173f-125">Disattivare questa opzione per disattivare tutte le funzionalità di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="e173f-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="e173f-126">Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e173f-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="e173f-127">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono squillare contemporaneamente a un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="e173f-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="e173f-128">Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni</span><span class="sxs-lookup"><span data-stu-id="e173f-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="e173f-129">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono squillare contemporaneamente a un numero esterno.</span><span class="sxs-lookup"><span data-stu-id="e173f-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="e173f-130">La segreteria telefonica è disponibile per l'instradamento delle chiamate in entrata</span><span class="sxs-lookup"><span data-stu-id="e173f-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="e173f-131">Questa impostazione consente l'invio delle chiamate in ingresso alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="e173f-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="e173f-132">Le opzioni valide sono:</span><span class="sxs-lookup"><span data-stu-id="e173f-132">Valid options are:</span></span>

- <span data-ttu-id="e173f-133">**Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in entrata.</span><span class="sxs-lookup"><span data-stu-id="e173f-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="e173f-134">**Disabilitato**  La segreteria telefonica non è disponibile per le chiamate in entrata.</span><span class="sxs-lookup"><span data-stu-id="e173f-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="e173f-135">**Utente controllato** Gli utenti possono stabilire se vogliono che la segreteria telefonica sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="e173f-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="e173f-136">Le chiamate in ingresso possono essere instradati ai gruppi di chiamata</span><span class="sxs-lookup"><span data-stu-id="e173f-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="e173f-137">Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e173f-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="e173f-138">Consentire la delega per le chiamate in ingresso e in uscita</span><span class="sxs-lookup"><span data-stu-id="e173f-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="e173f-139">Questa impostazione consente di instradare le chiamate in ingresso ai delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali hanno autorizzazioni delegate.</span><span class="sxs-lookup"><span data-stu-id="e173f-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="e173f-140">Per altre informazioni, vedere [Condividere una linea telefonica con un delegato.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="e173f-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="e173f-141">Evitare il bypass a pedaggio e inviare chiamate tramite PSTN</span><span class="sxs-lookup"><span data-stu-id="e173f-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="e173f-142">Impostando questa opzione **su On,** le chiamate vengono inviate tramite PSTN e vengono sostenute le chiamate invece di inviarle tramite la rete, senza superare i caselli a pagamento.</span><span class="sxs-lookup"><span data-stu-id="e173f-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="e173f-143">Occupato in Stato di occupato è disponibile durante una chiamata</span><span class="sxs-lookup"><span data-stu-id="e173f-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="e173f-144">Occupato in Disponibilità (Opzioni occupato) è una nuova impostazione che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o conferenza o ha una chiamata messa in attesa.</span><span class="sxs-lookup"><span data-stu-id="e173f-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="e173f-145">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato.</span><span class="sxs-lookup"><span data-stu-id="e173f-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="e173f-146">È possibile abilitare le opzioni di occupato a livello di tenant o di utente.</span><span class="sxs-lookup"><span data-stu-id="e173f-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="e173f-147">Indipendentemente da come sono configurate le opzioni di occupato, gli utenti in una chiamata o conferenza o gli utenti con chiamata in attesa non possono avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="e173f-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="e173f-148">Questa impostazione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e173f-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="e173f-149">Consenti chiamate PSTN Web</span><span class="sxs-lookup"><span data-stu-id="e173f-149">Allow web PSTN calling</span></span>

<span data-ttu-id="e173f-150">Questa impostazione consente agli utenti di chiamare i numeri PSTN utilizzando il client Web di Teams.</span><span class="sxs-lookup"><span data-stu-id="e173f-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="e173f-151">Consenti musica durante l'attesa</span><span class="sxs-lookup"><span data-stu-id="e173f-151">Allow music on hold</span></span>

<span data-ttu-id="e173f-152">Questa impostazione consente di attivare o disattivare l'attesa di musica quando un chiamante PSTN è in attesa.</span><span class="sxs-lookup"><span data-stu-id="e173f-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="e173f-153">È attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e173f-153">It's turned on by default.</span></span> <span data-ttu-id="e173f-154">Questa impostazione non si applica alle funzionalità per i delegati del parco chiamate e del responsabile ed è attualmente disponibile solo tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e173f-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e173f-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e173f-155">Related topics</span></span>

[<span data-ttu-id="e173f-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="e173f-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="e173f-157">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="e173f-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
