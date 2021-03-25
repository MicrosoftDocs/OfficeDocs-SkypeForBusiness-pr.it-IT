---
title: Gestire i criteri per le chiamate di emergenza in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa succede quando un utente di Teams nell'organizzazione effettua una chiamata di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120567"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="fc5b4-103">Gestire i criteri per le chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc5b4-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="fc5b4-104">Se l'organizzazione usa Piani per chiamate o routing diretto del sistema telefonico [distribuito,](direct-routing-landing-page.md)è possibile usare i criteri per le chiamate di emergenza in Microsoft Teams per definire cosa succede quando un utente di Teams nell'organizzazione effettua una chiamata di emergenza. [](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="fc5b4-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="fc5b4-105">È possibile impostare gli utenti a cui inviare una notifica e la modalità di notifica quando un utente a cui è assegnato il criterio chiama i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="fc5b4-106">Ad esempio, è possibile configurare le impostazioni dei criteri per inviare automaticamente una notifica al desk di sicurezza dell'organizzazione e fare in modo che ascoltino le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="fc5b4-107">Per gestire i criteri per le chiamate di emergenza, è possibile accedere ai criteri di emergenza vocale nell'interfaccia di amministrazione di Microsoft Teams o usando  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="fc5b4-108">I criteri possono essere assegnati a utenti e [siti di rete.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fc5b4-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="fc5b4-109">Per gli utenti, è possibile usare i criteri globali (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="fc5b4-110">Gli utenti riceveranno automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="fc5b4-111">Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non è possibile rinominarlo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="fc5b4-112">Per i siti di rete, è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="fc5b4-113">Se sono stati assegnati criteri per le chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in tale sito di rete, i criteri assegnati al sito di rete sostituiscono i criteri assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="fc5b4-114">Creare criteri personalizzati per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="fc5b4-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc5b4-115">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fc5b4-116">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri di emergenza vocale e quindi fare clic  >  sulla scheda **Criteri chiamate.**</span><span class="sxs-lookup"><span data-stu-id="fc5b4-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="fc5b4-117">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-117">Click **Add**.</span></span>
3. <span data-ttu-id="fc5b4-118">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="fc5b4-119">Impostare la modalità di notifica alle persone dell'organizzazione, in genere il desk di sicurezza, quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="fc5b4-120">A questo scopo, in **Modalità di notifica** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc5b4-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="fc5b4-121">**Invia solo notifica:** agli utenti e ai gruppi specificati viene inviato un messaggio di chat di Teams.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="fc5b4-122">Conferenza con audio disattivato e non in grado di riattivare l'audio: un messaggio di chat di Teams viene inviato agli utenti e ai gruppi specificati dall'utente e può ascoltare (ma non partecipare) alla conversazione tra il **chiamante** e l'operatore PSAP.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="fc5b4-123">Conferenza con audio disattivato ma in grado di riattivare l'audio: viene inviato un messaggio di chat di Teams agli utenti e ai gruppi specificati e possono riattivare l'audio per ascoltare e partecipare alla conversazione tra il **chiamante** e l'operatore PSAP.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="fc5b4-124">Se è stata selezionata una delle modalità di  notifica Conferenza **in** modalità di notifica disattivata, nella casella Numeri da chiamare per le notifiche di emergenza è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="fc5b4-125">Ad esempio, immettere il numero del desk di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="fc5b4-126">Il telefono PSTN non può essere riattivato anche quando la modalità è impostata su Conferenza con audio disattivato, ma è possibile **riattivare l'audio.**</span><span class="sxs-lookup"><span data-stu-id="fc5b4-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="fc5b4-127">Cercare e selezionare uno o più utenti o gruppi, ad esempio il desk di sicurezza dell'organizzazione, per inviare una notifica quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="fc5b4-128">La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="fc5b4-129">È possibile ricevere una notifica a un massimo di 50 utenti.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="fc5b4-130">Fare clic **su Applica**.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc5b4-131">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5b4-131">Using PowerShell</span></span>

<span data-ttu-id="fc5b4-132">Vedere [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="fc5b4-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="fc5b4-133">Modificare i criteri per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="fc5b4-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc5b4-134">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="fc5b4-135">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="fc5b4-136">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri di emergenza vocale e quindi fare clic  >  sulla scheda **Criteri chiamate.**</span><span class="sxs-lookup"><span data-stu-id="fc5b4-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="fc5b4-137">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="fc5b4-138">Apportare le modifiche desiderate e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="fc5b4-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc5b4-139">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5b4-139">Using PowerShell</span></span>

<span data-ttu-id="fc5b4-140">Vedere [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="fc5b4-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="fc5b4-141">Assegnare un criterio personalizzato per le chiamate di emergenza agli utenti</span><span class="sxs-lookup"><span data-stu-id="fc5b4-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="fc5b4-142">Vedere anche [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="fc5b4-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="fc5b4-143">Assegnare un criterio personalizzato per le chiamate di emergenza a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="fc5b4-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="fc5b4-144">Usare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="fc5b4-145">L'esempio seguente mostra come assegnare un criterio denominato Contoso Emergency Calling Policy 1 al sito Site1.</span><span class="sxs-lookup"><span data-stu-id="fc5b4-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="fc5b4-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fc5b4-146">Related topics</span></span>

[<span data-ttu-id="fc5b4-147">Gestire i criteri di routing delle chiamate di emergenza in Teams</span><span class="sxs-lookup"><span data-stu-id="fc5b4-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="fc5b4-148">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="fc5b4-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="fc5b4-149">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="fc5b4-149">Assign policies to your users in Teams</span></span>](assign-policies.md)