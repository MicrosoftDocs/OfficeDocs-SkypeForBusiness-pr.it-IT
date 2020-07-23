---
title: Elenco di controllo per l'accesso guest in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Informazioni su come attivare e configurare l'accesso guest in Microsoft teams come amministratore globale o in teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d38b0adf1a342c4398d2779e2f0b5ec3aa310144
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372005"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="d96bb-103">Elenco di controllo per l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d96bb-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="d96bb-104">Usare questo elenco di controllo per attivare e configurare l'accesso guest in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="d96bb-105">Per apportare queste modifiche è necessario essere un amministratore globale o un amministratore di Teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d96bb-106">Potrebbe essere necessario attendere qualche ora affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="d96bb-106">You may have to wait a few hours for your changes to take effect.</span></span>

<span data-ttu-id="d96bb-107">Guardare questo breve video (5:31 minuti) per scoprire come attivare l'accesso guest in tutto Microsoft 365, incluso Teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="d96bb-108">Passaggio 1: attivare l'accesso guest a livello di organizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="d96bb-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="d96bb-109">Per apportare queste modifiche, è necessario essere un amministratore del servizio teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-109">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="d96bb-110">Vedere [usare i ruoli di amministratore di team per gestire i team](https://docs.microsoft.com/microsoftteams/using-admin-roles) per leggere informazioni su come ottenere ruoli di amministratore e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d96bb-110">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="d96bb-111">Nell'interfaccia di amministrazione di Teams selezionare **Impostazioni organizzazione** > **Accesso guest**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-111">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="d96bb-112">Impostare il selettore **Consenti accesso ospite in Teams** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-112">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot che mostra un esempio di interruttore impostazioni di Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="d96bb-114">Nella stessa pagina attivare o disattivare le impostazioni di **Chiamata**, **Riunione** e **Messaggistica** per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="d96bb-114">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="d96bb-115">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-115">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="d96bb-116">Se si usano le impostazioni predefinite in Azure Active Directory, SharePoint Online e Microsoft 365 groups, è possibile che sia stata eseguita la configurazione dell'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="d96bb-116">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="d96bb-117">In questo caso, è possibile ignorare il resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="d96bb-117">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="d96bb-118">In caso di dubbi o se si usano impostazioni personalizzate per i gruppi AAD, SharePoint Online o Microsoft 365, procedere con il resto dei passaggi descritti in questo elenco di controllo.</span><span class="sxs-lookup"><span data-stu-id="d96bb-118">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="d96bb-119">Passaggio 2: configurare le impostazioni business-to-business di Azure AD</span><span class="sxs-lookup"><span data-stu-id="d96bb-119">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="d96bb-120">Queste sono le impostazioni di Azure AD che supportano l'accesso guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-120">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="d96bb-121">Una volta configurate queste impostazioni, sarà possibile [aggiungere](add-guests.md) e [gestire i guest](manage-guests.md) in Teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-121">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="d96bb-122">Accedere al [portale di Azure](https://portal.azure.com) come amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="d96bb-122">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="d96bb-123">Selezionare **Azure Active Directory** > **Utenti** > **Impostazioni utente**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-123">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="d96bb-124">In **Utenti esterni** selezionare **Gestisci le impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-124">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d96bb-125">Le **Impostazioni di collaborazione esterna** sono disponibili anche nella pagina **Relazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-125">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="d96bb-126">In Azure Active Directory, in **Gestisci** passare a **Relazioni aziendali** > **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-126">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="d96bb-127">Nella pagina **Impostazioni di collaborazione esterna** scegliere i criteri da abilitare.</span><span class="sxs-lookup"><span data-stu-id="d96bb-127">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="d96bb-128">**Le autorizzazioni degli utenti guest sono limitate**: questo criterio determina le autorizzazioni per i guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="d96bb-128">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="d96bb-129">Selezionare **Sì** per impedire ai guest di eseguire determinate attività della directory, come enumerare utenti, gruppi o altre risorse della directory.</span><span class="sxs-lookup"><span data-stu-id="d96bb-129">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="d96bb-130">Selezionare **No** per concedere ai guest lo stesso accesso degli utenti standard ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="d96bb-130">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="d96bb-131">\*\*Amministratori e utenti nel ruolo mittente dell'invito guest possono invitare \*\*: impostare il criterio su **Sì** per consentire agli amministratori e agli utenti nel ruolo Mittente dell'invito guest di invitare guest.</span><span class="sxs-lookup"><span data-stu-id="d96bb-131">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="d96bb-132">**I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare utenti guest, impostare questo criterio su **Yes** (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="d96bb-132">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="d96bb-133">Se si preferisce che solo gli amministratori siano autorizzati ad aggiungere utenti guest, è possibile impostare questo criterio su **No**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-133">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="d96bb-134">Tenere presente che l'opzione **No** limiterà l'esperienza guest per i proprietari di team non amministratori, che potranno aggiungere in Teams solo utenti guest già aggiunti in Azure AD dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="d96bb-134">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="d96bb-135">**Gli utenti guest possono invitare**: per consentire ai guest di invitare altri guest, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-135">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="d96bb-136">Al momento Teams non supporta il ruolo mittente dell'invito, pertanto se si imposta **I guest possono invitare** su **Sì**, gli utenti guest non possono invitare altri guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="d96bb-136">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="d96bb-137">**Abilita passcode monouso tramite posta elettronica per gli utenti guest (anteprima)**: per altre informazioni sulla funzionalità passcode monouso, vedere [Autenticazione con passcode monouso tramite indirizzo di posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="d96bb-137">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="d96bb-138">**Restrizioni di collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a domini specifici, vedere [Consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="d96bb-138">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="d96bb-139">Per le restrizioni della collaborazione, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="d96bb-139">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

    <span data-ttu-id="d96bb-140">Per altre informazioni su come controllare chi può invitare guest, consultare [Delegare gli inviti per Collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="d96bb-140">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="d96bb-141">Passaggio 3: configurare i gruppi Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d96bb-141">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="d96bb-142">Nell'interfaccia di amministrazione di Microsoft 365 accedere alle **Settings**impostazioni dell'  >  **organizzazione**impostazioni, fare clic su **Servizi**e quindi selezionare **gruppi Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-142">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![La schermata mostra le impostazioni dei gruppi di Microsoft 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="d96bb-144">Assicurarsi che la casella di controllo **Consenti ai membri del gruppo esterni all'organizzazione di accedere al contenuto del gruppo** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d96bb-144">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="d96bb-145">In caso contrario, gli utenti guest non saranno in grado di accedere al contenuto del gruppo.</span><span class="sxs-lookup"><span data-stu-id="d96bb-145">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![La schermata mostra le impostazioni dei gruppi di Microsoft 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="d96bb-147">Assicurarsi che la casella di controllo **Consenti ai proprietari di gruppi di aggiungere persone esterne all'organizzazione ai gruppi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d96bb-147">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="d96bb-148">In caso contrario, i proprietari dei gruppi non saranno in grado aggiungerne nuovi guest.</span><span class="sxs-lookup"><span data-stu-id="d96bb-148">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="d96bb-149">Per supportare l'accesso guest, è necessario come minimo che questa opzione sia attivata.</span><span class="sxs-lookup"><span data-stu-id="d96bb-149">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="d96bb-150">Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di microsoft 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="d96bb-150">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="d96bb-151">Passaggio 4: configurare la condivisione in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d96bb-151">Step 4: Configure sharing in Microsoft 365</span></span>

<span data-ttu-id="d96bb-152">Assicurarsi che gli utenti possano aggiungere guest.</span><span class="sxs-lookup"><span data-stu-id="d96bb-152">Make sure that users can add guests.</span></span> <span data-ttu-id="d96bb-153">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="d96bb-153">Here's how:</span></span>

1. <span data-ttu-id="d96bb-154">Nell'interfaccia di amministrazione di Microsoft 365 accedere alle **Settings**impostazioni dell'  >  **organizzazione**impostazioni, fare clic su **sicurezza & privacy**e quindi selezionare **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-154">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Screenshot che mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-security-privacy-settings.png)

2. <span data-ttu-id="d96bb-156">Selezionare la casella di controllo **Consenti agli utenti di aggiungere nuovi utenti guest all'organizzazione** e quindi fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-156">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Screenshot che mostra un esempio di selettore impostazioni di condivisione](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > <span data-ttu-id="d96bb-158">Questa impostazione è equivalente a **I membri possono invitare** in **Impostazioni utente** > **Utenti esterni** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d96bb-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="d96bb-159">Passaggio 5: verificare l'impostazione di condivisione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="d96bb-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="d96bb-160">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d96bb-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d96bb-161">In **Interfacce di amministrazione** selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="d96bb-162">Nella nuova interfaccia di amministrazione di SharePoint selezionare **Siti attivi** in **Siti**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Siti attivi nell'interfaccia di amministrazione di SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="d96bb-164">Selezionare il sito e fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="d96bb-165">Assicurarsi che l'opzione sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="d96bb-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Screenshot che mostra un esempio di selettore impostazioni di SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="d96bb-167">Passaggio 6: configurare le autorizzazioni degli utenti guest</span><span class="sxs-lookup"><span data-stu-id="d96bb-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="d96bb-168">Nell'applicazione Teams, a livello di singolo team, configurare le autorizzazioni che controllano se gli utenti guest possono creare, aggiornare o eliminare canali.</span><span class="sxs-lookup"><span data-stu-id="d96bb-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="d96bb-169">Possono configurare queste impostazioni gli amministratori di Teams e i proprietari dei team.</span><span class="sxs-lookup"><span data-stu-id="d96bb-169">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot che mostra un esempio di interruttore impostazioni di team/canale](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="d96bb-171">Per altre informazioni sull'accesso guest, vedere [Accesso guest in Teams](guest-access.md) e [Attivare o disattivare l'accesso guest a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d96bb-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d96bb-172">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d96bb-172">Troubleshooting</span></span>

<span data-ttu-id="d96bb-173">In caso di problemi con la configurazione dell'accesso guest o l'aggiunta di utenti guest in Teams, queste risorse possono rivelarsi utili:</span><span class="sxs-lookup"><span data-stu-id="d96bb-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="d96bb-174">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d96bb-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="d96bb-175">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="d96bb-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
