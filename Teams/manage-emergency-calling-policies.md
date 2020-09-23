---
title: Gestire i criteri delle chiamate di emergenza in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come usare e gestire i criteri delle chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217667"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="18973-103">Gestire i criteri delle chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18973-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="18973-104">Se l'organizzazione usa i [piani di chiamata](set-up-calling-plans.md) o il [routing diretto del sistema telefonico](direct-routing-landing-page.md)distribuito, è possibile usare i criteri per le chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="18973-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="18973-105">Puoi impostare gli utenti a cui inviare una notifica e il modo in cui vengono informati quando un utente a cui viene assegnato il criterio chiama i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="18973-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="18973-106">Ad esempio, è possibile configurare le impostazioni dei criteri per comunicare automaticamente alla scrivania di sicurezza dell'organizzazione e farli ascoltare in chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="18973-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="18973-107">Puoi gestire i criteri delle chiamate di emergenza **Voice**passando ai  >  **criteri di emergenza** vocale nell'interfaccia di amministrazione di Microsoft teams oppure usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18973-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="18973-108">I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="18973-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="18973-109">Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="18973-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="18973-110">Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="18973-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="18973-111">Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle.</span><span class="sxs-lookup"><span data-stu-id="18973-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="18973-112">Per i siti di rete, è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="18973-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="18973-113">Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="18973-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="18973-114">Creare un criterio di chiamata di emergenza personalizzato</span><span class="sxs-lookup"><span data-stu-id="18973-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18973-115">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18973-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18973-116">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="18973-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="18973-117">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="18973-117">Click **Add**.</span></span>
3. <span data-ttu-id="18973-118">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="18973-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="18973-119">Impostare il modo in cui si vuole informare gli utenti dell'organizzazione, in genere il servizio di sicurezza, quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="18973-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="18973-120">A questo scopo, in **modalità notifica**selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="18973-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="18973-121">**Invia solo notifica**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati.</span><span class="sxs-lookup"><span data-stu-id="18973-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="18973-122">**In conferenza ma in sordina**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati, che possono ascoltare, ma non partecipare, nella conversazione tra il chiamante e l'operatore di PSAP.</span><span class="sxs-lookup"><span data-stu-id="18973-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="18973-123">**Conferenze in e sono riattivate** **(presto disponibile)**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati e possono riattivare l'audio per ascoltare e partecipare alla conversazione tra il chiamante e l'operatore di PSAP.</span><span class="sxs-lookup"><span data-stu-id="18973-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="18973-124">Se è stata selezionata la modalità di notifica **in conferenza ma è disattivata** , nella casella **numeri da chiamare per le chiamate di emergenza** è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="18973-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="18973-125">Ad esempio, immettere il numero del servizio di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="18973-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="18973-126">Cercare e selezionare uno o più utenti o gruppi, ad esempio il servizio di sicurezza dell'organizzazione, per avvisare quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="18973-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="18973-127">La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="18973-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="18973-128">Può essere notificato un massimo di 50 utenti.</span><span class="sxs-lookup"><span data-stu-id="18973-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="18973-129">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="18973-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="18973-130">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="18973-130">Using PowerShell</span></span>

<span data-ttu-id="18973-131">Vedere [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="18973-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="18973-132">Modificare un criterio per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="18973-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18973-133">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18973-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="18973-134">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="18973-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="18973-135">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="18973-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="18973-136">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="18973-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="18973-137">Apportare le modifiche desiderate e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="18973-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="18973-138">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="18973-138">Using PowerShell</span></span>

<span data-ttu-id="18973-139">Vedere [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="18973-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="18973-140">Assegnare un criterio di chiamata di emergenza personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="18973-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="18973-141">Vedere anche [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="18973-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="18973-142">Assegnare un criterio di chiamata di emergenza personalizzato a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="18973-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="18973-143">Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="18973-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="18973-144">L'esempio seguente mostra come assegnare un criterio denominato criteri di chiamata di emergenza contoso 1 al sito di Microsoft1.</span><span class="sxs-lookup"><span data-stu-id="18973-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="18973-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="18973-145">Related topics</span></span>

[<span data-ttu-id="18973-146">Gestire i criteri di routing delle chiamate di emergenza in teams</span><span class="sxs-lookup"><span data-stu-id="18973-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="18973-147">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="18973-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="18973-148">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="18973-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
