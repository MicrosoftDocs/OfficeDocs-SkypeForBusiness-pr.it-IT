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
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212169"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="0dd54-103">Disponibilità dell'app Approvazioni in Teams</span><span class="sxs-lookup"><span data-stu-id="0dd54-103">Teams Approvals app availability</span></span>

<span data-ttu-id="0dd54-104">L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0dd54-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="0dd54-105">Offre un modo semplice per ottenere controlli, conformità, rendicontazione e flussi di lavoro delle approvazioni strutturate e non strutturate in Teams.</span><span class="sxs-lookup"><span data-stu-id="0dd54-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra l'app approvazioni](media/approvals-selection.png)

<span data-ttu-id="0dd54-107">Gli utenti possono aggiungere l'app Approvazioni e salvarla nella barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="0dd54-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra l'app approvazioni con l'opzione di aggiunta](media/approvalApp-pin.png)

<span data-ttu-id="0dd54-109">La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione Approvazioni nell'ambiente CDS (Common Data Service) predefinito.</span><span class="sxs-lookup"><span data-stu-id="0dd54-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="0dd54-110">Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito.</span><span class="sxs-lookup"><span data-stu-id="0dd54-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="0dd54-111">Questo articolo descrive i ruoli e i requisiti dell'app Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="0dd54-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="0dd54-112">Questa funzionalità non è ancora stata rilasciata per gli utenti Government Community Cloud (GCC), Government Community Cloud High (GCCH) e DoD (Department of Defense).</span><span class="sxs-lookup"><span data-stu-id="0dd54-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="0dd54-113">Autorizzazioni e licenze richieste</span><span class="sxs-lookup"><span data-stu-id="0dd54-113">Required permissions and licenses</span></span>

<span data-ttu-id="0dd54-114">Per usare l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dd54-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="0dd54-115">Autorizzazioni per la creazione di un database Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="0dd54-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="0dd54-116">Account su [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="0dd54-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="0dd54-117">Ruolo di amministratore nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="0dd54-118">Licenza per [Power Automate](/power-automate/get-started-approvals), Office 365 o Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0dd54-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="0dd54-119">La licenza per Microsoft Forms è necessaria per consentire agli utenti di configurare nuovi modelli di approvazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="0dd54-120">Archiviazione su CDS</span><span class="sxs-lookup"><span data-stu-id="0dd54-120">Storage with CDS</span></span>

