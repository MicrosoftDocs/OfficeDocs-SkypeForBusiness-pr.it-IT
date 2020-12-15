---
title: Approvazioni disponibilità delle applicazioni in teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla disponibilità di applicazioni approvate in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675194"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="078df-103">Disponibilità delle app di approvazioni Teams</span><span class="sxs-lookup"><span data-stu-id="078df-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="078df-104">L'app approvazioni è disponibile come app personale per tutti gli utenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="078df-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="078df-105">L'app approvazioni offre un modo semplice per offrire controllo, conformità, responsabilità e flussi di lavoro sia alle approvazioni strutturate che destrutturate in teams.</span><span class="sxs-lookup"><span data-stu-id="078df-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![Mostra l'app approvazioni](media/approvals-selection.png)

<span data-ttu-id="078df-107">Gli utenti possono aggiungere l'app approvations per salvarla nella barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="078df-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![Mostra l'app approvazioni con l'opzione pin](media/approvalApp-pin.png)

<span data-ttu-id="078df-109">La prima approvazione creata dall'app approvazioni attiverà il provisioning della soluzione di approvazione nell'ambiente CDS (Common Data Service) predefinito.</span><span class="sxs-lookup"><span data-stu-id="078df-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="078df-110">Le approvazioni create dall'app approvazioni verranno archiviate nell'ambiente CDS predefinito.</span><span class="sxs-lookup"><span data-stu-id="078df-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="078df-111">In questo articolo vengono illustrati i ruoli e i requisiti dell'app approvazione.</span><span class="sxs-lookup"><span data-stu-id="078df-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="078df-112">Autorizzazioni e licenze necessarie</span><span class="sxs-lookup"><span data-stu-id="078df-112">Required permissions and licenses</span></span>

<span data-ttu-id="078df-113">Per usare l'app approvazioni, è necessario disporre delle autorizzazioni per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="078df-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="078df-114">Autorizzazioni per creare un database di Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="078df-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="078df-115">Un account in [Flow.Microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="078df-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="078df-116">Ruolo di amministratore nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="078df-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="078df-117">Licenza per un [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), un Office 365 o una dinamica 365.</span><span class="sxs-lookup"><span data-stu-id="078df-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="078df-118">Archiviazione con CD</span><span class="sxs-lookup"><span data-stu-id="078df-118">Storage with CDS</span></span>

