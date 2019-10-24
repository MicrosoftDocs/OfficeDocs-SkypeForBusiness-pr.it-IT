---
title: Attivare o disattivare l'accesso Guest a Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Attivare o disattivare la funzionalità di accesso guest in Microsoft teams.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 186c83b82c396a21fe0098a561bcd4db13370140
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37571575"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="7154d-103">Attivare o disattivare l'accesso Guest a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7154d-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="7154d-104">L'amministratore di Office 365 deve abilitare la funzionalità Guest prima che l'utente o gli utenti dell'organizzazione (in particolare i proprietari del team) possano aggiungere Guest.</span><span class="sxs-lookup"><span data-stu-id="7154d-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="7154d-105">Le impostazioni Guest sono impostate in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7154d-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="7154d-106">Le modifiche possono essere effettive nell'organizzazione di Office 365 in 2 ore e 24 ore.</span><span class="sxs-lookup"><span data-stu-id="7154d-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="7154d-107">Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che la caratteristica Guest non sia stata abilitata o che le impostazioni non siano ancora valide.</span><span class="sxs-lookup"><span data-stu-id="7154d-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7154d-108">Per consentire l'esperienza completa della funzionalità di accesso guest, è importante comprendere la dipendenza dalle autorizzazioni principali tra Microsoft teams, Azure Active Directory e Office 365.</span><span class="sxs-lookup"><span data-stu-id="7154d-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="7154d-109">Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="7154d-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="7154d-110">Accesso guest e accesso esterno (Federazione)</span><span class="sxs-lookup"><span data-stu-id="7154d-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7154d-111">Configurare l'accesso guest nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7154d-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="7154d-112">Accedere all'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="7154d-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="7154d-113">Selezionare > **l'accesso Guest** **delle impostazioni a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="7154d-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="7154d-114">Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="7154d-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="7154d-115">Consenti l'opzione di accesso Guest impostata su attivato</span><span class="sxs-lookup"><span data-stu-id="7154d-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="7154d-116">Impostare i toggle in **chiamata**, **riunione**e **messaggistica** **su** attivato o **disattivato**, a seconda delle funzionalità che si desidera consentire agli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="7154d-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="7154d-117">**Effettuare chiamate private** : attivare **questa impostazione per consentire agli utenti** di effettuare chiamate peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7154d-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="7154d-118">**Consenti video IP** -attivare questa impostazione per consentire agli utenti di **usare il video** nelle chiamate e nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="7154d-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="7154d-119">**Modalità di condivisione dello schermo** : questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="7154d-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="7154d-120">Attivare questa impostazione su **disabilitata** per rimuovere la possibilità per gli utenti di condividere i loro schermi in teams.</span><span class="sxs-lookup"><span data-stu-id="7154d-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="7154d-121">Attivare questa impostazione su **singola applicazione** per consentire la condivisione di singole applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7154d-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="7154d-122">Attivare questa impostazione su **intero schermo** per consentire la condivisione completa dello schermo.</span><span class="sxs-lookup"><span data-stu-id="7154d-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="7154d-123">**Consenti riunione ora** : attivare **questa impostazione per consentire agli utenti** di usare la funzionalità incontra ora in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="7154d-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="7154d-124">**Modifica messaggi inviati** -attivare **questa impostazione per consentire agli utenti** di modificare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7154d-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="7154d-125">**Gli utenti possono eliminare i messaggi inviati** : attivare **questa impostazione per consentire agli utenti** di eliminare i messaggi inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7154d-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="7154d-126">**Chat** : attiva **questa impostazione per offrire agli utenti** la possibilità di usare la chat in teams.</span><span class="sxs-lookup"><span data-stu-id="7154d-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="7154d-127">**Usare giphy nelle conversazioni** : attivare **questa impostazione per consentire agli utenti** di usare giphy nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="7154d-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="7154d-128">Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati.</span><span class="sxs-lookup"><span data-stu-id="7154d-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="7154d-129">A ogni Giphy viene assegnata una valutazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="7154d-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="7154d-130">**Classificazione contenuto Giphy** -selezionare una classificazione nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="7154d-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="7154d-131">**Consenti tutto il contenuto** : gli utenti potranno inserire tutte le giphy in chat, indipendentemente dalla valutazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="7154d-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="7154d-132">**Moderato** : gli utenti potranno inserire giphy in chat, ma saranno limitati a moderatamente dal contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="7154d-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="7154d-133">**Strict** : gli utenti saranno in grado di inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.</span><span class="sxs-lookup"><span data-stu-id="7154d-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="7154d-134">**Usare memi nelle conversazioni** -attivare **questa impostazione per consentire agli utenti** di usare i memi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="7154d-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="7154d-135">**Usare gli adesivi nelle conversazioni** : attivare questa **impostazione per consentire agli utenti** di usare gli adesivi nelle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="7154d-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="7154d-136">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7154d-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="7154d-137">Usare PowerShell per attivare o disattivare l'accesso Guest</span><span class="sxs-lookup"><span data-stu-id="7154d-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="7154d-138">Scaricare il modulo di PowerShell per Skype for business online dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="7154d-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="7154d-139">Connettere una sessione di PowerShell all'endpoint di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="7154d-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="7154d-140">Controlla la configurazione e, `AllowGuestUser` se `$False`lo è, usa il cmdlet [set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) per impostarlo su `$True`.</span><span class="sxs-lookup"><span data-stu-id="7154d-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="7154d-141">È ora possibile avere utenti guest in teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7154d-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="7154d-142">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7154d-142">More information</span></span>

<span data-ttu-id="7154d-143">Guardare il video seguente per altre informazioni sull'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="7154d-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="7154d-144">Aggiunta di Guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7154d-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
