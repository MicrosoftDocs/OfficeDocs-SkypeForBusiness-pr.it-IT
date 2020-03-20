---
title: Elenco di controllo per l'accesso guest in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Usare questo elenco di controllo per configurare l'accesso guest in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833256"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="131b1-103">Elenco di controllo per l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="131b1-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="131b1-104">Usare questo elenco di controllo per attivare e configurare l'accesso guest in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="131b1-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="131b1-105">Per apportare queste modifiche è necessario essere un amministratore globale o un amministratore di Teams.</span><span class="sxs-lookup"><span data-stu-id="131b1-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="131b1-106">Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="131b1-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="131b1-107">Guardare questo breve video (5:31 minuti) per scoprire come attivare l'accesso guest in tutto Microsoft 365, incluso Teams.</span><span class="sxs-lookup"><span data-stu-id="131b1-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="131b1-108">Passaggio 1: attivare l'accesso guest a livello di organizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="131b1-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="131b1-109">Per attivare l'accesso guest, passare all'**interfaccia di amministrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="131b1-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="131b1-110">Nell'interfaccia di amministrazione di Teams selezionare **Impostazioni organizzazione** > **Accesso guest**.</span><span class="sxs-lookup"><span data-stu-id="131b1-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="131b1-111">Impostare il selettore **Consenti accesso ospite in Teams** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="131b1-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot che mostra un esempio di interruttore impostazioni di Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="131b1-113">Nella stessa pagina attivare o disattivare le impostazioni di **Chiamata**, **Riunione** e **Messaggistica** per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="131b1-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="131b1-114">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="131b1-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="131b1-115">Se si usano le impostazioni predefinite per Azure Active Directory, SharePoint Online e Gruppi di Office 365, è possibile che la configurazione dell'accesso guest sia già stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="131b1-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="131b1-116">In questo caso, è possibile ignorare il resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="131b1-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="131b1-117">Se non si è certi o se si usano impostazioni personalizzate per AAD, SharePoint Online o Gruppi di Office 365, continuare con i passaggi rimanenti dell'elenco di controllo.</span><span class="sxs-lookup"><span data-stu-id="131b1-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="131b1-118">Passaggio 2: configurare le impostazioni business-to-business di Azure AD</span><span class="sxs-lookup"><span data-stu-id="131b1-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="131b1-119">Queste sono le impostazioni di Azure AD che supportano l'accesso guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="131b1-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="131b1-120">Una volta configurate queste impostazioni, sarà possibile [aggiungere](add-guests.md) e [gestire i guest](manage-guests.md) in Teams.</span><span class="sxs-lookup"><span data-stu-id="131b1-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="131b1-121">Accedere al [portale di Azure](https://portal.azure.com) come amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="131b1-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="131b1-122">Selezionare **Azure Active Directory** > **Utenti** > **Impostazioni utente**.</span><span class="sxs-lookup"><span data-stu-id="131b1-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="131b1-123">In **Utenti esterni** selezionare **Gestisci le impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="131b1-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="131b1-124">Le **Impostazioni di collaborazione esterna** sono disponibili anche nella pagina **Relazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="131b1-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="131b1-125">In Azure Active Directory, in **Gestisci** passare a **Relazioni aziendali** > **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="131b1-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="131b1-126">Nella pagina **Impostazioni di collaborazione esterna** scegliere i criteri da abilitare.</span><span class="sxs-lookup"><span data-stu-id="131b1-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="131b1-127">**Le autorizzazioni degli utenti guest sono limitate**: questo criterio determina le autorizzazioni per i guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="131b1-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="131b1-128">Selezionare **Sì** per impedire ai guest di eseguire determinate attività della directory, come enumerare utenti, gruppi o altre risorse della directory.</span><span class="sxs-lookup"><span data-stu-id="131b1-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="131b1-129">Selezionare **No** per concedere ai guest lo stesso accesso degli utenti standard ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="131b1-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="131b1-130">\*\*Amministratori e utenti nel ruolo mittente dell'invito guest possono invitare \*\*: impostare il criterio su **Sì** per consentire agli amministratori e agli utenti nel ruolo Mittente dell'invito guest di invitare guest.</span><span class="sxs-lookup"><span data-stu-id="131b1-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="131b1-131">**I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare utenti guest, impostare questo criterio su **Yes** (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="131b1-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="131b1-132">Se si preferisce che solo gli amministratori siano autorizzati ad aggiungere utenti guest, è possibile impostare questo criterio su **No**.</span><span class="sxs-lookup"><span data-stu-id="131b1-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="131b1-133">Tenere presente che l'opzione **No** limiterà l'esperienza guest per i proprietari di team non amministratori, che potranno aggiungere in Teams solo utenti guest già aggiunti in Azure AD dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="131b1-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="131b1-134">**Gli utenti guest possono invitare**: per consentire ai guest di invitare altri guest, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="131b1-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="131b1-135">Al momento Teams non supporta il ruolo mittente dell'invito, pertanto se si imposta **I guest possono invitare** su **Sì**, gli utenti guest non possono invitare altri guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="131b1-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="131b1-136">**Abilita passcode monouso tramite posta elettronica per gli utenti guest (anteprima)**: per altre informazioni sulla funzionalità passcode monouso, vedere [Autenticazione con passcode monouso tramite indirizzo di posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="131b1-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="131b1-137">**Restrizioni di collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a domini specifici, vedere [Consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="131b1-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="131b1-138">Per le restrizioni della collaborazione, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="131b1-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="131b1-139">Per altre informazioni su come controllare chi può invitare guest, consultare [Delegare gli inviti per Collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="131b1-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="131b1-140">Passaggio 3: configurare i Gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="131b1-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="131b1-141">Nell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** > **Impostazioni**, fare clic su **Servizi** e quindi selezionare **Gruppi di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="131b1-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![Screenshot che mostra le impostazioni dei Gruppi di Office 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="131b1-143">Assicurarsi che la casella di controllo **Consenti ai membri del gruppo esterni all'organizzazione di accedere al contenuto del gruppo** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="131b1-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="131b1-144">In caso contrario, gli utenti guest non saranno in grado di accedere al contenuto del gruppo.</span><span class="sxs-lookup"><span data-stu-id="131b1-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Screenshot che mostra le impostazioni dei Gruppi di Office 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="131b1-146">Assicurarsi che la casella di controllo **Consenti ai proprietari di gruppi di aggiungere persone esterne all'organizzazione ai gruppi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="131b1-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="131b1-147">In caso contrario, i proprietari dei gruppi non saranno in grado aggiungerne nuovi guest.</span><span class="sxs-lookup"><span data-stu-id="131b1-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="131b1-148">Per supportare l'accesso guest, è necessario come minimo che questa opzione sia attivata.</span><span class="sxs-lookup"><span data-stu-id="131b1-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="131b1-149">Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [Gestire l'accesso guest in Gruppi di Office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [Controllare l'accesso guest in Gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="131b1-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="131b1-150">Passaggio 4: configurare la condivisione in Office 365</span><span class="sxs-lookup"><span data-stu-id="131b1-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="131b1-151">Assicurarsi che gli utenti possano aggiungere guest.</span><span class="sxs-lookup"><span data-stu-id="131b1-151">Make sure that users can add guests.</span></span> <span data-ttu-id="131b1-152">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="131b1-152">Here's how:</span></span>

1. <span data-ttu-id="131b1-153">Nell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** > **Impostazioni**, fare clic su **Sicurezza e privacy** e quindi selezionare **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="131b1-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Screenshot che mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="131b1-155">Selezionare la casella di controllo **Consenti agli utenti di aggiungere nuovi utenti guest all'organizzazione** e quindi fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="131b1-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Screenshot che mostra un esempio di selettore impostazioni di condivisione](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="131b1-157">Questa impostazione è equivalente a **I membri possono invitare** in **Impostazioni utente** > **Utenti esterni** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="131b1-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="131b1-158">Passaggio 5: verificare l'impostazione di condivisione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="131b1-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="131b1-159">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="131b1-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="131b1-160">In **Interfacce di amministrazione** selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="131b1-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="131b1-161">Nella nuova interfaccia di amministrazione di SharePoint selezionare **Siti attivi** in **Siti**.</span><span class="sxs-lookup"><span data-stu-id="131b1-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Siti attivi nell'interfaccia di amministrazione di SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="131b1-163">Selezionare il sito e fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="131b1-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="131b1-164">Assicurarsi che l'opzione sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="131b1-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Screenshot che mostra un esempio di selettore impostazioni di SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="131b1-166">Passaggio 6: configurare le autorizzazioni degli utenti guest</span><span class="sxs-lookup"><span data-stu-id="131b1-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="131b1-167">Nell'applicazione Teams, a livello di singolo team, configurare le autorizzazioni che controllano se gli utenti guest possono creare, aggiornare o eliminare canali.</span><span class="sxs-lookup"><span data-stu-id="131b1-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="131b1-168">Possono configurare queste impostazioni gli amministratori di Teams e i proprietari dei team.</span><span class="sxs-lookup"><span data-stu-id="131b1-168">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot che mostra un esempio di interruttore impostazioni di team/canale](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="131b1-170">Per altre informazioni sull'accesso guest, vedere [Accesso guest in Teams](guest-access.md) e [Attivare o disattivare l'accesso guest a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="131b1-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="131b1-171">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="131b1-171">Troubleshooting</span></span>

<span data-ttu-id="131b1-172">In caso di problemi con la configurazione dell'accesso guest o l'aggiunta di utenti guest in Teams, queste risorse possono rivelarsi utili:</span><span class="sxs-lookup"><span data-stu-id="131b1-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="131b1-173">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="131b1-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="131b1-174">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="131b1-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