<span data-ttu-id="078df-119">Common Data Model (CDM) è il linguaggio di dati condiviso usato dalle applicazioni aziendali e analitiche nei CD.</span><span class="sxs-lookup"><span data-stu-id="078df-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="078df-120">È costituito da un set di uno schema di dati estensibile standardizzato pubblicato da Microsoft e dai nostri partner che consente la coerenza dei dati e il relativo significato tra le applicazioni e i processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="078df-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="078df-121">Leggi altre informazioni sul [modello di dati comune di Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="078df-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="078df-122">Leggi altre informazioni sul [flusso di lavoro approvazione](https://docs.microsoft.com/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="078df-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="078df-123">Autorizzazioni per le app teams approvations</span><span class="sxs-lookup"><span data-stu-id="078df-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="078df-124">L'app Team approvations consente di accedere alle caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="078df-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="078df-125">Ricevere i messaggi e i dati forniti.</span><span class="sxs-lookup"><span data-stu-id="078df-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="078df-126">Inviare messaggi e notifiche.</span><span class="sxs-lookup"><span data-stu-id="078df-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="078df-127">Renderizzare le app personali e le finestre di dialogo senza un'intestazione fornita da teams.</span><span class="sxs-lookup"><span data-stu-id="078df-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="078df-128">Accedere alle informazioni del profilo, ad esempio il nome, l'indirizzo di posta elettronica, il nome della società e la lingua preferita.</span><span class="sxs-lookup"><span data-stu-id="078df-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="078df-129">Ricevere i messaggi e i dati forniti dai membri del team in un canale.</span><span class="sxs-lookup"><span data-stu-id="078df-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="078df-130">Inviare messaggi e notifiche in un canale.</span><span class="sxs-lookup"><span data-stu-id="078df-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="078df-131">Accedere alle informazioni del team:</span><span class="sxs-lookup"><span data-stu-id="078df-131">Access your team's information:</span></span>
  - <span data-ttu-id="078df-132">nome del team</span><span class="sxs-lookup"><span data-stu-id="078df-132">team name</span></span>
  - <span data-ttu-id="078df-133">elenco canali</span><span class="sxs-lookup"><span data-stu-id="078df-133">channel list</span></span>
  - <span data-ttu-id="078df-134">Roster (nomi e indirizzi di posta elettronica del membro del team).</span><span class="sxs-lookup"><span data-stu-id="078df-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="078df-135">Usare le informazioni del team per contattarle.</span><span class="sxs-lookup"><span data-stu-id="078df-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="078df-136">Disabilitare l'app approvazioni</span><span class="sxs-lookup"><span data-stu-id="078df-136">Disable the Approvals app</span></span>

<span data-ttu-id="078df-137">L'app approvazioni è disponibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="078df-137">The Approvals app is available by default.</span></span> <span data-ttu-id="078df-138">Puoi disabilitare l'app nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="078df-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="078df-139">Accedere all'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="078df-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="078df-140">Espandi le **app teams** e seleziona **Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="078df-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="078df-141">Cercare l'app approvazioni.</span><span class="sxs-lookup"><span data-stu-id="078df-141">Search for the Approvals app.</span></span>

![Mostra lo spostamento dell'interfaccia di amministrazione con le app teams > gestire le app evidenziate](media/manage-approval-apps.png)

  4. <span data-ttu-id="078df-143">Selezionare approvazioni.</span><span class="sxs-lookup"><span data-stu-id="078df-143">Select Approvals.</span></span>

  5. <span data-ttu-id="078df-144">Selezionare l'attiva/disattiva per disabilitare l'app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="078df-144">Select the toggle to disable the app for your organization.</span></span>

![Mostra i dettagli per l'app approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="078df-146">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="078df-146">Retention policy</span></span>

<span data-ttu-id="078df-147">Le approvazioni create dall'app approvazioni sono archiviate nell'ambiente CDS predefinito, che in questo momento non supporta i backup.</span><span class="sxs-lookup"><span data-stu-id="078df-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="078df-148">Leggi altre informazioni su come [eseguire il backup e il ripristino di ambienti-Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="078df-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="078df-149">Controllo</span><span class="sxs-lookup"><span data-stu-id="078df-149">Auditing</span></span>

<span data-ttu-id="078df-150">L'app approvations registra gli eventi di controllo nel centro sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="078df-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="078df-151">È possibile visualizzare il log di controllo.</span><span class="sxs-lookup"><span data-stu-id="078df-151">You can view the audit log.</span></span>

1. <span data-ttu-id="078df-152">Accedere al sito di conformità di M365.</span><span class="sxs-lookup"><span data-stu-id="078df-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="078df-153">Selezionare la sezione **controllo** .</span><span class="sxs-lookup"><span data-stu-id="078df-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="078df-154">Cercare attività in **attività di approvazione di Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="078df-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="078df-155">È possibile cercare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="078df-155">You can search for the following activities:</span></span>

- <span data-ttu-id="078df-156">Creare una nuova richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="078df-156">Create new approval request</span></span>

- <span data-ttu-id="078df-157">Visualizzare i dettagli delle richieste di approvazione</span><span class="sxs-lookup"><span data-stu-id="078df-157">View approval request details</span></span>

- <span data-ttu-id="078df-158">Richiesta di approvazione approvata</span><span class="sxs-lookup"><span data-stu-id="078df-158">Approved approval request</span></span>

- <span data-ttu-id="078df-159">Richiesta di approvazione rifiutata</span><span class="sxs-lookup"><span data-stu-id="078df-159">Rejected approval request</span></span>

- <span data-ttu-id="078df-160">Richiesta di approvazione annullata</span><span class="sxs-lookup"><span data-stu-id="078df-160">Canceled approval request</span></span>

- <span data-ttu-id="078df-161">Richiesta di approvazione condivisa</span><span class="sxs-lookup"><span data-stu-id="078df-161">Shared approval request</span></span>

- <span data-ttu-id="078df-162">File allegato alla richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="078df-162">File attached to approval request</span></span>

- <span data-ttu-id="078df-163">Richiesta di approvazione riassegnata</span><span class="sxs-lookup"><span data-stu-id="078df-163">Reassigned approval request</span></span>

- <span data-ttu-id="078df-164">Aggiunta della firma elettronica alla richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="078df-164">Added e-signature to approval request</span></span>

<span data-ttu-id="078df-165">Per accedere ad altre approvazioni di controllo in flusso, abilitare e configurare il controllo nell'ambiente predefinito per l'approvazione delle entità primarie, la richiesta di approvazione e la risposta all'approvazione.</span><span class="sxs-lookup"><span data-stu-id="078df-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="078df-166">Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record di approvazione.</span><span class="sxs-lookup"><span data-stu-id="078df-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="078df-167">Leggi altre informazioni sui [dati di controllo e sulle attività degli utenti per la sicurezza e la conformità-Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="078df-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="078df-168">Il controllo può essere ulteriormente personalizzato nel [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="078df-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="078df-169">Per usare i report preconfigurati, accedere a Office 365 sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="078df-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="078df-170">Selezionare **cerca & investigazione**.</span><span class="sxs-lookup"><span data-stu-id="078df-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="078df-171">Eseguire una ricerca nel log di controllo e selezionare la scheda **attività dinamiche 365** .</span><span class="sxs-lookup"><span data-stu-id="078df-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="078df-172">Leggi altre informazioni su [Microsoft dataverse e la registrazione delle attività delle app basate su modelli-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="078df-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="078df-173">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="078df-173">Security</span></span>

<span data-ttu-id="078df-174">Dall'app approvazione teams, gli utenti hanno accesso per creare nuove approvazioni e visualizzare le approvazioni che hanno inviato e ricevuto.</span><span class="sxs-lookup"><span data-stu-id="078df-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="078df-175">Gli utenti non avranno accesso alle approvazioni create da altri, a meno che non siano un risponditore o un visualizzatore della richiesta.</span><span class="sxs-lookup"><span data-stu-id="078df-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="078df-176">A un utente verrà assegnato un ruolo di Visualizzatore di una richiesta se fa parte della chat o del canale in cui è stato creato l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="078df-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="078df-177">Non avranno la possibilità di intervenire sulla richiesta se non hanno dato questo ruolo al momento della creazione dell'approvazione.</span><span class="sxs-lookup"><span data-stu-id="078df-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
