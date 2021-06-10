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
description: Informazioni su come usare e gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams per configurare i numeri di emergenza e specificare la modalità di instradamento delle chiamate di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096180"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="06960-103">Gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06960-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="06960-104">Se nell'organizzazione è stato distribuito [Sistema telefonico Routing](direct-routing-landing-page.md) diretto, è possibile usare i criteri di routing delle chiamate di emergenza in Microsoft Teams per configurare i numeri di emergenza e specificare la modalità di instradamento delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="06960-105">Un criterio di routing delle chiamate di emergenza determina se i servizi di emergenza migliorati sono abilitati per gli utenti a cui è assegnato il criterio, i numeri usati per chiamare i servizi di emergenza (ad esempio, il 911 negli Stati Uniti) e la modalità di instradamento delle chiamate ai servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="06960-106">Per gestire i criteri di routing delle chiamate di emergenza, è possibile accedere ai criteri di emergenza vocali nell'interfaccia di amministrazione di Microsoft Teams o usando  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06960-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="06960-107">I criteri possono essere assegnati a utenti e [siti di rete.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="06960-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="06960-108">Per gli utenti, è possibile usare i criteri globali (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="06960-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="06960-109">Gli utenti riceveranno automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="06960-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="06960-110">Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non è possibile rinominarlo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="06960-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="06960-111">Per i siti di rete, è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="06960-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="06960-112">Se è stato assegnato un criterio di routing delle chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce il criterio assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="06960-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="06960-113">Creare un criterio di routing delle chiamate di emergenza personalizzato</span><span class="sxs-lookup"><span data-stu-id="06960-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="06960-114">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06960-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="06960-115">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione, passare a Criteri di emergenza vocale e quindi fare  >  clic sulla scheda Criteri **routing chiamate.**</span><span class="sxs-lookup"><span data-stu-id="06960-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="06960-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="06960-116">Click **Add**.</span></span>
3. <span data-ttu-id="06960-117">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="06960-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="06960-118">Per abilitare le chiamate di emergenza dinamiche, attiva **Chiamate di emergenza dinamiche.**</span><span class="sxs-lookup"><span data-stu-id="06960-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="06960-119">Quando le chiamate di emergenza dinamiche sono abilitate, Teams recupera le informazioni sui criteri e sulla posizione dal servizio e le include come parte della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="06960-120">Definire uno o più numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="06960-121">A questo scopo, in **Numeri di emergenza** fare clic su **Aggiungi** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="06960-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="06960-122">**Stringa di chiamata di emergenza:** immettere la stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="06960-123">Questa stringa di chiamata indica che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="06960-124">Per il routing diretto, ci stiamo allontanando dai client Teams che inviano chiamate di emergenza con un "+" davanti alla stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="06960-125">Finché la transizione non viene completata, il modello di percorso vocale per la corrispondenza con una stringa di chiamata di emergenza deve verificare che sia stata trovata una corrispondenza per le stringhe che hanno e non hanno un "+" precedente, ad esempio 911 e +911.</span><span class="sxs-lookup"><span data-stu-id="06960-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="06960-126">Ad esempio, ^ \\ +?911 o .\*.</span><span class="sxs-lookup"><span data-stu-id="06960-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="06960-127">**Maschera di chiamata di emergenza:** per ogni numero di emergenza, è possibile specificare zero o più maschere di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="06960-128">Una maschera di chiamata è il numero che si vuole tradurre nel valore della stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="06960-129">In questo modo è possibile comporre numeri di emergenza alternativi e consentire comunque alla chiamata di raggiungere i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="06960-130">Ad esempio, si aggiunge 112 come maschera di chiamata di emergenza, che è il numero del servizio di emergenza per la maggior parte dell'Europa, e 911 come stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="06960-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="06960-131">Un Teams dall'Europa che sta visitando potrebbe non sapere che 911 è il numero di emergenza negli Stati Uniti e quando compone il 112, la chiamata viene effettuata al 911.</span><span class="sxs-lookup"><span data-stu-id="06960-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="06960-132">Per definire più maschere di chiamata, separare ogni valore con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="06960-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="06960-133">Ad esempio, 112;212.</span><span class="sxs-lookup"><span data-stu-id="06960-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="06960-134">**Record di utilizzo PSTN:** selezionare il record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="06960-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="06960-135">Il record di utilizzo PSTN viene usato per determinare quale percorso viene usato per instradare le chiamate di emergenza da parte di utenti autorizzati a usarle.</span><span class="sxs-lookup"><span data-stu-id="06960-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="06960-136">La route associata a questo utilizzo deve puntare a un trunk SIP (Session Initiation Protocol) dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di risposta per la sicurezza pubblica (PSAP) più vicino.</span><span class="sxs-lookup"><span data-stu-id="06960-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="06960-137">Le stringhe di chiamata e le maschere di chiamata devono essere univoche all'interno di un criterio.</span><span class="sxs-lookup"><span data-stu-id="06960-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="06960-138">Questo significa che per un criterio è possibile definire più numeri di emergenza ed è possibile impostare più maschere di chiamata per una stringa di chiamata, ma ogni stringa di chiamata e maschera di chiamata deve essere usata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="06960-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="06960-139">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="06960-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="06960-140">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="06960-140">Using PowerShell</span></span>

<span data-ttu-id="06960-141">Vedere [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="06960-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="06960-142">Modificare un criterio di routing delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="06960-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="06960-143">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06960-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="06960-144">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="06960-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="06960-145">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione, passare a Criteri di emergenza vocale e quindi fare  >  clic sulla scheda Criteri **routing chiamate.**</span><span class="sxs-lookup"><span data-stu-id="06960-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="06960-146">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="06960-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="06960-147">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="06960-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="06960-148">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="06960-148">Using PowerShell</span></span>

<span data-ttu-id="06960-149">Vedere [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="06960-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="06960-150">Assegnare un criterio di routing delle chiamate di emergenza personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="06960-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="06960-151">Vedere anche [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="06960-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="06960-152">Assegnare un criterio di routing delle chiamate di emergenza personalizzato a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="06960-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="06960-153">Usare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di routing delle chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="06960-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="06960-154">Questo esempio mostra come assegnare un criterio denominato Criterio routing chiamate di emergenza 1 al sito Sito1.</span><span class="sxs-lookup"><span data-stu-id="06960-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="06960-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="06960-155">Related topics</span></span>

[<span data-ttu-id="06960-156">Gestire i criteri per le chiamate di emergenza in Teams</span><span class="sxs-lookup"><span data-stu-id="06960-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="06960-157">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="06960-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="06960-158">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="06960-158">Assign policies to your users in Teams</span></span>](assign-policies.md)