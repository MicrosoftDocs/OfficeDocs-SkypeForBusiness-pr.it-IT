---
title: Elenco di controllo di accesso guest di Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Usare questo elenco di controllo per configurare l'accesso guest in Microsoft teams.
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
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833256"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="69dd7-103">Elenco di controllo di accesso guest di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69dd7-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="69dd7-104">Usare questo elenco di controllo per attivare e configurare l'accesso guest in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="69dd7-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="69dd7-105">È necessario essere un amministratore globale o un amministratore di teams per apportare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="69dd7-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69dd7-106">Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="69dd7-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="69dd7-107">Guardare questo breve video (5:31 minuti) per vedere come attivare l'accesso guest in tutto Microsoft 365, inclusi i team.</span><span class="sxs-lookup"><span data-stu-id="69dd7-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="69dd7-108">Passaggio 1: attivare l'accesso Guest a livello di organizzazione Teams</span><span class="sxs-lookup"><span data-stu-id="69dd7-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="69dd7-109">Per attivare l'accesso guest, accedere all'interfaccia di **amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="69dd7-110">Nell'interfaccia di amministrazione di teams selezionare**l'accesso Guest** **delle impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="69dd7-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="69dd7-111">Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="69dd7-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot mostra un esempio di attivazione di impostazioni team](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="69dd7-113">Nella stessa pagina attivare o disattivare le impostazioni di **chiamata**, **riunione**e **messaggistica** per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="69dd7-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="69dd7-114">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="69dd7-115">Se si usano le impostazioni predefinite in Azure Active Directory, SharePoint Online e Office 365 groups, è possibile che sia stata eseguita la configurazione dell'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="69dd7-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="69dd7-116">In questo caso, è possibile ignorare il resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="69dd7-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="69dd7-117">In caso di dubbi o se si usano impostazioni personalizzate per i gruppi AAD, SharePoint Online o Office 365, procedere con il resto della procedura descritta in questo elenco di controllo.</span><span class="sxs-lookup"><span data-stu-id="69dd7-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="69dd7-118">Passaggio 2: configurare le impostazioni di Azure AD business-to-business</span><span class="sxs-lookup"><span data-stu-id="69dd7-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="69dd7-119">Queste sono le impostazioni di Azure AD che supportano l'accesso guest in teams.</span><span class="sxs-lookup"><span data-stu-id="69dd7-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="69dd7-120">Una volta configurate queste impostazioni, sarà possibile [aggiungere](add-guests.md) e [gestire gli](manage-guests.md) utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="69dd7-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="69dd7-121">Accedere a [Azure Portal](https://portal.azure.com) come amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="69dd7-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="69dd7-122">Selezionare\*\*\*\* > **le impostazioni utente**di **Azure Active Directory** > Users.</span><span class="sxs-lookup"><span data-stu-id="69dd7-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="69dd7-123">In **utenti esterni**selezionare **Gestisci impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="69dd7-124">Le **impostazioni di collaborazione esterna** sono disponibili anche nella pagina **relazioni organizzative** .</span><span class="sxs-lookup"><span data-stu-id="69dd7-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="69dd7-125">In Azure Active Directory, in **Gestisci**, passa a > **Impostazioni** **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="69dd7-126">Nella pagina **impostazioni di collaborazione esterna** scegliere i criteri che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="69dd7-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="69dd7-127">Le **autorizzazioni degli utenti Guest sono limitate**: questo criterio determina le autorizzazioni per gli ospiti nella directory.</span><span class="sxs-lookup"><span data-stu-id="69dd7-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="69dd7-128">Selezionare **Sì** per bloccare gli ospiti da determinate attività di directory, come l'enumerazione di utenti, gruppi o altre risorse di directory.</span><span class="sxs-lookup"><span data-stu-id="69dd7-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="69dd7-129">Selezionare **No** per offrire agli ospiti lo stesso accesso ai dati della directory come utenti regolari nella directory.</span><span class="sxs-lookup"><span data-stu-id="69dd7-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="69dd7-130">Gli **amministratori e gli utenti del ruolo dell'invitato Guest possono invitare**: per consentire agli amministratori e agli utenti del ruolo "Guest invite" di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="69dd7-131">**I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare utenti guest, impostare questo criterio su **Yes** (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="69dd7-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="69dd7-132">Se si preferisce che solo gli amministratori siano autorizzati ad aggiungere utenti guest, è possibile impostare questo criterio su **No**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="69dd7-133">Tenere presente che l'opzione **No** limiterà l'esperienza guest per i proprietari di team non amministratori, che potranno aggiungere in Teams solo utenti guest già aggiunti in Azure AD dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="69dd7-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="69dd7-134">**Gli ospiti possono invitare**: per consentire agli ospiti di invitare altri ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="69dd7-135">Al momento Teams non supporta il ruolo mittente dell'invito, pertanto se si imposta **I guest possono invitare** su **Sì**, gli utenti guest non possono invitare altri guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="69dd7-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="69dd7-136">**Abilitare la password unica per gli utenti (anteprima)**: per altre informazioni sulla funzionalità di codice per la sola volta, vedere autenticazione di un codice di accesso unico per la [posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="69dd7-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="69dd7-137">**Limitazioni della collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a specifici domini, vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="69dd7-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="69dd7-138">Per le limitazioni della collaborazione, vedere [abilitare la collaborazione esterna B2B e gestire chi può invitare gli ospiti](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="69dd7-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="69dd7-139">Per altre informazioni su come controllare chi può invitare guest, consultare [Delegare gli inviti per Collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="69dd7-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="69dd7-140">Passaggio 3: configurare i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="69dd7-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="69dd7-141">Nell'interfaccia di amministrazione di Microsoft 365, accedere a**Impostazioni** **Impostazioni** > , fare clic su **Servizi**e quindi selezionare **gruppi di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![La schermata mostra le impostazioni dei gruppi di Office 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="69dd7-143">Verificare che la casella di controllo **consente ai membri del gruppo all'esterno del contenuto dell'organizzazione di Access Group** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="69dd7-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="69dd7-144">Se questa impostazione non è selezionata, gli utenti non saranno in grado di accedere a qualsiasi contenuto di gruppo.</span><span class="sxs-lookup"><span data-stu-id="69dd7-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![La schermata mostra le impostazioni dei gruppi di Office 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="69dd7-146">Verificare che la casella **di controllo Let Group owners Add people outside the Organization to** groups sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="69dd7-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="69dd7-147">Se questa impostazione non è selezionata, i proprietari del team non saranno in grado di aggiungere nuovi Guest.</span><span class="sxs-lookup"><span data-stu-id="69dd7-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="69dd7-148">Questa impostazione deve essere almeno attiva per supportare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="69dd7-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="69dd7-149">Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="69dd7-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="69dd7-150">Passaggio 4: configurare la condivisione in Office 365</span><span class="sxs-lookup"><span data-stu-id="69dd7-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="69dd7-151">Assicurarsi che gli utenti possano aggiungere Guest.</span><span class="sxs-lookup"><span data-stu-id="69dd7-151">Make sure that users can add guests.</span></span> <span data-ttu-id="69dd7-152">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="69dd7-152">Here's how:</span></span>

1. <span data-ttu-id="69dd7-153">Nell'interfaccia di amministrazione di Microsoft 365, accedere **a** > **Impostazioni**, fare clic su **sicurezza & privacy**e quindi selezionare **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Screenshot mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="69dd7-155">Selezionare la casella **di controllo consente agli utenti di aggiungere nuovi Guest all'organizzazione** e quindi fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="69dd7-157">Questa impostazione è equivalente ai **membri che possono invitare** l'impostazione in **Impostazioni** > utente**utenti esterni** in Azure ad.</span><span class="sxs-lookup"><span data-stu-id="69dd7-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="69dd7-158">Passaggio 5: verificare l'impostazione di condivisione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="69dd7-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="69dd7-159">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69dd7-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="69dd7-160">In **centri di amministrazione**selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="69dd7-161">Nella nuova interfaccia di amministrazione di SharePoint, in **siti**, selezionare **siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Siti attivi nell'interfaccia di amministrazione di SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="69dd7-163">Selezionare il sito e quindi fare clic su **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="69dd7-164">Verificare che l'opzione sia impostata su **tutti gli utenti** o **gli ospiti nuovi o esistenti**.</span><span class="sxs-lookup"><span data-stu-id="69dd7-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="69dd7-166">Passaggio 6: configurare le autorizzazioni per gli utenti Guest</span><span class="sxs-lookup"><span data-stu-id="69dd7-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="69dd7-167">Nell'applicazione teams, a livello di team specifico, configura le autorizzazioni guest che controllano se gli utenti possono creare, aggiornare o eliminare canali.</span><span class="sxs-lookup"><span data-stu-id="69dd7-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="69dd7-168">Gli amministratori dei team e i proprietari del team possono configurare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="69dd7-168">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot mostra un esempio di attivazione di impostazioni del team/canale](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="69dd7-170">Per ulteriori informazioni sull'accesso guest, vedere [accesso guest in teams](guest-access.md) e [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="69dd7-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="69dd7-171">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="69dd7-171">Troubleshooting</span></span>

<span data-ttu-id="69dd7-172">In caso di problemi con l'impostazione dell'accesso guest o l'aggiunta di ospiti in teams, usare queste risorse per aiutarti:</span><span class="sxs-lookup"><span data-stu-id="69dd7-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="69dd7-173">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69dd7-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="69dd7-174">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="69dd7-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
