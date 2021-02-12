---
title: Gestire i criteri del routing delle chiamate di emergenza
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di instradamento delle chiamate di emergenza in Microsoft Teams per impostare i numeri di emergenza e specificare come instradare le chiamate di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804676"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="1500f-103">Gestire i criteri di instradamento delle chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1500f-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="1500f-104">Se hai implementato [](direct-routing-landing-page.md) l'instradamento diretto del sistema telefonico nella tua organizzazione, puoi utilizzare i criteri di instradamento delle chiamate di emergenza in Microsoft Teams per impostare i numeri di emergenza e specificare come instradare le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="1500f-105">I criteri di instradamento delle chiamate di emergenza determinano se i servizi di emergenza avanzato sono abilitati per gli utenti a cui è assegnato il criterio, i numeri utilizzati per chiamare i servizi di emergenza (ad esempio il 911 negli Stati Uniti) e la modalità di instradamento delle chiamate ai servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="1500f-106">Per gestire i criteri di instradamento delle chiamate di emergenza, è possibile accedere ai criteri per gli interventi di emergenza vocali nell'interfaccia di amministrazione di Microsoft Teams o tramite  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1500f-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="1500f-107">I criteri possono essere assegnati a utenti e siti [di rete.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1500f-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="1500f-108">Per gli utenti, è possibile usare il criterio globale (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1500f-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="1500f-109">Gli utenti riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1500f-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1500f-110">Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non rinominarlo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="1500f-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="1500f-111">Per i siti di rete è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1500f-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="1500f-112">Se è stato assegnato un criterio di instradamento delle chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in quel sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="1500f-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="1500f-113">Creare un criterio personalizzato per l'instradamento delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="1500f-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1500f-114">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1500f-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1500f-115">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Criteri di emergenza vocali, quindi fai clic  >  sulla scheda Criteri **di instradamento** chiamate.</span><span class="sxs-lookup"><span data-stu-id="1500f-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="1500f-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1500f-116">Click **Add**.</span></span>
3. <span data-ttu-id="1500f-117">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="1500f-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="1500f-118">Per abilitare le chiamate di emergenza dinamiche, attiva **chiamate di emergenza dinamiche.**</span><span class="sxs-lookup"><span data-stu-id="1500f-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="1500f-119">Quando sono abilitate le chiamate di emergenza dinamiche, Teams recupera le informazioni sulla posizione e sui criteri dal servizio e include queste informazioni nell'ambito della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="1500f-120">Definire uno o più numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="1500f-121">A tale scopo, in **Numeri di emergenza** fare clic su **Aggiungi** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1500f-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="1500f-122">**Stringa di composizione per gli interventi di** emergenza: immettere la stringa di composizione per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="1500f-123">Questa stringa di chiamata indica che si tratta di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="1500f-124">Per l'instradamento diretto, ci stiamo allontanando dai client di Teams per l'invio di chiamate di emergenza con un "+" davanti alla stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="1500f-125">Fino al completamento della transizione, il modello del percorso vocale che corrisponde a una stringa di composizione per gli interventi di emergenza deve garantire la corrispondenza per le stringhe che hanno e non hanno un segno "+" preceduto, ad esempio 911 e +911.</span><span class="sxs-lookup"><span data-stu-id="1500f-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="1500f-126">Ad esempio, ^ \\ +?911 o \*.</span><span class="sxs-lookup"><span data-stu-id="1500f-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="1500f-127">**Maschera per le chiamate di** emergenza: per ogni numero di emergenza, è possibile specificare zero o più maschere di composizione per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="1500f-128">Una maschera di composizione è il numero che si desidera tradurre nel valore della stringa di composizione per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="1500f-129">In questo modo è possibile comporre numeri di emergenza alternativi e fare in modo che la chiamata raggiunga i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="1500f-130">Ad esempio, si aggiunge il 112 come maschera per le chiamate di emergenza, ovvero il numero dei servizi di emergenza per gran parte dell'Europa, e il 911 come stringa di composizione per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="1500f-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="1500f-131">Un utente di Teams dall'Europa che sta visitando potrebbe non sapere che il 911 è il numero di emergenza negli Stati Uniti e, quando compone il 112, la chiamata viene effettuata al 911.</span><span class="sxs-lookup"><span data-stu-id="1500f-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="1500f-132">Per definire più maschere di chiamata, separare ogni valore con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="1500f-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="1500f-133">Ad esempio, 112;212.</span><span class="sxs-lookup"><span data-stu-id="1500f-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="1500f-134">**Record di utilizzo PSTN:** selezionare il record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="1500f-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="1500f-135">Il record di utilizzo PSTN viene usato per determinare quale percorso utilizzare per instradare le chiamate di emergenza da parte di utenti autorizzati a usarle.</span><span class="sxs-lookup"><span data-stu-id="1500f-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="1500f-136">Il percorso associato a questo utilizzo deve puntare a un trunk SIP (Session Initiation Protocol) dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al più vicino punto di risposta per la sicurezza pubblica (PSAP, Public Safety Answering Point).</span><span class="sxs-lookup"><span data-stu-id="1500f-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1500f-137">Le stringhe di composizione e le maschere di chiamata devono essere univoche all'interno di un criterio.</span><span class="sxs-lookup"><span data-stu-id="1500f-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="1500f-138">Questo significa che per un criterio è possibile definire più numeri di emergenza e impostare più maschere di chiamata per una stringa di composizione, ma ogni stringa di composizione e maschera di chiamata deve essere utilizzata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="1500f-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="1500f-139">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1500f-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1500f-140">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1500f-140">Using PowerShell</span></span>

<span data-ttu-id="1500f-141">Vedere [New-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="1500f-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="1500f-142">Modificare i criteri di instradamento delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="1500f-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1500f-143">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1500f-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1500f-144">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1500f-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="1500f-145">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Criteri di emergenza vocali, quindi fai clic  >  sulla scheda Criteri **di instradamento** chiamate.</span><span class="sxs-lookup"><span data-stu-id="1500f-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="1500f-146">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1500f-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1500f-147">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="1500f-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1500f-148">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1500f-148">Using PowerShell</span></span>

<span data-ttu-id="1500f-149">Vedere [Set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="1500f-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="1500f-150">Assegnare un criterio personalizzato per l'instradamento delle chiamate di emergenza agli utenti</span><span class="sxs-lookup"><span data-stu-id="1500f-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="1500f-151">Vedere anche [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="1500f-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="1500f-152">Assegnare criteri personalizzati per l'instradamento delle chiamate di emergenza a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="1500f-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="1500f-153">Usare il cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di instradamento per le chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="1500f-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="1500f-154">Questo esempio mostra come assegnare un criterio denominato Criterio di instradamento chiamate di emergenza 1 al sito Sito1.</span><span class="sxs-lookup"><span data-stu-id="1500f-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="1500f-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1500f-155">Related topics</span></span>

[<span data-ttu-id="1500f-156">Gestire i criteri per le chiamate di emergenza in Teams</span><span class="sxs-lookup"><span data-stu-id="1500f-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="1500f-157">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="1500f-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="1500f-158">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="1500f-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
