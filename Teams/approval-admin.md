---
title: Disponibilità dell'applicazione Approvazioni in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla disponibilità dell'applicazione Approvazioni in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129795"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="d6c39-103">Disponibilità dell'app Approvazioni in Teams</span><span class="sxs-lookup"><span data-stu-id="d6c39-103">Teams Approvals app availability</span></span>

<span data-ttu-id="d6c39-104">L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6c39-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="d6c39-105">Offre un modo semplice per ottenere controlli, conformità, rendicontazione e flussi di lavoro delle approvazioni strutturate e non strutturate in Teams.</span><span class="sxs-lookup"><span data-stu-id="d6c39-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra l'app approvazioni](media/approvals-selection.png)

<span data-ttu-id="d6c39-107">Gli utenti possono aggiungere l'app Approvazioni e salvarla nella barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="d6c39-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra l'app approvazioni con l'opzione di aggiunta](media/approvalApp-pin.png)

<span data-ttu-id="d6c39-109">La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione Approvazioni nell'ambiente CDS (Common Data Service) predefinito.</span><span class="sxs-lookup"><span data-stu-id="d6c39-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="d6c39-110">Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito.</span><span class="sxs-lookup"><span data-stu-id="d6c39-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="d6c39-111">Questo articolo descrive i ruoli e i requisiti dell'app Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="d6c39-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c39-112">Questa funzionalità non è ancora stata rilasciata per gli utenti Government Community Cloud (GCC), Government Community Cloud High (GCCH) e DoD (Department of Defense).</span><span class="sxs-lookup"><span data-stu-id="d6c39-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="d6c39-113">Autorizzazioni e licenze richieste</span><span class="sxs-lookup"><span data-stu-id="d6c39-113">Required permissions and licenses</span></span>

<span data-ttu-id="d6c39-114">Per usare l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6c39-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="d6c39-115">Autorizzazioni per la creazione di un database Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="d6c39-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="d6c39-116">Account su [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="d6c39-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="d6c39-117">Ruolo di amministratore nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="d6c39-118">Licenza per [Power Automate](/power-automate/get-started-approvals), Office 365 o Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6c39-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="d6c39-119">Archiviazione su CDS</span><span class="sxs-lookup"><span data-stu-id="d6c39-119">Storage with CDS</span></span>

