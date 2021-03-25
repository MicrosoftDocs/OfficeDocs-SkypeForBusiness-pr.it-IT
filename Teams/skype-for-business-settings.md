---
title: Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams
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
description: Scopri come gestire le impostazioni per le funzionalità di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117004"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d2bcd-103">Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d2bcd-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d2bcd-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="d2bcd-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="d2bcd-105">L'interfaccia di amministrazione di Microsoft Teams consente di gestire le funzionalità di Skype for Business per gli utenti Skype for Business dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="d2bcd-106">Puoi gestire le impostazioni [per la tua](#manage-skype-for-business-settings-for-your-organization) organizzazione [](#manage-skype-for-business-settings-for-individual-users) nella pagina Skype **for Business** e le impostazioni per i singoli utenti nella scheda Skype **for Business** delle pagine dei dettagli degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="d2bcd-107">Verrà visualizzata la pagina **Skype for Business** solo se la modalità di coesistenza per l'organizzazione non è impostata solo su **Teams.**</span><span class="sxs-lookup"><span data-stu-id="d2bcd-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="d2bcd-108">Allo stesso modo, vedrai la scheda **Skype for Business** per un utente solo se la modalità di coesistenza dell'utente non è solo **Teams.**</span><span class="sxs-lookup"><span data-stu-id="d2bcd-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="d2bcd-109">Per altre informazioni sulle modalità di coesistenza, vedere Informazioni sulla coesistenza e [l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Teams e Skype for Business e [Impostare le impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d2bcd-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d2bcd-110">Le impostazioni di Skype for Business si trovavano in **precedenza** nel portale legacy nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d2bcd-111">Con il ritiro del portale legacy, abbiamo eseguito la migrazione delle impostazioni in queste nuove posizioni nell'interfaccia di amministrazione di Teams per la gestione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="d2bcd-112">Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams, è necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) dell'amministratore globale o dell'amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="d2bcd-113">Gestire le impostazioni di Skype for Business per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d2bcd-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="d2bcd-114">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Impostazioni** a livello di  >  **organizzazione Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="d2bcd-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="d2bcd-115">Da qui puoi configurare e gestire Skype Meeting Broadcast, la privacy della presenza e le notifiche dei dispositivi mobili per tutti gli utenti Skype for Business della tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="d2bcd-116">Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="d2bcd-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d2bcd-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="d2bcd-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="d2bcd-118">Usa le impostazioni seguenti per gestire [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) nella tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni di Skype Meeting Broadcast nell'interfaccia di amministrazione":::

- <span data-ttu-id="d2bcd-120">**Skype Meeting Broadcasts:** attiva questa opzione per abilitare Skype Meeting Broadcast per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="d2bcd-121">Dopo aver abilitato questa funzionalità, è necessario [configurare la rete per Skype Meeting Broadcast.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)</span><span class="sxs-lookup"><span data-stu-id="d2bcd-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="d2bcd-122">**Vedere funzionalità di anteprima:** attivare questa opzione per ottenere l'accesso anticipato alle nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="d2bcd-123">**Gli organizzatori possono pianificare riunioni** anonime: attivare questa opzione se si vuole consentire agli organizzatori di creare eventi di trasmissione che consentano a chiunque all'esterno dell'organizzazione di partecipare senza dover accedere.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="d2bcd-124">**Registra riunioni Skype Meeting Broadcast:** attiva questa opzione per consentire a organizzatori e relatori di registrare le riunioni.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="d2bcd-125">**URL supporto helpdesk** per i partecipanti: immettere l'URL di supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di assistenza durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="d2bcd-126">Notifiche di presenza e dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d2bcd-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d2bcd-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="d2bcd-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="d2bcd-128">Usare le impostazioni seguenti per gestire la privacy della presenza di Skype for Business e le notifiche per dispositivi mobili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione":::

#### <a name="presence"></a><span data-ttu-id="d2bcd-130">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="d2bcd-130">Presence</span></span>

