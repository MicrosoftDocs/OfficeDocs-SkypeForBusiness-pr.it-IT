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
ms.openlocfilehash: aaf37fda456f0e48d441e78f785a3ce450f1f42c
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786778"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="b73eb-103">Attivare o disattivare l'accesso guest in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b73eb-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="b73eb-104">Fino al **febbraio 2021**, l'accesso Guest è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b73eb-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="b73eb-105">È necessario attivare l'accesso guest per Teams prima che gli amministratori o i proprietari del team possano aggiungere guest.</span><span class="sxs-lookup"><span data-stu-id="b73eb-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="b73eb-106">Dopo aver attivato l'accesso guest, potrebbe essere necessario qualche ora affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="b73eb-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="b73eb-107">Se gli utenti vedono il messaggio **contattare l'amministratore** quando tentano di aggiungere un Guest al proprio team, è probabile che l'accesso guest non sia stato attivato o che le impostazioni non siano ancora valide.</span><span class="sxs-lookup"><span data-stu-id="b73eb-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span> 

> <span data-ttu-id="b73eb-108">Dopo il **2021 febbraio**, l'accesso guest in Microsoft teams sarà attivato per impostazione predefinita per i nuovi clienti & clienti esistenti che non hanno configurato questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="b73eb-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="b73eb-109">Quando questa modifica viene implementata, se non è già stata configurata la funzionalità di accesso guest in Microsoft teams, tale funzionalità verrà abilitata nel tenant.</span><span class="sxs-lookup"><span data-stu-id="b73eb-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="b73eb-110">Se si vuole che l'accesso Guest rimanga disabilitato per l'organizzazione, è necessario verificare che l'impostazione di accesso Guest sia impostata su **disattivato** al posto del **servizio predefinito**.</span><span class="sxs-lookup"><span data-stu-id="b73eb-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b73eb-111">L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365, SharePoint e Teams.</span><span class="sxs-lookup"><span data-stu-id="b73eb-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="b73eb-112">Per maggiori informazioni, vedere [Collaborare con gli utenti guest in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="b73eb-112">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="b73eb-113">Configurare l'accesso guest nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="b73eb-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="b73eb-114">Accedere all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b73eb-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="b73eb-115">Selezionare **Impostazioni a livello di organizzazione** > **Accesso guest**.</span><span class="sxs-lookup"><span data-stu-id="b73eb-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="b73eb-116">Impostare **Consenti accesso guest in Microsoft Teams** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="b73eb-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="b73eb-117">Consenti accesso guest impostato su Attivato</span><span class="sxs-lookup"><span data-stu-id="b73eb-117">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="b73eb-118">In **Chiamata**, **Riunione**, and **Messaggistica**, selezionare **Attivato** o **Disattivato** per ciascuna funzionalità, a seconda di ciò che si desidera consentire agli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="b73eb-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="b73eb-119">**Effettua chiamate private**: passare questa impostazione su **Attivato** per consentire agli utenti guest di effettuare chiamate peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b73eb-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="b73eb-120">**Consenti video IP**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare il video durante le chiamate e le riunioni.</span><span class="sxs-lookup"><span data-stu-id="b73eb-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="b73eb-121">**Modalità condivisione dello schermo**: questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="b73eb-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="b73eb-122">Passare questa impostazione su **Disattivato** per rimuovere la possibilità agli utenti guest di condividere i propri schermi in Teams.</span><span class="sxs-lookup"><span data-stu-id="b73eb-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="b73eb-123">Passare questa impostazione su **Singola applicazione** per consentire la condivisione di singole applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b73eb-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="b73eb-124">Passare questa impostazione su **Schermo interno** per consentire la condivisione dello schermo completa.</span><span class="sxs-lookup"><span data-stu-id="b73eb-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="b73eb-125">**Consenti Riunione immediata**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare la funzionalità Riunione immediata in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b73eb-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="b73eb-126">**Modifica messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di modificare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b73eb-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="b73eb-127">**Gli utenti guest possono eliminare i messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di eliminare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b73eb-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="b73eb-128">**Chat**: passare questa impostazione su **Attivato** per dare agli utenti guest la possibilità di usare la chat in Teams.</span><span class="sxs-lookup"><span data-stu-id="b73eb-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="b73eb-129">**Usa Giphys nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare Giphy nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="b73eb-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="b73eb-130">Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati.</span><span class="sxs-lookup"><span data-stu-id="b73eb-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="b73eb-131">A ogni Giphy viene assegnata una classificazione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="b73eb-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="b73eb-132">**Classificazione contenuti Giphy**: selezionare una classificazione dall’elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="b73eb-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="b73eb-133">**Consenti tutti i contenuti**: gli utenti guest potranno inserire tutti i contenuti Giphy nelle chat, indipendentemente dalla loro classificazione.</span><span class="sxs-lookup"><span data-stu-id="b73eb-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="b73eb-134">**Moderato**: gli utenti guest potranno inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno moderatamente limitati.</span><span class="sxs-lookup"><span data-stu-id="b73eb-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="b73eb-135">**Strict** : gli utenti possono inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="b73eb-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="b73eb-136">**Usa meme nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare meme nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="b73eb-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="b73eb-137">**Usa adesivi nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare adesivi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="b73eb-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Impostazioni autorizzazioni guest in Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="b73eb-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b73eb-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="b73eb-140">Accesso esterno (federazione) e accesso guest</span><span class="sxs-lookup"><span data-stu-id="b73eb-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="b73eb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b73eb-141">See also</span></span>

[<span data-ttu-id="b73eb-142">Configurare la collaborazione sicura con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b73eb-142">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="b73eb-143">Bloccare gli utenti guest di un team specifico</span><span class="sxs-lookup"><span data-stu-id="b73eb-143">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="b73eb-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="b73eb-144">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
