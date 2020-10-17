---
title: Attivare o disattivare l'accesso Guest a Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
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
description: Informazioni su come attivare o disattivare la caratteristica di accesso guest in Microsoft teams come amministratore di Office 365.
ms.openlocfilehash: 54d7461e9e03cd22900e07aca7ad2d12712faab7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508063"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="460de-103">Attivare o disattivare l'accesso Guest a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="460de-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="460de-104">L'accesso guest è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="460de-104">By default, guest access is turned off.</span></span> <span data-ttu-id="460de-105">È necessario attivare l'accesso guest per i team prima che gli amministratori o i proprietari del team possano aggiungere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="460de-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="460de-106">Dopo aver attivato l'accesso guest, potrebbe essere necessario qualche ora affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="460de-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="460de-107">Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che l'accesso guest non sia stato attivato o che le impostazioni non siano ancora valide.</span><span class="sxs-lookup"><span data-stu-id="460de-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="460de-108">L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365, SharePoint e teams.</span><span class="sxs-lookup"><span data-stu-id="460de-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="460de-109">Per altre informazioni, vedere [collaborare con gli utenti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="460de-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="460de-110">Configurare l'accesso guest nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="460de-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="460de-111">Accedere all'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="460de-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="460de-112">Selezionare l'accesso Guest **delle impostazioni a livello di organizzazione**  >  **Guest access**.</span><span class="sxs-lookup"><span data-stu-id="460de-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="460de-113">Impostare **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="460de-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="460de-114">Consenti l'opzione di accesso Guest impostata su attivato</span><span class="sxs-lookup"><span data-stu-id="460de-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="460de-115">In **chiamate**, **riunioni**e **messaggistica** **selezionare attivato** o **disattivato** per ogni funzionalità, a seconda di cosa si vuole consentire agli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="460de-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="460de-116">**Effettuare chiamate private** : attivare **questa impostazione per consentire agli utenti** di effettuare chiamate peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="460de-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="460de-117">**Consenti video IP** -attivare questa impostazione per consentire agli utenti di **usare il video** nelle chiamate e nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="460de-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="460de-118">**Modalità di condivisione dello schermo** : questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="460de-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="460de-119">Attivare questa impostazione su **disabilitata** per rimuovere la possibilità per gli utenti di condividere i loro schermi in teams.</span><span class="sxs-lookup"><span data-stu-id="460de-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="460de-120">Attivare questa impostazione su **singola applicazione** per consentire la condivisione di singole applicazioni.</span><span class="sxs-lookup"><span data-stu-id="460de-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="460de-121">Attivare questa impostazione su **intero schermo** per consentire la condivisione completa dello schermo.</span><span class="sxs-lookup"><span data-stu-id="460de-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="460de-122">**Consenti riunione ora** : attivare **questa impostazione per consentire agli utenti** di usare la funzionalità incontra ora in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="460de-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="460de-123">**Modifica messaggi inviati** -attivare **questa impostazione per consentire agli utenti** di modificare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="460de-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="460de-124">**Gli utenti possono eliminare i messaggi inviati** : attivare **questa impostazione per consentire agli utenti** di eliminare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="460de-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="460de-125">**Chat** : attiva **questa impostazione per offrire agli utenti** la possibilità di usare la chat in teams.</span><span class="sxs-lookup"><span data-stu-id="460de-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="460de-126">**Usare giphy nelle conversazioni** : attivare **questa impostazione per consentire agli utenti** di usare giphy nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="460de-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="460de-127">Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati.</span><span class="sxs-lookup"><span data-stu-id="460de-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="460de-128">A ogni Giphy viene assegnata una valutazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="460de-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="460de-129">**Classificazione contenuto Giphy** -selezionare una classificazione nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="460de-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="460de-130">**Consenti tutto il contenuto** : gli utenti potranno inserire tutte le giphy in chat, indipendentemente dalla valutazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="460de-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="460de-131">**Moderato** : gli utenti potranno inserire giphy in chat, ma saranno limitati a moderatamente dal contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="460de-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="460de-132">**Strict** : gli utenti saranno in grado di inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="460de-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="460de-133">**Usare memi nelle conversazioni** -attivare **questa impostazione per consentire agli utenti** di usare i memi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="460de-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="460de-134">**Usare gli adesivi nelle conversazioni** : attivare questa **impostazione per consentire agli utenti** di usare gli adesivi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="460de-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Impostazioni delle autorizzazioni guest in teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="460de-136">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="460de-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="460de-137">Accesso esterno (federazione) e accesso guest</span><span class="sxs-lookup"><span data-stu-id="460de-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="460de-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="460de-138">See also</span></span>

[<span data-ttu-id="460de-139">Configurare la collaborazione sicura con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="460de-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="460de-140">Bloccare gli utenti Guest da un team specifico</span><span class="sxs-lookup"><span data-stu-id="460de-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="460de-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="460de-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)