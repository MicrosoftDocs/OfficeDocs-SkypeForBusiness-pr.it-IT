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
ms.openlocfilehash: e7f019f2260b1e86b422f8b4238439fbd2f1607a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569543"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="8692e-103">Elenco di controllo di accesso Guest Teams</span><span class="sxs-lookup"><span data-stu-id="8692e-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="8692e-104">Usare questo elenco di controllo per abilitare e configurare la caratteristica di accesso guest in Microsoft teams in base alle preferenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8692e-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="8692e-105">Per le limitazioni della collaborazione [, vedere Abilitare la collaborazione esterna B2B e gestire chi può invitare Guest](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="8692e-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="8692e-106">Informazioni sulle limitazioni per gli utenti</span><span class="sxs-lookup"><span data-stu-id="8692e-106">Understand the limitations for guests</span></span>

<span data-ttu-id="8692e-107">L'esperienza Guest ha limitazioni per progettazione.</span><span class="sxs-lookup"><span data-stu-id="8692e-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="8692e-108">Assicurarsi di comprendere l'esperienza Guest in modo che non si tenti di risolvere un problema.</span><span class="sxs-lookup"><span data-stu-id="8692e-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="8692e-109">Ecco, ad esempio, un elenco di alcune delle funzionalità che non sono disponibili per un guest in Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="8692e-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="8692e-110">OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="8692e-110">OneDrive for Business</span></span>
- <span data-ttu-id="8692e-111">Ricerca utenti esterni a teams</span><span class="sxs-lookup"><span data-stu-id="8692e-111">People search outside of Teams</span></span>
- <span data-ttu-id="8692e-112">Calendario, riunioni pianificate o dettagli riunione</span><span class="sxs-lookup"><span data-stu-id="8692e-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="8692e-113">PSTN</span><span class="sxs-lookup"><span data-stu-id="8692e-113">PSTN</span></span>
- <span data-ttu-id="8692e-114">Organigramma</span><span class="sxs-lookup"><span data-stu-id="8692e-114">Organization chart</span></span>
- <span data-ttu-id="8692e-115">Creare o modificare un team</span><span class="sxs-lookup"><span data-stu-id="8692e-115">Create or revise a team</span></span>
- <span data-ttu-id="8692e-116">Cercare un team</span><span class="sxs-lookup"><span data-stu-id="8692e-116">Browse for a team</span></span>
- <span data-ttu-id="8692e-117">Caricare file in una chat utente</span><span class="sxs-lookup"><span data-stu-id="8692e-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="8692e-118">Gli utenti possono continuare a cercare e trovare un utente (al di fuori del proprio team) se conoscono l'ID della posta elettronica completa.</span><span class="sxs-lookup"><span data-stu-id="8692e-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="8692e-119">Per evitare questo problema, gli amministratori possono usare modelli come la [ricerca di directory con ambito](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) che hanno la possibilità di limitare gli ospiti al proprio GAL virtuale.</span><span class="sxs-lookup"><span data-stu-id="8692e-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="8692e-120">Per altri dettagli, vedere [l'esperienza Guest](guest-experience.md) e l' [accesso guest nei gruppi di Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="8692e-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="8692e-121">Accesso guest e accesso esterno (Federazione)</span><span class="sxs-lookup"><span data-stu-id="8692e-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="8692e-122">Attualmente Microsoft teams non supporta il ruolo di invitato Guest.</span><span class="sxs-lookup"><span data-stu-id="8692e-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="8692e-123">Almeno l'opzione "i membri possono invitare" deve essere impostata su "Sì" per consentire l'accesso Guest al lavoro in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8692e-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="8692e-124">Se si imposta "i membri possono invitare" a "No" e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="8692e-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="8692e-125">Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team.</span><span class="sxs-lookup"><span data-stu-id="8692e-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="8692e-126">Se i clienti vedono gli errori di licenza</span><span class="sxs-lookup"><span data-stu-id="8692e-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="8692e-127">L'accesso guest in Microsoft teams USA Azure Active Directory (Azure AD) business to business (B2B) e il relativo modello di licenza.</span><span class="sxs-lookup"><span data-stu-id="8692e-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="8692e-128">Se si verificano errori di licenza, leggere le istruzioni per la gestione delle licenze [B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per comprendere i requisiti di licenza dell'organizzazione in modo che gli utenti siano in grado di invitare gli ospiti alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8692e-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="8692e-129">Alcuni aspetti da ricordare:</span><span class="sxs-lookup"><span data-stu-id="8692e-129">A few things to remember:</span></span>

- <span data-ttu-id="8692e-130">Gli ospiti sono utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8692e-130">Guests are users outside your organization.</span></span> <span data-ttu-id="8692e-131">I dipendenti, gli appaltatori onsite, gli agenti onsite e così via non possono essere aggiunti come Guest.</span><span class="sxs-lookup"><span data-stu-id="8692e-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="8692e-132">Lo stesso vale per gli affiliati.</span><span class="sxs-lookup"><span data-stu-id="8692e-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="8692e-133">Le licenze Guest vengono conteggiate con l'organizzazione invitante.</span><span class="sxs-lookup"><span data-stu-id="8692e-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="8692e-134">Considerate questa operazione quando si calcola il numero di licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="8692e-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="8692e-135">Le licenze vengono conteggiate in base all'organizzazione se gli ospiti invitati provengono da un altro tenant di Office 365 o usano gli indirizzi di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="8692e-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="8692e-136">□ Passaggio 1: configurare le impostazioni in Azure AD business-to-business</span><span class="sxs-lookup"><span data-stu-id="8692e-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="8692e-137">Accedere a [Azure Portal](https://portal.azure.com) come amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="8692e-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="8692e-138">Selezionare\*\*\*\* > **le impostazioni utente**di **Azure Active Directory** > Users.</span><span class="sxs-lookup"><span data-stu-id="8692e-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="8692e-139">In **utenti esterni**selezionare **Gestisci impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="8692e-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8692e-140">Le **impostazioni di collaborazione esterna** sono disponibili anche nella pagina **relazioni organizzative** .</span><span class="sxs-lookup"><span data-stu-id="8692e-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="8692e-141">In Azure Active Directory, in **Gestisci**, passa a > **Impostazioni** **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="8692e-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="8692e-142">Nella pagina **impostazioni di collaborazione esterna** scegliere i criteri che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="8692e-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="8692e-143">Le **autorizzazioni degli utenti Guest sono limitate**: questo criterio determina le autorizzazioni per gli ospiti nella directory.</span><span class="sxs-lookup"><span data-stu-id="8692e-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="8692e-144">Selezionare **Sì** per bloccare gli ospiti da determinate attività di directory, come l'enumerazione di utenti, gruppi o altre risorse di directory.</span><span class="sxs-lookup"><span data-stu-id="8692e-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="8692e-145">Selezionare **No** per offrire agli ospiti lo stesso accesso ai dati della directory come utenti regolari nella directory.</span><span class="sxs-lookup"><span data-stu-id="8692e-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="8692e-146">Gli **amministratori e gli utenti del ruolo dell'invitato Guest possono invitare**: per consentire agli amministratori e agli utenti del ruolo "Guest invite" di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8692e-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="8692e-147">**I membri possono invitare**: per consentire ai membri non amministratori della directory di invitare gli ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8692e-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="8692e-148">Se si impostano **membri può invitare** a **No** e quindi abilitare l'accesso guest nei gruppi di Office 365 e Microsoft teams, gli amministratori possono controllare gli inviti Guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="8692e-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="8692e-149">Dopo che gli ospiti si trovano nella directory, possono essere aggiunti ai team da membri non amministratori che sono proprietari del team.</span><span class="sxs-lookup"><span data-stu-id="8692e-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="8692e-150">Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="8692e-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="8692e-151">**Gli ospiti possono invitare**: per consentire agli ospiti di invitare altri ospiti, impostare questo criterio su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8692e-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="8692e-152">**Abilitare la password unica per gli utenti (anteprima)**: per altre informazioni sulla funzionalità di codice per la sola volta, vedere autenticazione di un codice di accesso unico per la [posta elettronica (anteprima)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="8692e-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>

   - <span data-ttu-id="8692e-153">**Limitazioni della collaborazione**: per altre informazioni su come consentire o bloccare gli inviti a specifici domini, vedere [consentire o bloccare gli inviti agli utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="8692e-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
    
## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="8692e-154">□ Passaggio 2: configurare i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="8692e-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="8692e-155">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > **Servizi &** > gruppi di componenti aggiuntivi di**Office 365**.</span><span class="sxs-lookup"><span data-stu-id="8692e-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="8692e-156">Assicurarsi che **i membri del gruppo al di fuori del contenuto del gruppo di Access dell'organizzazione** siano impostati **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="8692e-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="8692e-157">Se questa impostazione è disattivata, gli utenti non saranno in grado di accedere a qualsiasi contenuto di gruppo.</span><span class="sxs-lookup"><span data-stu-id="8692e-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="8692e-158">Assicurarsi che **i proprietari del gruppo aggiungano persone all'esterno dell'organizzazione a gruppi** sia impostato **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="8692e-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="8692e-159">Se questa impostazione è disattivata, i proprietari del team non saranno in grado di aggiungere nuovi Guest.</span><span class="sxs-lookup"><span data-stu-id="8692e-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="8692e-160">Questa impostazione deve essere almeno attiva per supportare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="8692e-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![La schermata mostra i gruppi di Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="8692e-162">Per istruzioni dettagliate sulla configurazione di queste impostazioni, vedere [gestire l'accesso guest nei gruppi di office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controllare l'accesso guest nei gruppi di Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="8692e-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="8692e-163">□ Passaggio 3: abilitare l'accesso Guest a livello di tenant</span><span class="sxs-lookup"><span data-stu-id="8692e-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="8692e-164">È necessario attivare l'accesso guest per Microsoft teams sotto l'interfaccia di **amministrazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="8692e-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="8692e-165">Nell'interfaccia di amministrazione di teams selezionare**l'accesso Guest** **delle impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8692e-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="8692e-166">Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="8692e-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot mostra un esempio di attivazione di impostazioni team](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="8692e-168">Nella stessa pagina Configurare le altre impostazioni Guest necessarie.</span><span class="sxs-lookup"><span data-stu-id="8692e-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="8692e-169">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8692e-169">Click **Save**.</span></span>

<span data-ttu-id="8692e-170">Per istruzioni dettagliate, vedere [attivare o disattivare l'accesso Guest a Microsoft teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="8692e-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="8692e-171">□ Passaggio 4: configurare la condivisione in Office 365</span><span class="sxs-lookup"><span data-stu-id="8692e-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="8692e-172">Assicurarsi che gli utenti possano aggiungere Guest.</span><span class="sxs-lookup"><span data-stu-id="8692e-172">Make sure that users can add guests.</span></span> <span data-ttu-id="8692e-173">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="8692e-173">Here's how:</span></span>

1. <span data-ttu-id="8692e-174">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Impostazioni** > di**sicurezza & privacy**.</span><span class="sxs-lookup"><span data-stu-id="8692e-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot mostra un esempio di impostazioni dei servizi](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="8692e-176">In **condivisione**selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="8692e-176">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="8692e-178">Impostare **consentire agli utenti di aggiungere nuovi Guest a questa organizzazione** e quindi fare clic **su** **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8692e-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot mostra un esempio di attivazione di impostazioni di condivisione](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="8692e-180">Questa impostazione è equivalente ai **membri che possono invitare** l'impostazione in **Impostazioni** > utente**utenti esterni** in Azure ad.</span><span class="sxs-lookup"><span data-stu-id="8692e-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="8692e-181">□ Passaggio 5: verificare l'impostazione di condivisione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="8692e-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="8692e-182">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8692e-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="8692e-183">Fare clic su interfaccia di **Amministrazione**e quindi selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8692e-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="8692e-184">Nell'interfaccia di amministrazione di SharePoint selezionare **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="8692e-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="8692e-185">Verificare che l'opzione **non consentire la condivisione all'esterno** dell'organizzazione *non* sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8692e-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![La schermata mostra un esempio di attivazione di impostazioni online di SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="8692e-187">□ Passaggio 6: abilitare impostazioni specifiche per i canali</span><span class="sxs-lookup"><span data-stu-id="8692e-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="8692e-188">Nell'applicazione teams, a livello di team specifico, configura le autorizzazioni guest in modo che gli utenti possano creare, aggiornare ed eliminare canali.</span><span class="sxs-lookup"><span data-stu-id="8692e-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="8692e-189">Oltre agli amministratori, i proprietari del team possono configurare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="8692e-189">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot mostra un esempio di attivazione di impostazioni del team/canale](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="8692e-191">Per altre informazioni, inclusi i video di How-to, vedere [accesso guest in Microsoft teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="8692e-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="8692e-192">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8692e-192">Troubleshooting</span></span>

<span data-ttu-id="8692e-193">In caso di problemi con l'aggiunta di Guest in Microsoft teams, vedere la [Guida alla risoluzione dei problemi relativi a Access](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="8692e-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


