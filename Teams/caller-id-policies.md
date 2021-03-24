---
title: Gestire i criteri dell'ID chiamante in Microsoft Teams
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
description: Informazioni su come usare e gestire i criteri id chiamante in Microsoft Teams per modificare o bloccare l'ID chiamante degli utenti di Teams nell'organizzazione.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102782"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="3da31-103">Gestire i criteri dell'ID chiamante in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3da31-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="3da31-104">Gli amministratori possono usare i criteri id chiamante in Microsoft Teams per modificare o bloccare l'ID chiamante (noto anche come ID linea chiamante).</span><span class="sxs-lookup"><span data-stu-id="3da31-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="3da31-105">Per impostazione predefinita, il numero di telefono degli utenti di Teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono di chiamanti PSTN può essere visualizzato quando chiamano un utente di Teams.</span><span class="sxs-lookup"><span data-stu-id="3da31-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="3da31-106">È possibile usare i criteri id chiamante per visualizzare un numero di telefono alternativo per gli utenti di Teams nell'organizzazione o per impedire la visualizzazione di un numero in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3da31-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="3da31-107">Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante in modo da visualizzare il numero di telefono principale dell'organizzazione invece dei numeri di telefono degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3da31-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="3da31-108">Per gestire i criteri id chiamante, accedere **ai** criteri  >  **ID chiamante vocale** nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3da31-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3da31-109">È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3da31-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="3da31-110">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3da31-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="3da31-111">Creare criteri ID chiamante personalizzati</span><span class="sxs-lookup"><span data-stu-id="3da31-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="3da31-112">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri  >  **ID chiamante vocale.**</span><span class="sxs-lookup"><span data-stu-id="3da31-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="3da31-113">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3da31-113">Click **Add**.</span></span> <br>
<span data-ttu-id="3da31-114">![Screenshot della nuova pagina dei criteri per l'ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="3da31-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="3da31-115">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3da31-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="3da31-116">Da qui scegliere le impostazioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="3da31-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="3da31-117">**Blocca ID chiamante in arrivo:** attiva questa impostazione per impedire la visualizzazione dell'ID chiamante delle chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3da31-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="3da31-118">**Ignorare i criteri per l'ID** chiamante: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni nel criterio relativo alla visualizzazione o meno del numero ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="3da31-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="3da31-119">Questo significa che gli utenti possono scegliere se visualizzare l'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="3da31-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="3da31-120">Per altre informazioni, vedere [Controllo utente finale dell'ID chiamante in uscita.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)</span><span class="sxs-lookup"><span data-stu-id="3da31-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="3da31-121">**Sostituire l'ID chiamante con**: Impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3da31-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="3da31-122">**Numero utente:** visualizza il numero dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3da31-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="3da31-123">**Numero servizio:** consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="3da31-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="3da31-124">**Anonimo:** visualizza l'ID chiamante come anonimo.</span><span class="sxs-lookup"><span data-stu-id="3da31-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="3da31-125">**Sostituire l'ID chiamante con questo numero di servizio:** scegliere un numero di servizio per sostituire l'ID chiamante degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3da31-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="3da31-126">Questa opzione è disponibile se è stato selezionato **Numero servizio** in Sostituisci **l'ID chiamante con**.</span><span class="sxs-lookup"><span data-stu-id="3da31-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="3da31-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3da31-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="3da31-128">Modificare i criteri per l'ID chiamante</span><span class="sxs-lookup"><span data-stu-id="3da31-128">Edit a caller ID policy</span></span>

<span data-ttu-id="3da31-129">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3da31-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="3da31-130">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri  >  **ID chiamante vocale.**</span><span class="sxs-lookup"><span data-stu-id="3da31-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="3da31-131">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3da31-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3da31-132">Modificare le impostazioni desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="3da31-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="3da31-133">Assegnare criteri ID chiamante personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="3da31-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="3da31-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3da31-134">Related topics</span></span>

[<span data-ttu-id="3da31-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="3da31-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="3da31-136">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="3da31-136">Assign policies to your users in Teams</span></span>](assign-policies.md)