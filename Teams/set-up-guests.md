---
title: Attivare o disattivare l'accesso guest in Microsoft Teams.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Informazioni su come gli amministratori di Office 365 possono attivare o disattivare la funzionalità di accesso guest in Microsoft Teams.
ms.openlocfilehash: 0920e9d8b8184f7f7ca83a71f0bd97d3a4d78470
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031192"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="d593e-103">Attivare o disattivare l'accesso guest in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d593e-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="d593e-104">L'accesso guest è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d593e-104">By default, guest access is turned off.</span></span> <span data-ttu-id="d593e-105">È necessario attivare l'accesso guest per Teams prima che gli amministratori o i proprietari del team possano aggiungere guest.</span><span class="sxs-lookup"><span data-stu-id="d593e-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="d593e-106">Dopo aver attivato l'accesso guest, potrebbero essere necessarie alcune ore prima che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="d593e-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="d593e-107">Se un utente visualizza il messaggio "Contatta l'amministratore" quando tenta di aggiungere un utente guest al proprio team, è probabile che l'accesso non sia stato attivato o che le impostazioni non siano ancora effettive.</span><span class="sxs-lookup"><span data-stu-id="d593e-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d593e-108">L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365, SharePoint e Teams.</span><span class="sxs-lookup"><span data-stu-id="d593e-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="d593e-109">Per maggiori informazioni, vedere [Collaborare con gli utenti guest in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="d593e-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="d593e-110">Configurare l'accesso guest nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="d593e-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="d593e-111">Accedere all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d593e-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="d593e-112">Selezionare **Impostazioni a livello di organizzazione** > **Accesso guest**.</span><span class="sxs-lookup"><span data-stu-id="d593e-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="d593e-113">Impostare **Consenti accesso guest in Microsoft Teams** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="d593e-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="d593e-114">Consenti accesso guest impostato su Attivato</span><span class="sxs-lookup"><span data-stu-id="d593e-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="d593e-115">In **Chiamata**, **Riunione**, and **Messaggistica**, selezionare **Attivato** o **Disattivato** per ciascuna funzionalità, a seconda di ciò che si desidera consentire agli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="d593e-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="d593e-116">**Effettua chiamate private**: passare questa impostazione su **Attivato** per consentire agli utenti guest di effettuare chiamate peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="d593e-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="d593e-117">**Consenti video IP**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare il video durante le chiamate e le riunioni.</span><span class="sxs-lookup"><span data-stu-id="d593e-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="d593e-118">**Modalità condivisione dello schermo**: questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="d593e-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="d593e-119">Passare questa impostazione su **Disattivato** per rimuovere la possibilità agli utenti guest di condividere i propri schermi in Teams.</span><span class="sxs-lookup"><span data-stu-id="d593e-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="d593e-120">Passare questa impostazione su **Singola applicazione** per consentire la condivisione di singole applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d593e-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="d593e-121">Passare questa impostazione su **Schermo interno** per consentire la condivisione dello schermo completa.</span><span class="sxs-lookup"><span data-stu-id="d593e-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="d593e-122">**Consenti Riunione immediata**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare la funzionalità Riunione immediata in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d593e-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="d593e-123">**Modifica messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di modificare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d593e-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="d593e-124">**Gli utenti guest possono eliminare i messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di eliminare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d593e-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="d593e-125">**Chat**: passare questa impostazione su **Attivato** per dare agli utenti guest la possibilità di usare la chat in Teams.</span><span class="sxs-lookup"><span data-stu-id="d593e-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="d593e-126">**Usa Giphys nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare Giphy nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="d593e-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="d593e-127">Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati.</span><span class="sxs-lookup"><span data-stu-id="d593e-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="d593e-128">A ogni Giphy viene assegnata una classificazione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="d593e-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="d593e-129">**Classificazione contenuti Giphy**: selezionare una classificazione dall’elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="d593e-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="d593e-130">**Consenti tutti i contenuti**: gli utenti guest potranno inserire tutti i contenuti Giphy nelle chat, indipendentemente dalla loro classificazione.</span><span class="sxs-lookup"><span data-stu-id="d593e-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="d593e-131">**Moderato**: gli utenti guest potranno inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno moderatamente limitati.</span><span class="sxs-lookup"><span data-stu-id="d593e-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="d593e-132">**Rigido**: gli utenti guest potranno inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno vietati.</span><span class="sxs-lookup"><span data-stu-id="d593e-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="d593e-133">**Usa meme nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare meme nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="d593e-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="d593e-134">**Usa adesivi nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare adesivi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="d593e-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Impostazioni autorizzazioni guest in Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="d593e-136">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d593e-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="d593e-137">Accesso esterno (federazione) e accesso guest</span><span class="sxs-lookup"><span data-stu-id="d593e-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="d593e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d593e-138">See also</span></span>

[<span data-ttu-id="d593e-139">Configurare la collaborazione sicura con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d593e-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="d593e-140">Bloccare gli utenti guest di un team specifico</span><span class="sxs-lookup"><span data-stu-id="d593e-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="d593e-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="d593e-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
