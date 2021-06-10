---
title: Gestire Skype for Business impostazioni nell'Microsoft Teams di amministrazione
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
description: Informazioni su come gestire le impostazioni per Skype for Business funzionalità nell'interfaccia Microsoft Teams di amministrazione.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117004"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7519e-103">Gestire Skype for Business impostazioni nell'Microsoft Teams di amministrazione</span><span class="sxs-lookup"><span data-stu-id="7519e-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7519e-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="7519e-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="7519e-105">L'interfaccia di amministrazione Microsoft Teams è la posizione in cui è possibile gestire le Skype for Business per Skype for Business utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="7519e-106">È possibile gestire le [impostazioni per l'organizzazione](#manage-skype-for-business-settings-for-your-organization) [](#manage-skype-for-business-settings-for-individual-users) **nella** pagina Skype for Business e le impostazioni per i singoli utenti nella scheda Skype for Business **delle** pagine dei dettagli utente.</span><span class="sxs-lookup"><span data-stu-id="7519e-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="7519e-107">Verrà visualizzata la  pagina Skype for Business solo se la modalità di coesistenza per l'organizzazione non è impostata su **solo Teams .**</span><span class="sxs-lookup"><span data-stu-id="7519e-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="7519e-108">Allo stesso modo, verrà visualizzata la scheda Skype for Business **per** un utente solo se la modalità di coesistenza dell'utente non è Teams **solo**.</span><span class="sxs-lookup"><span data-stu-id="7519e-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="7519e-109">Per altre informazioni sulle modalità di coesistenza, vedere Comprendere Teams e [Skype for Business e](teams-and-skypeforbusiness-coexistence-and-interoperability.md) l'interoperabilità e Impostare le impostazioni di [coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7519e-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7519e-110">Skype for Business impostazioni precedenti erano nel **portale legacy** nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7519e-111">Con il ritiro del portale legacy, è stata eseguita la migrazione delle impostazioni in queste nuove posizioni nell'interfaccia di amministrazione di Teams per Skype for Business gestione.</span><span class="sxs-lookup"><span data-stu-id="7519e-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="7519e-112">È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire le funzionalità di Skype for Business nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="7519e-113">Gestire Skype for Business per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7519e-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="7519e-114">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a **Impostazioni a** livello di  >  **organizzazione Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="7519e-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="7519e-115">Da qui è possibile configurare e gestire Riunione Skype broadcast, la privacy della presenza e le notifiche dei dispositivi mobili per tutti Skype for Business utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="7519e-116">Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="7519e-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7519e-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="7519e-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="7519e-118">Usare le impostazioni seguenti per gestire Riunione Skype [broadcast nell'organizzazione.](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="7519e-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot delle impostazioni Riunione Skype broadcast nell'interfaccia di amministrazione":::

- <span data-ttu-id="7519e-120">**Riunione Skype broadcast:** attiva questa opzione per abilitare Riunione Skype broadcast per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="7519e-121">Dopo aver abilitato questa funzionalità, è necessario [configurare la rete](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)per Riunione Skype Broadcast .</span><span class="sxs-lookup"><span data-stu-id="7519e-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="7519e-122">**Vedere funzionalità di anteprima:** attivare questa opzione per ottenere l'accesso anticipato alle nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7519e-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="7519e-123">**Gli organizzatori possono pianificare riunioni** anonime: attivare questa opzione se si vuole consentire agli organizzatori di creare eventi di trasmissione che consentano a chiunque all'esterno dell'organizzazione di partecipare senza dover accedere.</span><span class="sxs-lookup"><span data-stu-id="7519e-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="7519e-124">**Registrare Riunione Skype riunioni broadcast:** attivare questa opzione per consentire a organizzatori e relatori di registrare le riunioni.</span><span class="sxs-lookup"><span data-stu-id="7519e-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="7519e-125">**URL supporto helpdesk** per i partecipanti: immettere l'URL di supporto dell'organizzazione che i partecipanti alla riunione possono usare se hanno bisogno di assistenza durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="7519e-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="7519e-126">Notifiche di presenza e dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7519e-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7519e-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="7519e-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="7519e-128">Usare le impostazioni seguenti per gestire la privacy Skype for Business sulla presenza e le notifiche per dispositivi mobili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot delle impostazioni di presenza nell'interfaccia di amministrazione":::

#### <a name="presence"></a><span data-ttu-id="7519e-130">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="7519e-130">Presence</span></span>

<span data-ttu-id="7519e-131">Per impostazione predefinita, Skype for Business utenti dell'organizzazione possono vedere lo stato presenza (ad esempio Disponibile, Occupato o Non al computer) di altri Skype for Business utenti.</span><span class="sxs-lookup"><span data-stu-id="7519e-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="7519e-132">Scegliere una delle opzioni seguenti per impostare gli utenti che possono vedere la presenza Skype for Business utenti.</span><span class="sxs-lookup"><span data-stu-id="7519e-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="7519e-133">**Visualizzare automaticamente** le informazioni sulla presenza: qualsiasi utente Skype for Business dell'organizzazione che  non  è stato aggiunto all'elenco Esterno o Bloccato dell'utente può vedere la presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7519e-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="7519e-134">**Visualizzare le** informazioni sulla presenza solo per i contatti di un utente: qualsiasi utente Skype for Business  nell'elenco Contatti dell'utente che non viene aggiunto all'elenco Esterno o Bloccato può vedere la presenza dell'utente. </span><span class="sxs-lookup"><span data-stu-id="7519e-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="7519e-135">Gli utenti possono ignorare questa impostazione in Skype for Business selezionando **Impostazioni**  >  **Strumenti**  >  **.**</span><span class="sxs-lookup"><span data-stu-id="7519e-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="7519e-136">Notifiche per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7519e-136">Mobile notifications</span></span>

<span data-ttu-id="7519e-137">È possibile specificare se gli utenti Skype for Business utenti mobili riceverà avvisi sui messaggi istantanei in arrivo e persi, sui messaggi della segreteria telefonica e sulle chiamate perse tramite un servizio di notifica push.</span><span class="sxs-lookup"><span data-stu-id="7519e-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="7519e-138">A seconda dei dispositivi mobili usati nell'organizzazione, è possibile usare il servizio di notifica **Push Microsoft,** il servizio di notifica **Push Apple** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="7519e-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="7519e-139">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7519e-139">Keep the following in mind:</span></span>

- <span data-ttu-id="7519e-140">Se si disattivano le notifiche push, gli utenti riceveranno tutti gli avvisi al successivo avvio Skype for Business sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7519e-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="7519e-141">Per impostazione predefinita, le notifiche push sono attivate.</span><span class="sxs-lookup"><span data-stu-id="7519e-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="7519e-142">I singoli utenti possono disattivarli Skype for Business sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7519e-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="7519e-143">Quando si disattivano le notifiche push, gli utenti non possono riattivarle.</span><span class="sxs-lookup"><span data-stu-id="7519e-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7519e-144">Microsoft usa altre società per fornire notifiche in tempo Skype for Business per dispositivi mobili per Windows Phone, iPhone e iPad utenti.</span><span class="sxs-lookup"><span data-stu-id="7519e-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="7519e-145">Vedere questa [Informativa sulla privacy.](https://go.microsoft.com/fwlink/p/?linkid=247732)</span><span class="sxs-lookup"><span data-stu-id="7519e-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="7519e-146">Gestire Skype for Business per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="7519e-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="7519e-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="7519e-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="7519e-148">Per gestire le impostazioni di Skype for Business per i singoli utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Utenti,** fare clic sul nome visualizzato dell'utente per aprire la pagina dei dettagli utente e quindi selezionare la scheda **Impostazioni** Skype for Business utente. Da qui è possibile configurare le impostazioni di accesso esterno e riunione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7519e-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot della scheda Skype for Business nella pagina dei dettagli utente":::

### <a name="external-access-settings"></a><span data-ttu-id="7519e-150">Impostazioni di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="7519e-150">External access settings</span></span>

<span data-ttu-id="7519e-151">È possibile consentire o bloccare in modo selettivo se un utente può comunicare con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7519e-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="7519e-152">**Utenti Skype for Business** esterni: attivare questa opzione se si vuole consentire all'utente di comunicare con Skype for Business utenti nei domini federati.</span><span class="sxs-lookup"><span data-stu-id="7519e-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="7519e-153">**Utenti Skype** esterni: attivare questa opzione se si vuole consentire all'utente di comunicare con Skype utenti.</span><span class="sxs-lookup"><span data-stu-id="7519e-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="7519e-154">Impostazioni riunione</span><span class="sxs-lookup"><span data-stu-id="7519e-154">Meeting settings</span></span>

<span data-ttu-id="7519e-155">È possibile configurare le impostazioni della riunione seguenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7519e-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="7519e-156">**Audio & Video:** scegliere una delle impostazioni audio e video seguenti:</span><span class="sxs-lookup"><span data-stu-id="7519e-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="7519e-157">**Nessuno:** l'utente non può usare audio o video.</span><span class="sxs-lookup"><span data-stu-id="7519e-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="7519e-158">**Solo audio:** l'utente può usare l'audio ma non il video.</span><span class="sxs-lookup"><span data-stu-id="7519e-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="7519e-159">**Audio e video:** l'utente può usare audio e video.</span><span class="sxs-lookup"><span data-stu-id="7519e-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="7519e-160">**Audio e video (HD): l'utente** può usare audio e video ad alta definizione.</span><span class="sxs-lookup"><span data-stu-id="7519e-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="7519e-161">**Registrare conversazioni & riunioni:** attivare questa opzione per consentire all'utente di registrare conversazioni e riunioni.</span><span class="sxs-lookup"><span data-stu-id="7519e-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="7519e-162">**Conformità:** attivare questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="7519e-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>