<span data-ttu-id="0dd54-121">Common Data Model (CDM) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e di analisi in CDS.</span><span class="sxs-lookup"><span data-stu-id="0dd54-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="0dd54-122">È costituito da un set di schemi di dati standardizzati ed estendibili pubblicati da Microsoft e dai propri partner, che consentono la coerenza dei dati e il loro significato nelle applicazioni e nei processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="0dd54-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="0dd54-123">Per altre informazioni, vedere [Common Data Model di Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="0dd54-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="0dd54-124">Altre informazioni sui [flussi di lavoro di Approvazioni](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="0dd54-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="0dd54-125">Le approvazioni create da un modello archiviano comunque i dati in CDS, ad esempio il titolo, i dettagli, l'ID del modello e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0dd54-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="0dd54-126">Le risposte inviate nella richiesta di approvazione vengono archiviate in Moduli.</span><span class="sxs-lookup"><span data-stu-id="0dd54-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="0dd54-127">Altre informazioni  [sull'archiviazione dei dati per Microsoft Forms.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)</span><span class="sxs-lookup"><span data-stu-id="0dd54-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="0dd54-128">Se si elimina il modello di modulo nel sito Di Microsoft Forms, il modello Di approvazione verrà eliminato e gli utenti non potranno avviare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="0dd54-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="0dd54-129">Gli utenti riceveranno un messaggio di errore "Tabella CDBNonFound" quando si prova ad aprire un modello approvazione eliminato in Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="0dd54-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="0dd54-130">I modelli di approvazione sono archiviati in Substrate Data Archiviazione (SDS), una piattaforma di archiviazione conforme usata internamente solo all'interno di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0dd54-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="0dd54-131">I modelli con ambito di organizzazione sono archiviati nella "partizione tenant" di SDS e i modelli con ambito team sono archiviati in "partizioni di gruppo" di SDS.</span><span class="sxs-lookup"><span data-stu-id="0dd54-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="0dd54-132">Questo significa che i modelli con ambito di organizzazione condividono la stessa durata del tenant e i modelli con ambito di team condividono la stessa durata del team.</span><span class="sxs-lookup"><span data-stu-id="0dd54-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="0dd54-133">Pertanto, l'eliminazione definitiva del team elimina i modelli correlati.</span><span class="sxs-lookup"><span data-stu-id="0dd54-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="0dd54-134">Autorizzazioni dell'app Approvazioni di Teams</span><span class="sxs-lookup"><span data-stu-id="0dd54-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="0dd54-135">L'app Approvazioni di Teams consente di accedere alle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dd54-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="0dd54-136">Ricevere messaggi e dati forniti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0dd54-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="0dd54-137">Invio di messaggi e notifiche dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0dd54-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="0dd54-138">Render delle app e delle finestre di dialogo personali senza intestazione fornita da Teams.</span><span class="sxs-lookup"><span data-stu-id="0dd54-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="0dd54-139">Accesso alle informazioni del profilo, ad esempio nome, indirizzo di posta elettronica, nome della società e lingua preferita.</span><span class="sxs-lookup"><span data-stu-id="0dd54-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="0dd54-140">Ricevere messaggi e dati forniti dai membri del team nel canale.</span><span class="sxs-lookup"><span data-stu-id="0dd54-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="0dd54-141">Inviare messaggi e notifiche in un canale.</span><span class="sxs-lookup"><span data-stu-id="0dd54-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="0dd54-142">Accedere alle informazioni del team:</span><span class="sxs-lookup"><span data-stu-id="0dd54-142">Access your team's information:</span></span>
  - <span data-ttu-id="0dd54-143">nome del team</span><span class="sxs-lookup"><span data-stu-id="0dd54-143">team name</span></span>
  - <span data-ttu-id="0dd54-144">elenco dei canali</span><span class="sxs-lookup"><span data-stu-id="0dd54-144">channel list</span></span>
  - <span data-ttu-id="0dd54-145">elenco partecipanti (nomi e indirizzi di posta elettronica dei membri del team).</span><span class="sxs-lookup"><span data-stu-id="0dd54-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="0dd54-146">Uso delle informazioni del team per i contatti.</span><span class="sxs-lookup"><span data-stu-id="0dd54-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="0dd54-147">Autorizzazioni per i modelli di approvazione</span><span class="sxs-lookup"><span data-stu-id="0dd54-147">Approval Template Permissions</span></span>

- <span data-ttu-id="0dd54-148">Tutti i proprietari del team possono creare un modello di approvazione per i team di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="0dd54-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="0dd54-149">Quando un amministratore crea un modello per l'intera organizzazione per la prima volta, crea automaticamente un nuovo team di Teams per tutti gli amministratori del tenant, inclusi gli amministratori dei servizi globali e del team.</span><span class="sxs-lookup"><span data-stu-id="0dd54-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="0dd54-150">Questi amministratori verranno aggiunti come proprietari del team, in modo che possano gestire insieme i modelli dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="0dd54-151">Gli amministratori che non hanno più accesso all'organizzazione dopo la creazione del team devono essere aggiunti manualmente come proprietari del team in modo che abbia le stesse autorizzazioni per gestire i modelli a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="0dd54-152">Se un amministratore elimina il team, è necessario un mese per ripristinarlo all'interno del portale Azure Active Directory (AAD) per ripristinare tutti i dati correlati.</span><span class="sxs-lookup"><span data-stu-id="0dd54-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="0dd54-153">Dopo un mese o se l'amministratore elimina il team nel Cestino, si perderanno tutti i dati correlati.</span><span class="sxs-lookup"><span data-stu-id="0dd54-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="0dd54-154">Disabilitare l'app Approvazioni</span><span class="sxs-lookup"><span data-stu-id="0dd54-154">Disable the Approvals app</span></span>

