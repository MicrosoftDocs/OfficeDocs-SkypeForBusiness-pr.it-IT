---
title: Installare, gestire e assegnare autorizzazioni per l'app teams Learning (anteprima privata)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Usare l'app Microsoft teams learning per creare un hub centrale per l'apprendimento in cui i dipendenti possono condividere, assegnare e imparare dalle raccolte di contenuti in un'organizzazione.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703457"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="556a2-103">Installare, gestire e assegnare autorizzazioni per l'app teams Learning (anteprima privata)</span><span class="sxs-lookup"><span data-stu-id="556a2-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="556a2-104">*Questo articolo contiene contenuto preliminare per l'app teams Learning, che si trova in anteprima privata.*</span><span class="sxs-lookup"><span data-stu-id="556a2-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="556a2-105">L'app Microsoft teams Learning (private Preview) autorizza i team e gli utenti dell'organizzazione a rendere l'apprendimento una parte naturale della loro giornata.</span><span class="sxs-lookup"><span data-stu-id="556a2-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="556a2-106">L'app crea un hub centrale in teams in cui i dipendenti possono condividere, assegnare e imparare dalle raccolte di contenuti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="556a2-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="556a2-107">Gli amministratori impostano le autorizzazioni e consentono l'apprendimento delle origini contenuto per l'app.</span><span class="sxs-lookup"><span data-stu-id="556a2-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="556a2-108">Il contenuto di apprendimento può includere LinkedIn Learning, Microsoft Learn, Microsoft 365 training, il contenuto dell'organizzazione archiviato in SharePoint Online e i provider di terze parti supportati dall'app.</span><span class="sxs-lookup"><span data-stu-id="556a2-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="556a2-109">Per configurare l'app teams Learning (private Preview), è necessario coinvolgere:</span><span class="sxs-lookup"><span data-stu-id="556a2-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="556a2-110">Amministratore dell'interfaccia di amministrazione Teams</span><span class="sxs-lookup"><span data-stu-id="556a2-110">Teams admin center admin</span></span>
-   <span data-ttu-id="556a2-111">Amministratore dell'interfaccia di amministrazione di Microsoft 365, ovvero Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="556a2-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="556a2-112">Knowledge admin (un nuovo ruolo nell'interfaccia di amministrazione di Microsoft 365 che un amministratore globale (noto anche come amministratore IT o amministratore di Microsoft 365) può assegnare a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="556a2-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="556a2-113">Questo ruolo gestisce le origini dei contenuti di apprendimento dell'organizzazione tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="556a2-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="556a2-114">Gestire l'app teams Learning (private Preview) nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="556a2-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="556a2-115">L'amministratore di teams installa l'app teams Learning (private Preview) dall'App Store e applica i criteri di configurazione, gestione e autorizzazioni dell'app tramite l'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="556a2-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="556a2-116">Gestire l'app teams Learning (anteprima privata)</span><span class="sxs-lookup"><span data-stu-id="556a2-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="556a2-117">Per gestire le impostazioni per l'app, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="556a2-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="556a2-118">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.</span><span class="sxs-lookup"><span data-stu-id="556a2-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Spostamento a sinistra nell'interfaccia di amministrazione di teams che mostra le app team e Gestisci la sezione app](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="556a2-120">Nella casella di ricerca della pagina **Manage Apps** Digitare *Learning* per cercare l'app teams Learning (private Preview).</span><span class="sxs-lookup"><span data-stu-id="556a2-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Pagina Gestisci app nell'interfaccia di amministrazione di teams che mostra la casella di ricerca](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="556a2-122">Nella pagina **apprendimento** :</span><span class="sxs-lookup"><span data-stu-id="556a2-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="556a2-123">In **stato** selezionare **consentito** per attivare l'app.</span><span class="sxs-lookup"><span data-stu-id="556a2-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="556a2-124">Nella sezione **impostazioni app** della scheda **Impostazioni** accedere all'interfaccia di amministrazione di Microsoft 365 per configurare le origini del contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="556a2-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Pagina di apprendimento nell'interfaccia di amministrazione di teams che mostra lo stato e la sezione Impostazioni app](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="556a2-126">Dopo aver gestito le impostazioni dell' **app** , passa a **autorizzazioni e criteri di configurazione** per concedere l'autorizzazione ai dipendenti che devono avere accesso all'app come parte della partecipazione dell'organizzazione all'anteprima privata.</span><span class="sxs-lookup"><span data-stu-id="556a2-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="556a2-127">Se l'organizzazione è in Ring 4,0 come parte del programma teams TAP100, potrebbe essere necessario eseguire le operazioni seguenti per consentire agli utenti approvati in Ring 3,0 di accedere all'app per l'apprendimento dei team (anteprima privata).</span><span class="sxs-lookup"><span data-stu-id="556a2-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="556a2-128">Nell'ambito dell'anteprima privata, l'app teams Learning (private Preview) viene rilasciata in Ring 3,0.</span><span class="sxs-lookup"><span data-stu-id="556a2-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="556a2-129">Se l'organizzazione è in Ring 4,0, l'app non viene visualizzata nell'App Store.</span><span class="sxs-lookup"><span data-stu-id="556a2-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="556a2-130">Per testare l'app, devi creare un criterio di autorizzazione per le app personalizzate, impostarlo per **consentire tutte le app** e assegnarlo agli utenti approvati di Ring 3,0.</span><span class="sxs-lookup"><span data-stu-id="556a2-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![TOCCARE-AppsPermission-plcy pagina che mostra Consenti tutte le app selezionate](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="556a2-132">Configurare le origini di contenuto per l'apprendimento nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="556a2-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="556a2-133">Gli amministratori dell'interfaccia di amministrazione di Microsoft 365, da sole o assegnando il ruolo di amministratore della conoscenza agli utenti selezionati nell'organizzazione, possono gestire le impostazioni relative all'app per l'apprendimento dei team (anteprima privata) e possono configurare le origini del contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="556a2-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="556a2-134">L'amministratore della Knowledge deve essere moderatamente tecnico e avere le credenziali di amministratore di SharePoint esistenti, preferibilmente una persona esperta nella parte dell'organizzazione per l'istruzione, l'apprendimento, la formazione o i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="556a2-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="556a2-135">L'amministratore seleziona le origini di contenuto per l'apprendimento (come LinkedIn Learning o SharePoint) sarà disponibile nell'app.</span><span class="sxs-lookup"><span data-stu-id="556a2-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="556a2-136">L'amministratore configura quindi tali origini per verificare che il contenuto sia disponibile per la ricerca e l'individuazione e possa essere esplorato dai dipendenti che usano l'app.</span><span class="sxs-lookup"><span data-stu-id="556a2-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="556a2-137">Assegnare il ruolo di amministratore della conoscenza [facoltativo]</span><span class="sxs-lookup"><span data-stu-id="556a2-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="556a2-138">Questi passaggi devono essere eseguiti dall'amministratore per l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="556a2-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="556a2-139">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365 passa a **ruoli**.</span><span class="sxs-lookup"><span data-stu-id="556a2-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="556a2-140">Nella scheda **Azure ad** della pagina **roles** selezionare **Knowledge admin**.</span><span class="sxs-lookup"><span data-stu-id="556a2-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="556a2-141">Nella sezione **amministratori assegnati** della pagina **Knowledge admin** selezionare **Aggiungi** e quindi aggiungere la persona scelta per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="556a2-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="556a2-142">Configurare le impostazioni per le origini del contenuto di apprendimento per l'app</span><span class="sxs-lookup"><span data-stu-id="556a2-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="556a2-143">Questa procedura deve essere eseguita dall'amministratore di Microsoft 365 o dall'amministratore della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="556a2-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="556a2-144">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere alle impostazioni dell'organizzazione delle **Impostazioni**  >  .</span><span class="sxs-lookup"><span data-stu-id="556a2-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="556a2-145">Nella scheda **servizi & componenti** aggiuntivi della pagina **Impostazioni** selezionare **apprendimento app**.</span><span class="sxs-lookup"><span data-stu-id="556a2-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Pagina impostazioni nell'interfaccia di amministrazione di Microsoft 365 che mostra l'app di apprendimento elencata](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="556a2-147">Nel pannello **app Learning** selezionare le origini di contenuto di apprendimento che si desidera configurare per l'organizzazione e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="556a2-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Pannello delle app di apprendimento nell'interfaccia di amministrazione di Microsoft 365 che mostra le opzioni di origini contenuto](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="556a2-149">Tra tutte le fonti di apprendimento esistenti, alcune verranno abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="556a2-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="556a2-150">Questi includono:</span><span class="sxs-lookup"><span data-stu-id="556a2-150">These include:</span></span>

- <span data-ttu-id="556a2-151">LinkedIn Learning (contenuto gratuito)</span><span class="sxs-lookup"><span data-stu-id="556a2-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="556a2-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="556a2-152">Microsoft Learn</span></span>
- <span data-ttu-id="556a2-153">Formazione su Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="556a2-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="556a2-154">Se l'organizzazione ha un abbonamento a LinkedIn Learning standard o Pro, il repository di contenuti verrà sbloccato per i dipendenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="556a2-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="556a2-155">Solo i dipendenti che hanno l'autorizzazione saranno in grado di usare l'intero repository di contenuto.</span><span class="sxs-lookup"><span data-stu-id="556a2-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="556a2-156">Potrebbe essere necessario abilitare o configurare altre origini manualmente.</span><span class="sxs-lookup"><span data-stu-id="556a2-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="556a2-157">Le fonti di apprendimento non provenienti da Microsoft sono concesse in licenza separatamente tra l'organizzazione e la terza parte.</span><span class="sxs-lookup"><span data-stu-id="556a2-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="556a2-158">È necessario verificare di aver effettuato l'iscrizione per l'apprendimento per l'utente e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="556a2-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="556a2-159">Per abilitare o disabilitare un'origine di contenuto di apprendimento, selezionare la casella di controllo accanto all'origine.</span><span class="sxs-lookup"><span data-stu-id="556a2-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="556a2-160">Se è abilitata un'origine, un segno di spunta sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="556a2-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="556a2-161">Configurare SharePoint come origine del contenuto di apprendimento</span><span class="sxs-lookup"><span data-stu-id="556a2-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="556a2-162">È possibile configurare SharePoint come origine del contenuto di apprendimento per l'app teams Learning (private Preview) nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="556a2-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="556a2-163">Panoramica</span><span class="sxs-lookup"><span data-stu-id="556a2-163">Overview</span></span>

<span data-ttu-id="556a2-164">L'amministratore della Knowledge fornisce un URL del sito in cui il servizio di apprendimento può creare un repository di contenuti di apprendimento centralizzato vuoto sotto forma di un elenco di SharePoint strutturato.</span><span class="sxs-lookup"><span data-stu-id="556a2-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="556a2-165">Questo elenco può essere usato dall'organizzazione per ospitare i collegamenti a cartelle di SharePoint tra società che contengono contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="556a2-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="556a2-166">Gli amministratori sono responsabili della raccolta e della cura di un elenco di URL per le cartelle.</span><span class="sxs-lookup"><span data-stu-id="556a2-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="556a2-167">Queste cartelle devono includere solo il contenuto che può essere reso disponibile nell'app per l'apprendimento di Teams (private Preview).</span><span class="sxs-lookup"><span data-stu-id="556a2-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="556a2-168">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="556a2-168">Permissions</span></span>

<span data-ttu-id="556a2-169">Gli URL delle cartelle possono essere raccolti da qualsiasi sito di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="556a2-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="556a2-170">Qualsiasi contenuto all'interno di queste cartelle sarà ricercabile, ma solo il contenuto a cui può essere usato il singolo dipendente ha le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="556a2-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="556a2-171">Servizio di apprendimento</span><span class="sxs-lookup"><span data-stu-id="556a2-171">Learning Service</span></span>

<span data-ttu-id="556a2-172">Il servizio di apprendimento usa gli URL della cartella forniti per ottenere metadati da tutto il contenuto archiviato in tali cartelle.</span><span class="sxs-lookup"><span data-stu-id="556a2-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="556a2-173">Entro 24 ore dall'approvvigionamento dell'URL della cartella nel repository centralizzato, i dipendenti possono cercare e usare il contenuto della società nell'app.</span><span class="sxs-lookup"><span data-stu-id="556a2-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="556a2-174">L'eliminazione del contenuto dal repository non è supportata a questo punto.</span><span class="sxs-lookup"><span data-stu-id="556a2-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="556a2-175">Il contenuto con superficie involontaria può essere rimosso solo fornendo un nuovo URL del sito di SharePoint nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="556a2-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="556a2-176">Configurare SharePoint come origine</span><span class="sxs-lookup"><span data-stu-id="556a2-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="556a2-177">Questi passaggi devono essere eseguiti dall'amministratore di Microsoft 365 o dall'amministratore della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="556a2-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="556a2-178">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="556a2-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="556a2-179">Nella scheda **servizi & componenti** aggiuntivi della pagina **Impostazioni** selezionare **apprendimento app**.</span><span class="sxs-lookup"><span data-stu-id="556a2-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Pagina impostazioni nell'interfaccia di amministrazione di Microsoft 365 che mostra l'app di apprendimento elencata](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="556a2-181">Nel pannello **app Learning** fornisci l'URL del sito al sito di SharePoint in cui vuoi che l'app crei un repository centralizzato.</span><span class="sxs-lookup"><span data-stu-id="556a2-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Pannello delle app di apprendimento nell'interfaccia di amministrazione di Microsoft 365 che mostra SharePoint selezionato](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="556a2-183">Un elenco di SharePoint viene creato automaticamente nel sito di SharePoint dell'organizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="556a2-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="556a2-184">Nella barra di spostamento sinistra del sito di SharePoint selezionare **learning content app repository**.</span><span class="sxs-lookup"><span data-stu-id="556a2-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Spostamento a sinistra in SharePoint che mostra la sezione del repository del contenuto dell'app Learning](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="556a2-186">Nella pagina **Learning app content repository** compilare l'elenco di SharePoint con gli URL per le cartelle del contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="556a2-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="556a2-187">Selezionare **nuovo** per visualizzare il pannello **nuovo elemento** .</span><span class="sxs-lookup"><span data-stu-id="556a2-187">Select **New** to view the **New item** panel.</span></span> 

   ![Pagina del repository del contenuto dell'app di apprendimento in SharePoint che mostra la nuova opzione](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="556a2-189">Nel riquadro **nuovo elemento** , nel campo **titolo** , aggiungere il nome della directory desiderata.</span><span class="sxs-lookup"><span data-stu-id="556a2-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="556a2-190">Nel campo **URL cartella** aggiungere l'URL alla cartella contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="556a2-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="556a2-191">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="556a2-191">Select **Save**.</span></span>

   ![Pannello nuovo elemento in SharePoint che mostra i campi titolo e URL cartella](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="556a2-193">La pagina del repository del contenuto dell'app Learning viene aggiornata con il nuovo contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="556a2-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Pagina del repository del contenuto dell'app di apprendimento in SharePoint che mostra le informazioni aggiornate](media/learning-app-content-repository-populated.png)


 