<span data-ttu-id="d6c39-120">Common Data Model (CDM) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e di analisi in CDS.</span><span class="sxs-lookup"><span data-stu-id="d6c39-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="d6c39-121">È costituito da un set di schemi di dati standardizzati ed estendibili pubblicati da Microsoft e dai propri partner, che consentono la coerenza dei dati e il loro significato nelle applicazioni e nei processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="d6c39-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="d6c39-122">Per altre informazioni, vedere [Common Data Model di Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="d6c39-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="d6c39-123">Altre informazioni sui [flussi di lavoro di Approvazioni](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="d6c39-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="d6c39-124">Autorizzazioni dell'app Approvazioni di Teams</span><span class="sxs-lookup"><span data-stu-id="d6c39-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="d6c39-125">L'app Approvazioni di Teams consente di accedere alle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6c39-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="d6c39-126">Ricevere messaggi e dati forniti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d6c39-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="d6c39-127">Invio di messaggi e notifiche dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d6c39-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="d6c39-128">Render delle app e delle finestre di dialogo personali senza intestazione fornita da Teams.</span><span class="sxs-lookup"><span data-stu-id="d6c39-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="d6c39-129">Accesso alle informazioni del profilo, ad esempio nome, indirizzo di posta elettronica, nome della società e lingua preferita.</span><span class="sxs-lookup"><span data-stu-id="d6c39-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="d6c39-130">Ricevere messaggi e dati forniti dai membri del team nel canale.</span><span class="sxs-lookup"><span data-stu-id="d6c39-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="d6c39-131">Inviare messaggi e notifiche in un canale.</span><span class="sxs-lookup"><span data-stu-id="d6c39-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="d6c39-132">Accedere alle informazioni del team:</span><span class="sxs-lookup"><span data-stu-id="d6c39-132">Access your team's information:</span></span>
  - <span data-ttu-id="d6c39-133">nome del team</span><span class="sxs-lookup"><span data-stu-id="d6c39-133">team name</span></span>
  - <span data-ttu-id="d6c39-134">elenco dei canali</span><span class="sxs-lookup"><span data-stu-id="d6c39-134">channel list</span></span>
  - <span data-ttu-id="d6c39-135">elenco partecipanti (nomi e indirizzi di posta elettronica dei membri del team).</span><span class="sxs-lookup"><span data-stu-id="d6c39-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="d6c39-136">Uso delle informazioni del team per i contatti.</span><span class="sxs-lookup"><span data-stu-id="d6c39-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="d6c39-137">Disabilitare l'app Approvazioni</span><span class="sxs-lookup"><span data-stu-id="d6c39-137">Disable the Approvals app</span></span>

<span data-ttu-id="d6c39-138">L'app Approvazioni è disponibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d6c39-138">The Approvals app is available by default.</span></span> <span data-ttu-id="d6c39-139">È possibile disabilitarla nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="d6c39-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="d6c39-140">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="d6c39-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="d6c39-141">Espandere **App di Teams** e selezionare **Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="d6c39-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="d6c39-142">Cercare l'app Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="d6c39-142">Search for the Approvals app.</span></span>

     ![mostra lo spostamento dell'interfaccia di amministrazione di Teams con le opzioni App di Teams > Gestisci app evidenziate](media/manage-approval-apps.png)

  4. <span data-ttu-id="d6c39-144">Selezionare Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="d6c39-144">Select Approvals.</span></span>

  5. <span data-ttu-id="d6c39-145">Selezionare l'interruttore per disabilitare l'app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-145">Select the toggle to disable the app for your organization.</span></span>

     ![mostra i dettagli dell'app Approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="d6c39-147">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="d6c39-147">Retention policy</span></span>

<span data-ttu-id="d6c39-148">Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito, che al momento non supporta i backup.</span><span class="sxs-lookup"><span data-stu-id="d6c39-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="d6c39-149">Altre informazioni su come eseguire il [Backup e il ripristino di ambienti - Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="d6c39-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="d6c39-150">Controllo</span><span class="sxs-lookup"><span data-stu-id="d6c39-150">Auditing</span></span>

<span data-ttu-id="d6c39-151">L'app Approvazioni registra gli eventi di controllo all'interno del Centro sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6c39-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="d6c39-152">È possibile visualizzare il log di audit.</span><span class="sxs-lookup"><span data-stu-id="d6c39-152">You can view the audit log.</span></span>

1. <span data-ttu-id="d6c39-153">Passare al sito Conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6c39-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="d6c39-154">Selezionare la sezione **Controllo**.</span><span class="sxs-lookup"><span data-stu-id="d6c39-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="d6c39-155">Cercare le attività in **Attività di approvazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="d6c39-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="d6c39-156">È possibile cercare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6c39-156">You can search for the following activities:</span></span>

- <span data-ttu-id="d6c39-157">Creazione di una nuova richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="d6c39-157">Create new approval request</span></span>

- <span data-ttu-id="d6c39-158">Visualizzazione dei dettagli della richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="d6c39-158">View approval request details</span></span>

- <span data-ttu-id="d6c39-159">Richieste di approvazione approvate</span><span class="sxs-lookup"><span data-stu-id="d6c39-159">Approved approval request</span></span>

- <span data-ttu-id="d6c39-160">Richieste di approvazione rifiutate</span><span class="sxs-lookup"><span data-stu-id="d6c39-160">Rejected approval request</span></span>

- <span data-ttu-id="d6c39-161">Richieste di approvazione annullate</span><span class="sxs-lookup"><span data-stu-id="d6c39-161">Canceled approval request</span></span>

- <span data-ttu-id="d6c39-162">Richieste di approvazione condivise</span><span class="sxs-lookup"><span data-stu-id="d6c39-162">Shared approval request</span></span>

- <span data-ttu-id="d6c39-163">File allegato alle richieste di approvazione</span><span class="sxs-lookup"><span data-stu-id="d6c39-163">File attached to approval request</span></span>

- <span data-ttu-id="d6c39-164">Richieste di approvazione riassegnate</span><span class="sxs-lookup"><span data-stu-id="d6c39-164">Reassigned approval request</span></span>

- <span data-ttu-id="d6c39-165">Firma elettronica aggiunta alle richieste di approvazione</span><span class="sxs-lookup"><span data-stu-id="d6c39-165">Added e-signature to approval request</span></span>

- <span data-ttu-id="d6c39-166">Dettagli della richiesta di firma elettronica visualizzati</span><span class="sxs-lookup"><span data-stu-id="d6c39-166">Viewed e-signature request details</span></span>

- <span data-ttu-id="d6c39-167">Richiesta di firma elettronica esaminata</span><span class="sxs-lookup"><span data-stu-id="d6c39-167">Reviewed e-signature request</span></span>

- <span data-ttu-id="d6c39-168">Richiesta di firma elettronica annullata</span><span class="sxs-lookup"><span data-stu-id="d6c39-168">Canceled e-signature request</span></span>

<span data-ttu-id="d6c39-169">Per accedere ad altre approvazioni di controllo all'interno del flusso, abilitare e configurare il controllo nell'ambiente predefinito per le entità di approvazione principali Approvazione, Richiesta di approvazione e Risposta di approvazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-169">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="d6c39-170">Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record di approvazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-170">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="d6c39-171">Per altre informazioni, vedere [Dati di controllo e attività degli utenti per la sicurezza e la conformità - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="d6c39-171">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="d6c39-172">Il controllo può essere personalizzato ulteriormente nel [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="d6c39-172">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="d6c39-173">Per usare i report preconfigurati, accedere al Centro sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6c39-173">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="d6c39-174">Selezionare **Ricerche e indagini**.</span><span class="sxs-lookup"><span data-stu-id="d6c39-174">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="d6c39-175">Cercare nel log di audit e selezionare la scheda **Attività di Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="d6c39-175">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="d6c39-176">Altre informazioni su [Microsoft Dataverse e registrazione delle attività delle app basata su modello - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="d6c39-176">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="d6c39-177">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6c39-177">Security</span></span>

<span data-ttu-id="d6c39-178">Tramite l'app Approvazioni di Teams, gli utenti hanno accesso alla creazione di nuove approvazioni e alla visualizzazione di quelle inviate e ricevute.</span><span class="sxs-lookup"><span data-stu-id="d6c39-178">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="d6c39-179">Gli utenti non possono accedere alle approvazioni create da altri utenti a meno che non abbiano risposto o visualizzato la richiesta.</span><span class="sxs-lookup"><span data-stu-id="d6c39-179">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="d6c39-180">L'utente riceve il ruolo di visualizzatore della richiesta se fa parte della chat o del canale in cui è stata creata l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-180">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="d6c39-181">Non è possibile intervenire sulla richiesta se al momento della creazione dell'approvazione non è stato assegnato il ruolo specifico.</span><span class="sxs-lookup"><span data-stu-id="d6c39-181">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="d6c39-182">Integrazione delle firme elettroniche per le approvazioni</span><span class="sxs-lookup"><span data-stu-id="d6c39-182">Approvals e-signature integration</span></span>

<span data-ttu-id="d6c39-183">Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nell'ambiente cloud del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="d6c39-183">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="d6c39-184">Per altre informazioni sull'archiviazione relativa al contratto di firma elettronica, vedere la documentazione di archiviazione del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="d6c39-184">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="d6c39-185">Per usare la caratteristica di firma elettronica dell'app Approvazioni, sono necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6c39-185">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="d6c39-186">Licenza per lo specifico provider di firme elettroniche che si sceglie di usare.</span><span class="sxs-lookup"><span data-stu-id="d6c39-186">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="d6c39-187">Per ottenere una licenza per l'organizzazione, è necessario accedere al sito del provider.</span><span class="sxs-lookup"><span data-stu-id="d6c39-187">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="d6c39-188">Per la funzionalità di firma elettronica Approvazioni, i partner delle firme di terze parti verranno visualizzati nell'app Teams approvazioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d6c39-188">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="d6c39-189">È possibile disabilitare specifici provider di firme elettroniche accedendo alle impostazioni dell'app nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-189">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="d6c39-190">Nell'Teams di amministrazione, in **Gestisci app,** selezionare l'app Approvazioni e scegliere **Impostazioni**. </span><span class="sxs-lookup"><span data-stu-id="d6c39-190">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="d6c39-191">Per impostazione predefinita, ogni provider di firme elettroniche ha un interruttore accanto alla posizione attiva (a destra).</span><span class="sxs-lookup"><span data-stu-id="d6c39-191">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="d6c39-192">Scorrere l'interruttore verso sinistra per disabilitare uno specifico provider di firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="d6c39-192">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="d6c39-193">Se un Teams disabilita un provider, gli utenti finali non potranno vedere il provider durante la creazione di un'approvazione.</span><span class="sxs-lookup"><span data-stu-id="d6c39-193">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="d6c39-194">Gli utenti finali non saranno inoltre in grado di visualizzare le richieste di firma elettronica effettuate con il provider.</span><span class="sxs-lookup"><span data-stu-id="d6c39-194">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="d6c39-195">Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nel cloud del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="d6c39-195">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="d6c39-196">Sarà quindi necessario accedere al sito del provider per esportare i dati relativi alle firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="d6c39-196">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="d6c39-197">Fare riferimento alla documentazione del provider relativa all'esportazione e alla conservazione di questi contratti.</span><span class="sxs-lookup"><span data-stu-id="d6c39-197">Refer to the provider's documentation about export and retention of these agreements.</span></span>
