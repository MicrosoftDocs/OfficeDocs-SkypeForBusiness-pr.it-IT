---
title: Gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire le impostazioni per le funzionalità di Skype for business nell'interfaccia di amministrazione di Microsoft teams.
ms.openlocfilehash: 7248d57c5a2efb49714bf9e43c4e367ef454bfd0
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739234"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="fb942-103">Gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb942-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="fb942-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="fb942-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="fb942-105">Come amministratore, l'interfaccia di amministrazione di Microsoft teams è la posizione in cui Gestisci le funzionalità di Skype for business per gli utenti di Skype for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb942-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="fb942-106">È possibile gestire le [impostazioni per l'organizzazione](#manage-skype-for-business-settings-for-your-organization) nella pagina **Skype for business** e le impostazioni [per singoli utenti](#manage-skype-for-business-settings-for-individual-users) nella scheda **Skype for business** delle pagine dei dettagli utente.</span><span class="sxs-lookup"><span data-stu-id="fb942-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="fb942-107">Verrà visualizzata solo la pagina **Skype for business** nell'interfaccia di amministrazione di Microsoft teams se la modalità di coesistenza per l'organizzazione non è impostata **solo su teams**.</span><span class="sxs-lookup"><span data-stu-id="fb942-107">You'll only see the **Skype for Business** page in the Microsoft Teams admin center if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="fb942-108">Analogamente, viene visualizzata solo la scheda **Skype for business** per un utente se la modalità di coesistenza dell'utente non è **solo teams**.</span><span class="sxs-lookup"><span data-stu-id="fb942-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="fb942-109">Per altre informazioni sulle modalità di coesistenza, vedere informazioni sui [team e sulla coesistenza e interoperabilità di Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e [impostare le impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fb942-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb942-110">Le impostazioni di Skype for business erano in precedenza nel **portale legacy** nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fb942-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fb942-111">Con la pensione del portale legacy, abbiamo migrato le impostazioni a queste nuove posizioni nell'interfaccia di amministrazione di teams per la gestione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="fb942-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="fb942-112">Gestire le impostazioni di Skype for business per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fb942-112">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="fb942-113">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **impostazioni a livello di organizzazione**  >  **Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="fb942-113">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="fb942-114">Da qui puoi configurare e gestire le notifiche di Skype meeting broadcast, Presence privacy e device mobile per tutti gli utenti di Skype for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb942-114">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="fb942-115">Trasmissione riunione Skype</span><span class="sxs-lookup"><span data-stu-id="fb942-115">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="fb942-116"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="fb942-116"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="fb942-117">Usare le impostazioni seguenti per gestire [Skype meeting broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb942-117">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni di Skype meeting broadcast nell'interfaccia di amministrazione":::

- <span data-ttu-id="fb942-119">**Skype meeting broadcasts**: attivare questa opzione per abilitare Skype meeting broadcast per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb942-119">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="fb942-120">Dopo aver abilitato questa funzionalità, è necessario [configurare la rete per Skype meeting broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span><span class="sxs-lookup"><span data-stu-id="fb942-120">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="fb942-121">**Vedere funzionalità di anteprima**: attivare questa opzione per ottenere l'accesso anticipato alle nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="fb942-121">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="fb942-122">Gli **organizzatori possono programmare riunioni anonime**: attivare questa opzione se si vuole consentire agli organizzatori di creare eventi broadcast che consentano a tutti gli utenti esterni all'organizzazione di partecipare senza dover eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fb942-122">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="fb942-123">**Registrare riunioni Skype meeting broadcast**: attivare questa opzione per consentire agli organizzatori e ai relatori di registrare riunioni.</span><span class="sxs-lookup"><span data-stu-id="fb942-123">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="fb942-124">**URL del supporto dell'helpdesk per i partecipanti**: immettere l'URL del supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di assistenza durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="fb942-124">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="fb942-125">Notifiche di presenza e per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="fb942-125">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="fb942-126"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="fb942-126"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="fb942-127">Usare le impostazioni seguenti per gestire le notifiche di privacy e dispositivi mobili di Skype for business nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb942-127">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione":::

#### <a name="presence"></a><span data-ttu-id="fb942-129">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="fb942-129">Presence</span></span>

<span data-ttu-id="fb942-130">Per impostazione predefinita, gli utenti di Skype for business nell'organizzazione possono vedere lo stato presenza, ad esempio disponibile, occupato o assente, di altri utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="fb942-130">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="fb942-131">Scegli una delle opzioni seguenti per impostare chi può vedere la presenza degli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="fb942-131">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="fb942-132">**Visualizza automaticamente le informazioni sulla presenza**: qualsiasi utente di Skype for business nell'organizzazione che non è stato aggiunto all'elenco **esterno** o **bloccato** dell'utente può vedere la presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fb942-132">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="fb942-133">**Visualizzare le informazioni sulla presenza solo ai contatti di un utente**: qualsiasi utente Skype for business nell'elenco contatti dell'utente che non è stato aggiunto all'elenco **esterno** o **bloccato** può vedere la presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fb942-133">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="fb942-134">Gli utenti possono eseguire l'override di questa impostazione in Skype for **Settings**business accedendo alle  >  **Opzioni degli strumenti**impostazioni  >  **Options**.</span><span class="sxs-lookup"><span data-stu-id="fb942-134">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="fb942-135">Notifiche per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="fb942-135">Mobile notifications</span></span>

<span data-ttu-id="fb942-136">Puoi impostare se gli utenti di Skype for business mobile ricevono avvisi sui messaggi istantanei in arrivo e in uscita, i messaggi della segreteria telefonica e le chiamate perse tramite un servizio di notifica push.</span><span class="sxs-lookup"><span data-stu-id="fb942-136">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="fb942-137">A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il servizio di **notifica push Microsoft**, il **servizio notifica push Apple**o entrambi.</span><span class="sxs-lookup"><span data-stu-id="fb942-137">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="fb942-138">Tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fb942-138">Keep the following in mind:</span></span>

- <span data-ttu-id="fb942-139">Se si disattivano le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio di Skype for business nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="fb942-139">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="fb942-140">Per impostazione predefinita, le notifiche push sono attivate.</span><span class="sxs-lookup"><span data-stu-id="fb942-140">By default, push notifications are turned on.</span></span> <span data-ttu-id="fb942-141">I singoli utenti possono disattivarli in Skype for business nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="fb942-141">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="fb942-142">Quando si disattivano le notifiche push, gli utenti non possono riattivarli.</span><span class="sxs-lookup"><span data-stu-id="fb942-142">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fb942-143">Microsoft usa altre società per comunicare in tempo reale le notifiche per dispositivi mobili Skype for business per gli utenti di Windows Phone, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="fb942-143">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="fb942-144">Vedere la presente [informativa sulla privacy](https://go.microsoft.com/fwlink/p/?linkid=247732).</span><span class="sxs-lookup"><span data-stu-id="fb942-144">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="fb942-145">Gestire le impostazioni di Skype for business per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="fb942-145">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="fb942-146"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="fb942-146"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="fb942-147">Per gestire le impostazioni di Skype for business per singoli utenti, nella barra di spostamento sinistra dell'interfaccia di amministrazione di teams, passa a **utenti**, fai clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli utente e quindi seleziona la scheda **impostazioni di Skype for business** . Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="fb942-147">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for business nella pagina dei dettagli utente":::

### <a name="external-access-settings"></a><span data-ttu-id="fb942-149">Impostazioni di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="fb942-149">External access settings</span></span>

<span data-ttu-id="fb942-150">È possibile consentire o bloccare selettivamente se un utente può comunicare con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb942-150">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="fb942-151">**Utenti Skype for business esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con utenti Skype for business in domini federati.</span><span class="sxs-lookup"><span data-stu-id="fb942-151">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="fb942-152">**Utenti Skype esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="fb942-152">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="fb942-153">Impostazioni riunione</span><span class="sxs-lookup"><span data-stu-id="fb942-153">Meeting settings</span></span>

<span data-ttu-id="fb942-154">È possibile configurare le impostazioni delle riunioni seguenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="fb942-154">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="fb942-155">**Audio & video**: scegliere una delle impostazioni audio e video seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb942-155">**Audio & video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="fb942-156">**Nessuno**: l'utente non può usare l'audio o il video.</span><span class="sxs-lookup"><span data-stu-id="fb942-156">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="fb942-157">**Solo audio**: l'utente può usare l'audio ma non il video.</span><span class="sxs-lookup"><span data-stu-id="fb942-157">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="fb942-158">**Audio e video**: l'utente può usare l'audio e il video.</span><span class="sxs-lookup"><span data-stu-id="fb942-158">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="fb942-159">**Audio e video (HD)**: l'utente può usare l'audio e il video ad alta definizione.</span><span class="sxs-lookup"><span data-stu-id="fb942-159">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="fb942-160">**Registrare conversazioni & riunioni**: attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.</span><span class="sxs-lookup"><span data-stu-id="fb942-160">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="fb942-161">**Conformità**: attivare questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="fb942-161">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
