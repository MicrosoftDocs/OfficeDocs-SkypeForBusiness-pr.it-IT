---
title: Attivare o disattivare l'accesso Guest a Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Informazioni su come attivare o disattivare la caratteristica di accesso guest in Microsoft teams come amministratore di Office 365.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43965ef0b32551a9b4d5030b762d8fe0c53abcc4
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690052"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="949bb-103">Attivare o disattivare l'accesso Guest a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="949bb-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="949bb-104">L'accesso guest è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="949bb-104">By default, guest access is turned off.</span></span> <span data-ttu-id="949bb-105">Come amministratore di Microsoft 365 o Office 365, è necessario attivare l'accesso guest per i team prima che l'amministratore o i proprietari del team possano aggiungere Guest.</span><span class="sxs-lookup"><span data-stu-id="949bb-105">As the Microsoft 365 or Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="949bb-106">Per attivare l'accesso guest, usare l' [elenco di controllo di accesso Guest](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="949bb-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="949bb-107">Dopo aver attivato l'accesso guest, potrebbe essere necessario qualche ora affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="949bb-107">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="949bb-108">Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che l'accesso guest non sia stato attivato o che le impostazioni non siano ancora valide.</span><span class="sxs-lookup"><span data-stu-id="949bb-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="949bb-109">L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365 o Office 365, SharePoint Online e teams.</span><span class="sxs-lookup"><span data-stu-id="949bb-109">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365 or Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="949bb-110">Per altre informazioni, vedere [autorizzare l'accesso guest in teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="949bb-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="949bb-111">Configurare l'accesso guest nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="949bb-111">Configure guest access in the Teams admin center</span></span>

1.    <span data-ttu-id="949bb-112">Accedere all'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="949bb-112">Sign in to the Microsoft Teams admin center.</span></span>

2.    <span data-ttu-id="949bb-113">Selezionare l'accesso Guest **delle impostazioni a livello di organizzazione**  >  **Guest access**.</span><span class="sxs-lookup"><span data-stu-id="949bb-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="949bb-114">Impostare **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="949bb-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="949bb-115">Consenti l'opzione di accesso Guest impostata su attivato</span><span class="sxs-lookup"><span data-stu-id="949bb-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.    <span data-ttu-id="949bb-116">In **chiamate**, **riunioni**e **messaggistica** **selezionare attivato** o **disattivato** per ogni funzionalità, a seconda di cosa si vuole consentire agli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="949bb-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

    - <span data-ttu-id="949bb-117">**Effettuare chiamate private** : attivare **questa impostazione per consentire agli utenti** di effettuare chiamate peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="949bb-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="949bb-118">**Consenti video IP** -attivare questa impostazione per consentire agli utenti di **usare il video** nelle chiamate e nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="949bb-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="949bb-119">**Modalità di condivisione dello schermo** : questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="949bb-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="949bb-120">Attivare questa impostazione su **disabilitata** per rimuovere la possibilità per gli utenti di condividere i loro schermi in teams.</span><span class="sxs-lookup"><span data-stu-id="949bb-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="949bb-121">Attivare questa impostazione su **singola applicazione** per consentire la condivisione di singole applicazioni.</span><span class="sxs-lookup"><span data-stu-id="949bb-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="949bb-122">Attivare questa impostazione su **intero schermo** per consentire la condivisione completa dello schermo.</span><span class="sxs-lookup"><span data-stu-id="949bb-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="949bb-123">**Consenti riunione ora** : attivare **questa impostazione per consentire agli utenti** di usare la funzionalità incontra ora in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="949bb-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="949bb-124">**Modifica messaggi inviati** -attivare **questa impostazione per consentire agli utenti** di modificare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="949bb-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="949bb-125">**Gli utenti possono eliminare i messaggi inviati** : attivare **questa impostazione per consentire agli utenti** di eliminare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="949bb-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="949bb-126">**Chat** : attiva **questa impostazione per offrire agli utenti** la possibilità di usare la chat in teams.</span><span class="sxs-lookup"><span data-stu-id="949bb-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="949bb-127">**Usare giphy nelle conversazioni** : attivare **questa impostazione per consentire agli utenti** di usare giphy nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="949bb-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="949bb-128">Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati.</span><span class="sxs-lookup"><span data-stu-id="949bb-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="949bb-129">A ogni Giphy viene assegnata una valutazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="949bb-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="949bb-130">**Classificazione contenuto Giphy** -selezionare una classificazione nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="949bb-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="949bb-131">**Consenti tutto il contenuto** : gli utenti potranno inserire tutte le giphy in chat, indipendentemente dalla valutazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="949bb-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="949bb-132">**Moderato** : gli utenti potranno inserire giphy in chat, ma saranno limitati a moderatamente dal contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="949bb-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="949bb-133">**Strict** : gli utenti saranno in grado di inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="949bb-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="949bb-134">**Usare memi nelle conversazioni** -attivare **questa impostazione per consentire agli utenti** di usare i memi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="949bb-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="949bb-135">**Usare gli adesivi nelle conversazioni** : attivare questa **impostazione per consentire agli utenti** di usare gli adesivi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="949bb-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.    <span data-ttu-id="949bb-136">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="949bb-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="949bb-137">Usare PowerShell per attivare o disattivare l'accesso Guest</span><span class="sxs-lookup"><span data-stu-id="949bb-137">Use PowerShell to turn guest access on or off</span></span>
<span data-ttu-id="949bb-138">Leggere [usare PowerShell per attivare o disattivare l'accesso Guest](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="949bb-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="949bb-139">Video: aggiunta di Guest in teams</span><span class="sxs-lookup"><span data-stu-id="949bb-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="949bb-140">Aggiunta di Guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="949bb-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="949bb-141">Accesso esterno (federazione) e accesso guest</span><span class="sxs-lookup"><span data-stu-id="949bb-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]