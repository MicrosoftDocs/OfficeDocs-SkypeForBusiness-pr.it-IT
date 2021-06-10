---
title: Gestire i criteri dell'ID chiamante in Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri id chiamante in Microsoft Teams modificare o bloccare l'ID chiamante Teams utenti dell'organizzazione.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308375"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="611b0-103">Gestire i criteri dell'ID chiamante in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="611b0-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="611b0-104">Per impostare l'ID chiamante su un numero di telefono dell'account della risorsa e per impostare il nome della parte chiamante, usare i cmdlet di PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity nel modulo di PowerShell 2.3.1 o versione successiva di Teams.</span><span class="sxs-lookup"><span data-stu-id="611b0-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="611b0-105">Queste opzioni non sono attualmente disponibili nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="611b0-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="611b0-106">Per impostazione predefinita, quando Teams un utente effettua una chiamata a un telefono PSTN, il numero di telefono Teams'utente è visibile.</span><span class="sxs-lookup"><span data-stu-id="611b0-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="611b0-107">Allo stesso modo, quando un chiamante PSTN effettua una chiamata a un Teams utente, il numero di telefono del chiamante PSTN è visibile.</span><span class="sxs-lookup"><span data-stu-id="611b0-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="611b0-108">L'amministratore può usare i criteri per l'ID chiamante per modificare o bloccare l'ID chiamante (noto anche come ID linea chiamante).</span><span class="sxs-lookup"><span data-stu-id="611b0-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="611b0-109">È possibile usare i criteri id chiamante per visualizzare un numero di telefono alternativo per gli utenti di Teams dell'organizzazione, bloccare il numero di telefono in uscita, bloccare la visualizzazione di un numero in arrivo o impostare il nome della parte chiamante (CNAM).</span><span class="sxs-lookup"><span data-stu-id="611b0-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="611b0-110">Ad esempio, quando un utente effettua una chiamata, è possibile modificare l'ID chiamante in modo da visualizzare il numero di telefono principale e il nome della società dell'organizzazione invece del numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="611b0-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="611b0-111">Per gestire i criteri id chiamante, accedere **ai** criteri ID chiamante vocale  >   nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="611b0-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="611b0-112">È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="611b0-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="611b0-113">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="611b0-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="611b0-114">Creare criteri ID chiamante personalizzati</span><span class="sxs-lookup"><span data-stu-id="611b0-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="611b0-115">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Criteri  >  **ID chiamante vocale.**</span><span class="sxs-lookup"><span data-stu-id="611b0-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="611b0-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="611b0-116">Click **Add**.</span></span> <br>
<span data-ttu-id="611b0-117">![Screenshot della nuova pagina dei criteri per l'ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="611b0-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="611b0-118">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="611b0-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="611b0-119">Da qui scegliere le impostazioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="611b0-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="611b0-120">**Blocca ID chiamante in arrivo:** attiva questa impostazione per impedire la visualizzazione dell'ID chiamante delle chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="611b0-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="611b0-121">**Ignorare i criteri per l'ID** chiamante: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni nel criterio relativo alla visualizzazione o meno del numero ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="611b0-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="611b0-122">Questo significa che gli utenti possono scegliere se visualizzare l'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="611b0-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="611b0-123">Per altre informazioni, vedere [Controllo utente finale dell'ID chiamante in uscita.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)</span><span class="sxs-lookup"><span data-stu-id="611b0-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="611b0-124">**Sostituire l'ID chiamante con**: Impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="611b0-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="611b0-125">**Numero utente:** visualizza il numero dell'utente.</span><span class="sxs-lookup"><span data-stu-id="611b0-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="611b0-126">**Numero servizio:** consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="611b0-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="611b0-127">**Anonimo:** visualizza l'ID chiamante come anonimo.</span><span class="sxs-lookup"><span data-stu-id="611b0-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="611b0-128">**Sostituire l'ID chiamante con questo numero di servizio:** scegliere un numero di servizio per sostituire l'ID chiamante degli utenti.</span><span class="sxs-lookup"><span data-stu-id="611b0-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="611b0-129">Questa opzione è disponibile se è stato selezionato **Numero servizio** in Sostituisci **l'ID chiamante con**.</span><span class="sxs-lookup"><span data-stu-id="611b0-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="611b0-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="611b0-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="611b0-131">Modificare i criteri per l'ID chiamante</span><span class="sxs-lookup"><span data-stu-id="611b0-131">Edit a caller ID policy</span></span>

<span data-ttu-id="611b0-132">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="611b0-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="611b0-133">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Criteri  >  **ID chiamante vocale.**</span><span class="sxs-lookup"><span data-stu-id="611b0-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="611b0-134">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="611b0-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="611b0-135">Modificare le impostazioni desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="611b0-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="611b0-136">Assegnare criteri ID chiamante personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="611b0-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="611b0-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="611b0-137">Related topics</span></span>

[<span data-ttu-id="611b0-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="611b0-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="611b0-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="611b0-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="611b0-140">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="611b0-140">Assign policies to your users in Teams</span></span>](assign-policies.md)