<span data-ttu-id="0dd54-155">L'app Approvazioni è disponibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0dd54-155">The Approvals app is available by default.</span></span> <span data-ttu-id="0dd54-156">È possibile disabilitarla nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="0dd54-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="0dd54-157">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="0dd54-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="0dd54-158">Espandere **App di Teams** e selezionare **Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="0dd54-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="0dd54-159">Cercare l'app Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="0dd54-159">Search for the Approvals app.</span></span>

     ![mostra lo spostamento dell'interfaccia di amministrazione di Teams con le opzioni App di Teams > Gestisci app evidenziate](media/manage-approval-apps.png)

  4. <span data-ttu-id="0dd54-161">Selezionare Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="0dd54-161">Select Approvals.</span></span>

  5. <span data-ttu-id="0dd54-162">Selezionare l'interruttore per disabilitare l'app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-162">Select the toggle to disable the app for your organization.</span></span>

     ![mostra i dettagli dell'app Approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="0dd54-164">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="0dd54-164">Retention policy</span></span>

<span data-ttu-id="0dd54-165">Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito, che al momento non supporta i backup.</span><span class="sxs-lookup"><span data-stu-id="0dd54-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="0dd54-166">Altre informazioni su come eseguire il [Backup e il ripristino di ambienti - Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="0dd54-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="0dd54-167">I dati archiviati in Forms non verranno eliminati finché i proprietari del team non lo puliranno dalla **scheda** Moduli eliminati nell'app Web Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="0dd54-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="0dd54-168">Limitazioni dei dati</span><span class="sxs-lookup"><span data-stu-id="0dd54-168">Data limitations</span></span>

<span data-ttu-id="0dd54-169">Ogni team può contenere al massimo 400 modelli di approvazione e ogni modello può raccogliere un massimo di 50.000 richieste in base alla funzionalità corrente in Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="0dd54-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="0dd54-170">Controllo</span><span class="sxs-lookup"><span data-stu-id="0dd54-170">Auditing</span></span>

<span data-ttu-id="0dd54-171">L'app Approvazioni registra gli eventi di controllo all'interno del Centro sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dd54-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="0dd54-172">È possibile visualizzare il log di audit.</span><span class="sxs-lookup"><span data-stu-id="0dd54-172">You can view the audit log.</span></span>

1. <span data-ttu-id="0dd54-173">Passare al sito Conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dd54-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="0dd54-174">Selezionare la sezione **Controllo**.</span><span class="sxs-lookup"><span data-stu-id="0dd54-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="0dd54-175">Cercare le attività in **Attività di approvazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="0dd54-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="0dd54-176">È possibile cercare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dd54-176">You can search for the following activities:</span></span>

- <span data-ttu-id="0dd54-177">Creazione di una nuova richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="0dd54-177">Create new approval request</span></span>

- <span data-ttu-id="0dd54-178">Visualizzazione dei dettagli della richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="0dd54-178">View approval request details</span></span>

- <span data-ttu-id="0dd54-179">Richieste di approvazione approvate</span><span class="sxs-lookup"><span data-stu-id="0dd54-179">Approved approval request</span></span>

- <span data-ttu-id="0dd54-180">Richieste di approvazione rifiutate</span><span class="sxs-lookup"><span data-stu-id="0dd54-180">Rejected approval request</span></span>

- <span data-ttu-id="0dd54-181">Richieste di approvazione annullate</span><span class="sxs-lookup"><span data-stu-id="0dd54-181">Canceled approval request</span></span>

- <span data-ttu-id="0dd54-182">Richieste di approvazione condivise</span><span class="sxs-lookup"><span data-stu-id="0dd54-182">Shared approval request</span></span>

- <span data-ttu-id="0dd54-183">File allegato alle richieste di approvazione</span><span class="sxs-lookup"><span data-stu-id="0dd54-183">File attached to approval request</span></span>

- <span data-ttu-id="0dd54-184">Richieste di approvazione riassegnate</span><span class="sxs-lookup"><span data-stu-id="0dd54-184">Reassigned approval request</span></span>

- <span data-ttu-id="0dd54-185">Firma elettronica aggiunta alle richieste di approvazione</span><span class="sxs-lookup"><span data-stu-id="0dd54-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="0dd54-186">Dettagli della richiesta di firma elettronica visualizzati</span><span class="sxs-lookup"><span data-stu-id="0dd54-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="0dd54-187">Richiesta di firma elettronica esaminata</span><span class="sxs-lookup"><span data-stu-id="0dd54-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="0dd54-188">Richiesta di firma elettronica annullata</span><span class="sxs-lookup"><span data-stu-id="0dd54-188">Canceled e-signature request</span></span>

- <span data-ttu-id="0dd54-189">Creare un nuovo modello</span><span class="sxs-lookup"><span data-stu-id="0dd54-189">Create a new template</span></span>

- <span data-ttu-id="0dd54-190">Modificare un modello esistente</span><span class="sxs-lookup"><span data-stu-id="0dd54-190">Edit an existing template</span></span>

- <span data-ttu-id="0dd54-191">Abilitare/disabilitare un modello</span><span class="sxs-lookup"><span data-stu-id="0dd54-191">Enable/disable a template</span></span>

- <span data-ttu-id="0dd54-192">Modello visualizzato</span><span class="sxs-lookup"><span data-stu-id="0dd54-192">Viewed template</span></span>

<span data-ttu-id="0dd54-193">Per accedere ad altre approvazioni di controllo all'interno del flusso, abilitare e configurare il controllo nell'ambiente predefinito per le entità di approvazione principali Approvazione, Richiesta di approvazione e Risposta di approvazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="0dd54-194">Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record di approvazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="0dd54-195">Per altre informazioni, vedere [Dati di controllo e attività degli utenti per la sicurezza e la conformità - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="0dd54-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="0dd54-196">Il controllo può essere personalizzato ulteriormente nel [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="0dd54-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="0dd54-197">Per usare i report preconfigurati, accedere al Centro sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dd54-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="0dd54-198">Selezionare **Ricerche e indagini**.</span><span class="sxs-lookup"><span data-stu-id="0dd54-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="0dd54-199">Cercare nel log di audit e selezionare la scheda **Attività di Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="0dd54-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="0dd54-200">Altre informazioni su [Microsoft Dataverse e registrazione delle attività delle app basata su modello - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="0dd54-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="0dd54-201">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0dd54-201">Security</span></span>

<span data-ttu-id="0dd54-202">Tramite l'app Approvazioni di Teams, gli utenti hanno accesso alla creazione di nuove approvazioni e alla visualizzazione di quelle inviate e ricevute.</span><span class="sxs-lookup"><span data-stu-id="0dd54-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="0dd54-203">Gli utenti non possono accedere alle approvazioni create da altri utenti a meno che non abbiano risposto o visualizzato la richiesta.</span><span class="sxs-lookup"><span data-stu-id="0dd54-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="0dd54-204">L'utente riceve il ruolo di visualizzatore della richiesta se fa parte della chat o del canale in cui è stata creata l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="0dd54-205">Non è possibile intervenire sulla richiesta se al momento della creazione dell'approvazione non è stato assegnato il ruolo specifico.</span><span class="sxs-lookup"><span data-stu-id="0dd54-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="0dd54-206">Integrazione delle firme elettroniche per le approvazioni</span><span class="sxs-lookup"><span data-stu-id="0dd54-206">Approvals e-signature integration</span></span>

<span data-ttu-id="0dd54-207">Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nell'ambiente cloud del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="0dd54-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="0dd54-208">Per altre informazioni sull'archiviazione relativa al contratto di firma elettronica, vedere la documentazione di archiviazione del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="0dd54-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="0dd54-209">Per usare la caratteristica di firma elettronica dell'app Approvazioni, sono necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dd54-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="0dd54-210">Licenza per lo specifico provider di firme elettroniche che si sceglie di usare.</span><span class="sxs-lookup"><span data-stu-id="0dd54-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="0dd54-211">Per ottenere una licenza per l'organizzazione, è necessario accedere al sito del provider.</span><span class="sxs-lookup"><span data-stu-id="0dd54-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="0dd54-212">Per la funzionalità di firma elettronica Approvazioni, i partner delle firme di terze parti verranno visualizzati nell'app Teams approvazioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0dd54-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="0dd54-213">È possibile disabilitare specifici provider di firme elettroniche accedendo alle impostazioni dell'app nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="0dd54-214">Nell'Teams di amministrazione, in **Gestisci app,** selezionare l'app Approvazioni e scegliere **Impostazioni**. </span><span class="sxs-lookup"><span data-stu-id="0dd54-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="0dd54-215">Per impostazione predefinita, ogni provider di firme elettroniche ha un interruttore accanto alla posizione attiva (a destra).</span><span class="sxs-lookup"><span data-stu-id="0dd54-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="0dd54-216">Scorrere l'interruttore verso sinistra per disabilitare uno specifico provider di firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="0dd54-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="0dd54-217">Se un Teams disabilita un provider, gli utenti finali non potranno vedere il provider durante la creazione di un'approvazione.</span><span class="sxs-lookup"><span data-stu-id="0dd54-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="0dd54-218">Gli utenti finali non saranno inoltre in grado di visualizzare le richieste di firma elettronica effettuate con il provider.</span><span class="sxs-lookup"><span data-stu-id="0dd54-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="0dd54-219">Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nel cloud del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="0dd54-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="0dd54-220">Sarà quindi necessario accedere al sito del provider per esportare i dati relativi alle firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="0dd54-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="0dd54-221">Fare riferimento alla documentazione del provider relativa all'esportazione e alla conservazione di questi contratti.</span><span class="sxs-lookup"><span data-stu-id="0dd54-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
