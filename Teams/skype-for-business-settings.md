---
title: Gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834216"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7fc64-103">Gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7fc64-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7fc64-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="7fc64-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="7fc64-105">Come amministratore, l'interfaccia di amministrazione di Microsoft teams è la posizione in cui Gestisci le funzionalità di Skype for business per gli utenti di Skype for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="7fc64-106">È possibile gestire le [impostazioni per l'organizzazione](#manage-skype-for-business-settings-for-your-organization) nella pagina **Skype for business** e le impostazioni [per singoli utenti](#manage-skype-for-business-settings-for-individual-users) nella scheda **Skype for business** delle pagine dei dettagli utente.</span><span class="sxs-lookup"><span data-stu-id="7fc64-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="7fc64-107">Verrà visualizzata solo la pagina **Skype for business** se la modalità di coesistenza per l'organizzazione non è impostata **solo su teams**.</span><span class="sxs-lookup"><span data-stu-id="7fc64-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="7fc64-108">Analogamente, viene visualizzata solo la scheda **Skype for business** per un utente se la modalità di coesistenza dell'utente non è **solo teams**.</span><span class="sxs-lookup"><span data-stu-id="7fc64-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="7fc64-109">Per altre informazioni sulle modalità di coesistenza, vedere informazioni sui [team e sulla coesistenza e interoperabilità di Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e [impostare le impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7fc64-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7fc64-110">Le impostazioni di Skype for business erano in precedenza nel **portale legacy** nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="7fc64-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7fc64-111">Con la pensione del portale legacy, abbiamo migrato le impostazioni a queste nuove posizioni nell'interfaccia di amministrazione di teams per la gestione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7fc64-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="7fc64-112">Per gestire le funzionalità di Skype for business nell'interfaccia di amministrazione di Microsoft teams, è necessario avere il [ruolo di amministratore di Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) per l'amministratore globale o per l'amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7fc64-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="7fc64-113">Gestire le impostazioni di Skype for business per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7fc64-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="7fc64-114">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **impostazioni a livello di organizzazione**  >  **Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="7fc64-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="7fc64-115">Da qui puoi configurare e gestire le notifiche di Skype meeting broadcast, Presence privacy e device mobile per tutti gli utenti di Skype for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="7fc64-116">Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="7fc64-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7fc64-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="7fc64-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="7fc64-118">Usare le impostazioni seguenti per gestire [Skype meeting broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni di Skype meeting broadcast nell'interfaccia di amministrazione":::

