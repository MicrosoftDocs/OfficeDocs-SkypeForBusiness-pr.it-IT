---
title: Elenco di controllo di accesso guest di Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Usare questo elenco di controllo per configurare l'accesso guest in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcba883166e01bd8a18d6d76b4622df0740500c8
ms.sourcegitcommit: 000fdb3bc1a0d4dda63fb00bab6a9a9ab0c85ab0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "39813776"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="81cba-103">Elenco di controllo di accesso guest di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81cba-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="81cba-104">Usare questo elenco di controllo per attivare e configurare l'accesso guest in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="81cba-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="81cba-105">È necessario essere un amministratore globale o un amministratore di teams per apportare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="81cba-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81cba-106">Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="81cba-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="81cba-107">Guardare questo breve video (5:31 minuti) per vedere come attivare l'accesso guest in tutto Microsoft 365, inclusi i team.</span><span class="sxs-lookup"><span data-stu-id="81cba-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="81cba-108">Passaggio 1: attivare l'accesso Guest a livello di organizzazione Teams</span><span class="sxs-lookup"><span data-stu-id="81cba-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="81cba-109">Per attivare l'accesso guest, accedere all'interfaccia di **amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="81cba-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="81cba-110">Nell'interfaccia di amministrazione di teams selezionare**l'accesso Guest** **delle impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="81cba-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="81cba-111">Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="81cba-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot mostra un esempio di attivazione di impostazioni team](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="81cba-113">Nella stessa pagina attivare o disattivare le impostazioni di **chiamata**, **riunione**e **messaggistica** per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="81cba-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="81cba-114">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81cba-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="81cba-115">Se si usano le impostazioni predefinite in Azure Active Directory, SharePoint Online e Office 365 groups, è possibile che sia stata eseguita la configurazione dell'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="81cba-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="81cba-116">In questo caso, è possibile ignorare il resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="81cba-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="81cba-117">In caso di dubbi o se si usano impostazioni personalizzate per i gruppi AAD, SharePoint Online o Office 365, procedere con il resto della procedura descritta in questo elenco di controllo.</span><span class="sxs-lookup"><span data-stu-id="81cba-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="81cba-118">Passaggio 2: configurare le impostazioni di Azure AD business-to-business</span><span class="sxs-lookup"><span data-stu-id="81cba-118">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="81cba-119">Accedere a [Azure Portal](https://portal.azure.com) come amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="81cba-119">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="81cba-120">Selezionare\*\*\*\* > **le impostazioni utente**di **Azure Active Directory** > Users.</span><span class="sxs-lookup"><span data-stu-id="81cba-120">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="81cba-121">In **utenti esterni**selezionare **Gestisci impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="81cba-121">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="81cba-122">Le **impostazioni di collaborazione esterna** sono disponibili anche nella pagina **relazioni organizzative** .</span><span class="sxs-lookup"><span data-stu-id="81cba-122">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="81cba-123">In Azure Active Directory, in **Gestisci**, passa a > **Impostazioni** **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="81cba-123">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="81cba-124">Nella pagina **impostazioni di collaborazione esterna** scegliere i criteri che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="81cba-124">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="81cba-125">Le **autorizzazioni degli utenti Guest sono limitate**: questo criterio determina le autorizzazioni per gli ospiti nella directory.</span><span class="sxs-lookup"><span data-stu-id="81cba-125">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="81cba-126">Selezionare **Sì** per bloccare gli ospiti da determinate attività di directory, come l'enumerazione di utenti, gruppi o altre risorse di directory.</span><span class="sxs-lookup"><span data-stu-id="81cba-126">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="81cba-127">Selezionare **No** per offrire agli ospiti lo stesso accesso ai dati della directory come utenti regolari nella directory.</span><span class="sxs-lookup"><span data-stu-id="81cba-127">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="81cba-128">Gli **amministratori e gli utenti del ruolo dell'invitato Guest possono invitare**: per consentire agli amministratori e agli utenti del ruolo "Guest invite" di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="81cba-128">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="81cba-129">**I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="81cba-129">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>

         > [!NOTE]
         > <span data-ttu-id="81cba-130">Se si impostano **membri può invitare** a **No** e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="81cba-130">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="81cba-131">Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team.</span><span class="sxs-lookup"><span data-stu-id="81cba-131">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="81cba-132">Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="81cba-132">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="81cba-133">Per il pieno funzionamento dell'accesso guest in Teams, è necessario impostare **I membri possono invitare** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="81cba-133">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
     - <span data-ttu-id="81cba-134">**Gli ospiti possono invitare**: per consentire agli ospiti di invitare altri ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="81cba-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="81cba-135">Al momento Teams non supporta il ruolo mittente dell'invito, pertanto se si imposta **I guest possono invitare** su **Sì**, gli utenti guest non possono invitare altri guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="81cba-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="81cba-136">**Abilitare la password unica per gli utenti (anteprima)**: per altre informazioni sulla funzionalità di codice per la sola volta, vedere autenticazione di un codice di accesso unico per la [posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="81cba-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="81cba-137">**Limitazioni della collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a specifici domini, vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="81cba-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="81cba-138">Per le limitazioni della collaborazione, vedere [abilitare la collaborazione esterna B2B e gestire chi può invitare gli ospiti](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="81cba-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
    <span data-ttu-id="81cba-139">Per altre informazioni su come controllare chi può invitare guest, consultare [Delegare gli inviti per Collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="81cba-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="81cba-140">Passaggio 3: configurare i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="81cba-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="81cba-141">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > **Servizi &** > gruppi di componenti aggiuntivi di**Office 365**.</span><span class="sxs-lookup"><span data-stu-id="81cba-141">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="81cba-142">Assicurarsi che **i membri del gruppo al di fuori del contenuto del gruppo di Access dell'organizzazione** siano impostati **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="81cba-142">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="81cba-143">Se questa impostazione è disattivata, gli utenti non saranno in grado di accedere a qualsiasi contenuto di gruppo.</span><span class="sxs-lookup"><span data-stu-id="81cba-143">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="81cba-144">Assicurarsi che **i proprietari del gruppo aggiungano persone all'esterno dell'organizzazione a gruppi** sia impostato **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="81cba-144">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="81cba-145">Se questa impostazione è disattivata, i proprietari del team non saranno in grado di aggiungere nuovi Guest.</span><span class="sxs-lookup"><span data-stu-id="81cba-145">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="81cba-146">Questa impostazione deve essere almeno attiva per supportare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="81cba-146">At a minimum, this setting must be On to support guest access.</span></span>

     ![La schermata mostra i gruppi di Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="81cba-148">Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="81cba-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="81cba-149">Passaggio 4: configurare la condivisione in Office 365</span><span class="sxs-lookup"><span data-stu-id="81cba-149">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="81cba-150">Assicurarsi che gli utenti possano aggiungere Guest.</span><span class="sxs-lookup"><span data-stu-id="81cba-150">Make sure that users can add guests.</span></span> <span data-ttu-id="81cba-151">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="81cba-151">Here's how:</span></span>

1. <span data-ttu-id="81cba-152">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > di**sicurezza & privacy**.</span><span class="sxs-lookup"><span data-stu-id="81cba-152">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="81cba-154">In **condivisione**selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="81cba-154">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="81cba-156">Impostare **consentire agli utenti di aggiungere nuovi Guest a questa organizzazione** e quindi fare clic **su** **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81cba-156">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > <span data-ttu-id="81cba-158">Questa impostazione è equivalente ai **membri che possono invitare** l'impostazione in **Impostazioni** > utente**utenti esterni** in Azure ad.</span><span class="sxs-lookup"><span data-stu-id="81cba-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="81cba-159">Passaggio 5: verificare l'impostazione di condivisione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="81cba-159">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="81cba-160">Questo è un po' un rompicapo.</span><span class="sxs-lookup"><span data-stu-id="81cba-160">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="81cba-161">L'accesso guest in teams non funziona se l'opzione **non consentire la condivisione all'esterno dell'organizzazione** è selezionata nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81cba-161">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="81cba-162">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81cba-162">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="81cba-163">Fare clic su interfaccia di **Amministrazione**e quindi selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="81cba-163">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="81cba-164">Nell'interfaccia di amministrazione di SharePoint selezionare **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="81cba-164">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="81cba-165">Verificare che l'opzione **non consentire la condivisione all'esterno** dell'organizzazione *non* sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="81cba-165">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![La schermata mostra un esempio di attivazione di impostazioni online di SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="81cba-167">Passaggio 6: configurare le autorizzazioni per gli utenti Guest</span><span class="sxs-lookup"><span data-stu-id="81cba-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="81cba-168">Nell'applicazione teams, a livello di team specifico, configura le autorizzazioni guest che controllano se gli utenti possono creare, aggiornare o eliminare canali.</span><span class="sxs-lookup"><span data-stu-id="81cba-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="81cba-169">Gli amministratori dei team e i proprietari del team possono configurare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="81cba-169">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot mostra un esempio di attivazione di impostazioni del team/canale](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="81cba-171">Per ulteriori informazioni sull'accesso guest, vedere [accesso guest in teams](guest-access.md) e [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="81cba-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="81cba-172">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="81cba-172">Troubleshooting</span></span>

<span data-ttu-id="81cba-173">In caso di problemi con l'impostazione dell'accesso guest o l'aggiunta di ospiti in teams, usare queste risorse per aiutarti:</span><span class="sxs-lookup"><span data-stu-id="81cba-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="81cba-174">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81cba-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="81cba-175">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="81cba-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



