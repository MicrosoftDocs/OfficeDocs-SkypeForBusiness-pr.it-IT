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
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753321"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="3ce76-103">Elenco di controllo di accesso guest di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ce76-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="3ce76-104">Usare questo elenco di controllo per attivare e configurare l'accesso guest in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="3ce76-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ce76-105">Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="3ce76-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="3ce76-106">Passaggio 1: attivare l'accesso Guest a livello di organizzazione Teams</span><span class="sxs-lookup"><span data-stu-id="3ce76-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="3ce76-107">Per attivare l'accesso guest, accedere all'interfaccia di **amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="3ce76-108">Nell'interfaccia di amministrazione di teams selezionare**l'accesso Guest** **delle impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ce76-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="3ce76-109">Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="3ce76-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot mostra un esempio di attivazione di impostazioni team](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="3ce76-111">Nella stessa pagina attivare o disattivare le impostazioni di **chiamata**, **riunione**e **messaggistica** per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3ce76-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="3ce76-112">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="3ce76-113">Se si usano le impostazioni predefinite in Azure Active Directory, SharePoint Online e Office 365 groups, è possibile che sia stata eseguita la configurazione dell'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="3ce76-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="3ce76-114">In questo caso, è possibile ignorare il resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="3ce76-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="3ce76-115">In caso di dubbi o se si usano impostazioni personalizzate per i gruppi AAD, SharePoint Online o Office 365, procedere con il resto della procedura descritta in questo elenco di controllo.</span><span class="sxs-lookup"><span data-stu-id="3ce76-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="3ce76-116">Passaggio 2: configurare le impostazioni di Azure AD business-to-business</span><span class="sxs-lookup"><span data-stu-id="3ce76-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="3ce76-117">Accedere a [Azure Portal](https://portal.azure.com) come amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="3ce76-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="3ce76-118">Selezionare\*\*\*\* > **le impostazioni utente**di **Azure Active Directory** > Users.</span><span class="sxs-lookup"><span data-stu-id="3ce76-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="3ce76-119">In **utenti esterni**selezionare **Gestisci impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3ce76-120">Le **impostazioni di collaborazione esterna** sono disponibili anche nella pagina **relazioni organizzative** .</span><span class="sxs-lookup"><span data-stu-id="3ce76-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="3ce76-121">In Azure Active Directory, in **Gestisci**, passa a > **Impostazioni** **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="3ce76-122">Nella pagina **impostazioni di collaborazione esterna** scegliere i criteri che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="3ce76-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="3ce76-123">Le **autorizzazioni degli utenti Guest sono limitate**: questo criterio determina le autorizzazioni per gli ospiti nella directory.</span><span class="sxs-lookup"><span data-stu-id="3ce76-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="3ce76-124">Selezionare **Sì** per bloccare gli ospiti da determinate attività di directory, come l'enumerazione di utenti, gruppi o altre risorse di directory.</span><span class="sxs-lookup"><span data-stu-id="3ce76-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="3ce76-125">Selezionare **No** per offrire agli ospiti lo stesso accesso ai dati della directory come utenti regolari nella directory.</span><span class="sxs-lookup"><span data-stu-id="3ce76-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="3ce76-126">Gli **amministratori e gli utenti del ruolo dell'invitato Guest possono invitare**: per consentire agli amministratori e agli utenti del ruolo "Guest invite" di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="3ce76-127">**I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="3ce76-128">Se si impostano **membri può invitare** a **No** e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="3ce76-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="3ce76-129">Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team.</span><span class="sxs-lookup"><span data-stu-id="3ce76-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="3ce76-130">Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="3ce76-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="3ce76-131">Per consentire agli utenti di accedere al lavoro in teams, è necessario impostare **i membri può invitare** a **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="3ce76-132">**Gli ospiti possono invitare**: per consentire agli ospiti di invitare altri ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="3ce76-133">Attualmente, teams non supporta il ruolo di invitato Guest, quindi, anche se si imposta **gli ospiti possono invitare** a **Sì**, gli utenti non possono invitare altri ospiti in teams.</span><span class="sxs-lookup"><span data-stu-id="3ce76-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="3ce76-134">**Abilitare la password unica per gli utenti (anteprima)**: per altre informazioni sulla funzionalità di codice per la sola volta, vedere autenticazione di un codice di accesso unico per la [posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="3ce76-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="3ce76-135">**Limitazioni della collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a specifici domini, vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="3ce76-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="3ce76-136">Per le limitazioni della collaborazione, vedere [abilitare la collaborazione esterna B2B e gestire chi può invitare gli ospiti](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="3ce76-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="3ce76-137">Per altre informazioni su come controllare chi può invitare gli ospiti, vedere [delegare gli inviti per la collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="3ce76-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="3ce76-138">Passaggio 3: configurare i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="3ce76-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="3ce76-139">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > **Servizi &** > gruppi di componenti aggiuntivi di**Office 365**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="3ce76-140">Assicurarsi che **i membri del gruppo al di fuori del contenuto del gruppo di Access dell'organizzazione** siano impostati **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="3ce76-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="3ce76-141">Se questa impostazione è disattivata, gli utenti non saranno in grado di accedere a qualsiasi contenuto di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3ce76-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="3ce76-142">Assicurarsi che **i proprietari del gruppo aggiungano persone all'esterno dell'organizzazione a gruppi** sia impostato **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="3ce76-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="3ce76-143">Se questa impostazione è disattivata, i proprietari del team non saranno in grado di aggiungere nuovi Guest.</span><span class="sxs-lookup"><span data-stu-id="3ce76-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="3ce76-144">Questa impostazione deve essere almeno attiva per supportare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="3ce76-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![La schermata mostra i gruppi di Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="3ce76-146">Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="3ce76-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="3ce76-147">Passaggio 4: configurare la condivisione in Office 365</span><span class="sxs-lookup"><span data-stu-id="3ce76-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="3ce76-148">Assicurarsi che gli utenti possano aggiungere Guest.</span><span class="sxs-lookup"><span data-stu-id="3ce76-148">Make sure that users can add guests.</span></span> <span data-ttu-id="3ce76-149">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="3ce76-149">Here's how:</span></span>

1. <span data-ttu-id="3ce76-150">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > di**sicurezza & privacy**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="3ce76-152">In **condivisione**selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-152">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="3ce76-154">Impostare **consentire agli utenti di aggiungere nuovi Guest a questa organizzazione** e quindi fare clic **su** **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="3ce76-156">Questa impostazione è equivalente ai **membri che possono invitare** l'impostazione in **Impostazioni** > utente**utenti esterni** in Azure ad.</span><span class="sxs-lookup"><span data-stu-id="3ce76-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="3ce76-157">Passaggio 5: verificare l'impostazione di condivisione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="3ce76-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="3ce76-158">Questo è un po' un rompicapo.</span><span class="sxs-lookup"><span data-stu-id="3ce76-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="3ce76-159">L'accesso guest in teams non funziona se l'opzione **non consentire la condivisione all'esterno dell'organizzazione** è selezionata nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3ce76-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="3ce76-160">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ce76-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="3ce76-161">Fare clic su interfaccia di **Amministrazione**e quindi selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="3ce76-162">Nell'interfaccia di amministrazione di SharePoint selezionare **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="3ce76-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="3ce76-163">Verificare che l'opzione **non consentire la condivisione all'esterno** dell'organizzazione *non* sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="3ce76-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![La schermata mostra un esempio di attivazione di impostazioni online di SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="3ce76-165">Passaggio 6: configurare le autorizzazioni per gli utenti Guest</span><span class="sxs-lookup"><span data-stu-id="3ce76-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="3ce76-166">Nell'applicazione teams, a livello di team specifico, configura le autorizzazioni guest che controllano se gli utenti possono creare, aggiornare o eliminare canali.</span><span class="sxs-lookup"><span data-stu-id="3ce76-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="3ce76-167">Gli amministratori dei team e i proprietari del team possono configurare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3ce76-167">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot mostra un esempio di attivazione di impostazioni del team/canale](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="3ce76-169">Per ulteriori informazioni sull'accesso guest, vedere [accesso guest in teams](guest-access.md) e [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="3ce76-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="3ce76-170">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3ce76-170">Troubleshooting</span></span>

<span data-ttu-id="3ce76-171">In caso di problemi con l'impostazione dell'accesso guest o l'aggiunta di ospiti in teams, usare queste risorse per aiutarti:</span><span class="sxs-lookup"><span data-stu-id="3ce76-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="3ce76-172">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ce76-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="3ce76-173">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="3ce76-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