<span data-ttu-id="d2bcd-131">Per impostazione predefinita, gli utenti skype for business dell'organizzazione possono vedere lo stato presenza (ad esempio Disponibile, Occupato o Non al computer) di altri utenti di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="d2bcd-132">Scegli una delle opzioni seguenti per impostare chi può vedere la presenza degli utenti Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="d2bcd-133">**Visualizzare automaticamente** le informazioni sulla presenza: qualsiasi utente Skype for Business  dell'organizzazione che non è stato aggiunto all'elenco Esterno o Bloccato dell'utente può vedere la presenza dell'utente. </span><span class="sxs-lookup"><span data-stu-id="d2bcd-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="d2bcd-134">**Visualizzare le** informazioni sulla presenza solo ai contatti di un utente: qualsiasi utente Skype for  Business  nell'elenco Contatti dell'utente che non viene aggiunto all'elenco Esterno o Bloccato può vedere la presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="d2bcd-135">Gli utenti possono ignorare questa impostazione in Skype for Business andando in **Strumenti**  >  **impostazioni**  >  **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="d2bcd-136">Notifiche per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d2bcd-136">Mobile notifications</span></span>

<span data-ttu-id="d2bcd-137">È possibile specificare se gli utenti di Skype for Business per dispositivi mobili riceveno avvisi relativi ai messaggi istantanei in arrivo e persi, ai messaggi della segreteria telefonica e alle chiamate perse tramite un servizio di notifica push.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="d2bcd-138">A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il servizio di notifica **Push Microsoft,** il servizio di notifica **Push Apple** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="d2bcd-139">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d2bcd-139">Keep the following in mind:</span></span>

- <span data-ttu-id="d2bcd-140">Se dissegni le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio di Skype for Business sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="d2bcd-141">Per impostazione predefinita, le notifiche push sono attivate.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="d2bcd-142">I singoli utenti possono disattivarli in Skype for Business sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="d2bcd-143">Quando si disattivano le notifiche push, gli utenti non possono riattivarle.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d2bcd-144">Microsoft usa altre società per fornire notifiche per dispositivi mobili Skype for Business in tempo reale per gli utenti di Windows Phone, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="d2bcd-145">Vedere questa [Informativa sulla privacy.](https://go.microsoft.com/fwlink/p/?linkid=247732)</span><span class="sxs-lookup"><span data-stu-id="d2bcd-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="d2bcd-146">Gestire le impostazioni di Skype for Business per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="d2bcd-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d2bcd-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="d2bcd-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="d2bcd-148">Per gestire le impostazioni di Skype for Business per i singoli utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Utenti,** fare clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli utente e quindi selezionare la scheda Impostazioni **di Skype for Business.** Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for Business nella pagina dei dettagli dell'utente":::

### <a name="external-access-settings"></a><span data-ttu-id="d2bcd-150">Impostazioni di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d2bcd-150">External access settings</span></span>

<span data-ttu-id="d2bcd-151">È possibile consentire o bloccare in modo selettivo se un utente può comunicare con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="d2bcd-152">**Utenti esterni di Skype for Business:** attiva questa opzione per consentire all'utente di comunicare con utenti Skype for Business in domini federati.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="d2bcd-153">**Utenti Skype esterni:** attiva questa opzione per consentire all'utente di comunicare con gli utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="d2bcd-154">Impostazioni riunione</span><span class="sxs-lookup"><span data-stu-id="d2bcd-154">Meeting settings</span></span>

<span data-ttu-id="d2bcd-155">È possibile configurare le impostazioni della riunione seguenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="d2bcd-156">**Audio & Video:** scegliere una delle impostazioni audio e video seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2bcd-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="d2bcd-157">**Nessuno:** l'utente non può usare audio o video.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="d2bcd-158">**Solo audio:** l'utente può usare l'audio ma non il video.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="d2bcd-159">**Audio e video:** l'utente può usare audio e video.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="d2bcd-160">**Audio e video (HD): l'utente** può usare audio e video ad alta definizione.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="d2bcd-161">**Registrare conversazioni & riunioni:** attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="d2bcd-162">**Conformità:** attivare questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="d2bcd-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>