- <span data-ttu-id="7fc64-120">**Skype meeting broadcasts**: attivare questa opzione per abilitare Skype meeting broadcast per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="7fc64-121">Dopo aver abilitato questa funzionalità, è necessario [configurare la rete per Skype meeting broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span><span class="sxs-lookup"><span data-stu-id="7fc64-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="7fc64-122">**Vedere funzionalità di anteprima**: attivare questa opzione per ottenere l'accesso anticipato alle nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7fc64-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="7fc64-123">Gli **organizzatori possono programmare riunioni anonime**: attivare questa opzione se si vuole consentire agli organizzatori di creare eventi broadcast che consentano a tutti gli utenti esterni all'organizzazione di partecipare senza dover eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7fc64-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="7fc64-124">**Registrare riunioni Skype meeting broadcast**: attivare questa opzione per consentire agli organizzatori e ai relatori di registrare riunioni.</span><span class="sxs-lookup"><span data-stu-id="7fc64-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="7fc64-125">**URL del supporto dell'helpdesk per i partecipanti**: immettere l'URL del supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di assistenza durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="7fc64-126">Notifiche di presenza e per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7fc64-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7fc64-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="7fc64-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="7fc64-128">Usare le impostazioni seguenti per gestire le notifiche di privacy e dispositivi mobili di Skype for business nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione":::

#### <a name="presence"></a><span data-ttu-id="7fc64-130">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="7fc64-130">Presence</span></span>

<span data-ttu-id="7fc64-131">Per impostazione predefinita, gli utenti di Skype for business nell'organizzazione possono vedere lo stato presenza, ad esempio disponibile, occupato o assente, di altri utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7fc64-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="7fc64-132">Scegli una delle opzioni seguenti per impostare chi può vedere la presenza degli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7fc64-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="7fc64-133">**Visualizza automaticamente le informazioni sulla presenza**: qualsiasi utente di Skype for business nell'organizzazione che non è stato aggiunto all'elenco **esterno** o **bloccato** dell'utente può vedere la presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7fc64-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="7fc64-134">**Visualizzare le informazioni sulla presenza solo ai contatti di un utente**: qualsiasi utente Skype for business nell'elenco contatti dell'utente che non è stato aggiunto all'elenco **esterno** o **bloccato** può vedere la presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7fc64-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="7fc64-135">Gli utenti possono eseguire l'override di questa impostazione in Skype for business accedendo alle  >  **Opzioni degli strumenti** impostazioni  >  .</span><span class="sxs-lookup"><span data-stu-id="7fc64-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="7fc64-136">Notifiche per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7fc64-136">Mobile notifications</span></span>

<span data-ttu-id="7fc64-137">Puoi impostare se gli utenti di Skype for business mobile ricevono avvisi sui messaggi istantanei in arrivo e in uscita, i messaggi della segreteria telefonica e le chiamate perse tramite un servizio di notifica push.</span><span class="sxs-lookup"><span data-stu-id="7fc64-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="7fc64-138">A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il servizio di **notifica push Microsoft**, il **servizio notifica push Apple** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="7fc64-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="7fc64-139">Tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7fc64-139">Keep the following in mind:</span></span>

- <span data-ttu-id="7fc64-140">Se si disattivano le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio di Skype for business nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7fc64-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="7fc64-141">Per impostazione predefinita, le notifiche push sono attivate.</span><span class="sxs-lookup"><span data-stu-id="7fc64-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="7fc64-142">I singoli utenti possono disattivarli in Skype for business nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7fc64-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="7fc64-143">Quando si disattivano le notifiche push, gli utenti non possono riattivarli.</span><span class="sxs-lookup"><span data-stu-id="7fc64-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7fc64-144">Microsoft usa altre società per comunicare in tempo reale le notifiche per dispositivi mobili Skype for business per gli utenti di Windows Phone, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="7fc64-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="7fc64-145">Vedere la presente [informativa sulla privacy](https://go.microsoft.com/fwlink/p/?linkid=247732).</span><span class="sxs-lookup"><span data-stu-id="7fc64-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="7fc64-146">Gestire le impostazioni di Skype for business per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="7fc64-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7fc64-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="7fc64-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="7fc64-148">Per gestire le impostazioni di Skype for business per singoli utenti, nella barra di spostamento sinistra dell'interfaccia di amministrazione di teams, passa a **utenti**, fai clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli utente e quindi seleziona la scheda **impostazioni di Skype for business** . Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7fc64-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for business nella pagina dei dettagli utente":::

### <a name="external-access-settings"></a><span data-ttu-id="7fc64-150">Impostazioni di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="7fc64-150">External access settings</span></span>

<span data-ttu-id="7fc64-151">È possibile consentire o bloccare selettivamente se un utente può comunicare con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="7fc64-152">**Utenti Skype for business esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con utenti Skype for business in domini federati.</span><span class="sxs-lookup"><span data-stu-id="7fc64-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="7fc64-153">**Utenti Skype esterni**: attivare questa opzione se si vuole consentire all'utente di comunicare con utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="7fc64-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="7fc64-154">Impostazioni riunione</span><span class="sxs-lookup"><span data-stu-id="7fc64-154">Meeting settings</span></span>

<span data-ttu-id="7fc64-155">È possibile configurare le impostazioni delle riunioni seguenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7fc64-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="7fc64-156">**Audio & video**: scegliere una delle impostazioni audio e video seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fc64-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="7fc64-157">**Nessuno**: l'utente non può usare l'audio o il video.</span><span class="sxs-lookup"><span data-stu-id="7fc64-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="7fc64-158">**Solo audio**: l'utente può usare l'audio ma non il video.</span><span class="sxs-lookup"><span data-stu-id="7fc64-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="7fc64-159">**Audio e video**: l'utente può usare l'audio e il video.</span><span class="sxs-lookup"><span data-stu-id="7fc64-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="7fc64-160">**Audio e video (HD)**: l'utente può usare l'audio e il video ad alta definizione.</span><span class="sxs-lookup"><span data-stu-id="7fc64-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="7fc64-161">**Registrare conversazioni & riunioni**: attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.</span><span class="sxs-lookup"><span data-stu-id="7fc64-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="7fc64-162">**Conformità**: attivare questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="7fc64-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
