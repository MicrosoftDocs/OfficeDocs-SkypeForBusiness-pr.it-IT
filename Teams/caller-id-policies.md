---
title: Gestire i criteri di ID chiamante in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
description: Informazioni su come usare e gestire i criteri di ID chiamante in Microsoft teams per modificare o bloccare l'ID chiamante degli utenti di teams nell'organizzazione.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255529"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="e094a-103">Gestire i criteri di ID chiamante in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e094a-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="e094a-104">Come amministratore, puoi usare i criteri di ID chiamante in Microsoft teams per cambiare o bloccare l'ID chiamante (noto anche come ID linea chiamante).</span><span class="sxs-lookup"><span data-stu-id="e094a-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="e094a-105">Per impostazione predefinita, il numero di telefono degli utenti di teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono dei chiamanti PSTN può essere visualizzato quando chiamano un utente di teams.</span><span class="sxs-lookup"><span data-stu-id="e094a-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="e094a-106">Puoi usare i criteri ID chiamante per visualizzare un numero di telefono alternativo per gli utenti di team dell'organizzazione o bloccare un numero in arrivo.</span><span class="sxs-lookup"><span data-stu-id="e094a-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="e094a-107">Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante per visualizzare il numero di telefono principale dell'organizzazione anziché i numeri di telefono degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e094a-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="e094a-108">Puoi gestire i criteri ID chiamante accedendo **Voice**ai  >  **criteri ID chiamante** vocale nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e094a-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e094a-109">Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e094a-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e094a-110">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e094a-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="e094a-111">Creare un criterio ID chiamante personalizzato</span><span class="sxs-lookup"><span data-stu-id="e094a-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="e094a-112">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **criteri ID chiamante**vocale.</span><span class="sxs-lookup"><span data-stu-id="e094a-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e094a-113">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e094a-113">Click **Add**.</span></span> <br>
<span data-ttu-id="e094a-114">![Screenshot della nuova pagina dei criteri ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e094a-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="e094a-115">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e094a-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e094a-116">Da qui scegliere le impostazioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="e094a-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="e094a-117">**Bloccare l'ID chiamante in arrivo**: attivare questa impostazione per bloccare l'ID chiamante delle chiamate in arrivo dalla visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="e094a-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="e094a-118">**Eseguire l'override dei criteri ID chiamante**: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni dei criteri relativi alla visualizzazione del loro numero per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="e094a-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="e094a-119">Ciò significa che gli utenti possono scegliere se visualizzare l'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="e094a-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="e094a-120">Per altre informazioni, vedere [controllo dell'utente finale dell'ID chiamante in uscita](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="e094a-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="e094a-121">**Sostituire l'ID chiamante con**: impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e094a-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="e094a-122">**Numero dell'utente**: Visualizza il numero dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e094a-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="e094a-123">**Numero di servizio**: consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="e094a-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="e094a-124">**Anonymous**: Visualizza l'ID chiamante come anonimo.</span><span class="sxs-lookup"><span data-stu-id="e094a-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="e094a-125">**Sostituire l'ID chiamante con questo numero di servizio**: scegliere un numero di servizio per sostituire l'ID chiamante degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e094a-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="e094a-126">Questa opzione è disponibile se è **stato selezionato numero di servizio** in **Sostituisci l'ID chiamante con**.</span><span class="sxs-lookup"><span data-stu-id="e094a-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="e094a-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e094a-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="e094a-128">Modificare un criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="e094a-128">Edit a caller ID policy</span></span>

<span data-ttu-id="e094a-129">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="e094a-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="e094a-130">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **criteri ID chiamante**vocale.</span><span class="sxs-lookup"><span data-stu-id="e094a-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e094a-131">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="e094a-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e094a-132">Modificare le impostazioni desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e094a-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="e094a-133">Assegnare un criterio ID chiamante personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="e094a-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="e094a-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e094a-134">Related topics</span></span>

[<span data-ttu-id="e094a-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="e094a-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="e094a-136">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="e094a-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
