---
title: Disponibilità delle applicazioni di approvazione in Teams
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
description: Informazioni sulla disponibilità delle applicazioni Approvazione in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909520"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="4f9cc-103">Disponibilità dell'app Approvazione Teams</span><span class="sxs-lookup"><span data-stu-id="4f9cc-103">Teams Approvals app availability</span></span>

<span data-ttu-id="4f9cc-104">L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="4f9cc-105">L'app Approvazioni offre un modo semplice per portare il controllo, la conformità, la responsabilità e i flussi di lavoro nelle approvazioni strutturate e non strutturate in Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra l'app Approvazioni](media/approvals-selection.png)

<span data-ttu-id="4f9cc-107">Gli utenti possono aggiungere l'app Approvazioni per salvarla sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra l'app Approvazioni con l'opzione Aggiungi](media/approvalApp-pin.png)

<span data-ttu-id="4f9cc-109">La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione di approvazione nell'ambiente CDS (Common Data Service) predefinito.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="4f9cc-110">Le approvazioni create dall'app Approvazioni verranno archiviate nell'ambiente CDS predefinito.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="4f9cc-111">Questo articolo descrive i requisiti e i ruoli dell'app Approvazione.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="4f9cc-112">Autorizzazioni e licenze necessarie</span><span class="sxs-lookup"><span data-stu-id="4f9cc-112">Required permissions and licenses</span></span>

<span data-ttu-id="4f9cc-113">Per usare l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f9cc-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="4f9cc-114">Autorizzazioni per la creazione di un database CDS Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="4f9cc-115">Un account [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="4f9cc-116">Ruolo di amministratore nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="4f9cc-117">Licenza per [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 o Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="4f9cc-118">Archiviazione con CDS</span><span class="sxs-lookup"><span data-stu-id="4f9cc-118">Storage with CDS</span></span>

<span data-ttu-id="4f9cc-119">Il modello CDM (Common Data Model) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e analitiche in CDS.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="4f9cc-120">È costituito da un set di schemi di dati estendibili standardizzati pubblicati da Microsoft e dai nostri partner che consentono la coerenza dei dati e il relativo significato in applicazioni e processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="4f9cc-121">Altre informazioni sul [modello di dati comuni della piattaforma Microsoft Power.](https://docs.microsoft.com/power-automate/get-started-approvals)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="4f9cc-122">Altre informazioni sul flusso [di lavoro Approvazione.](https://docs.microsoft.com/power-automate/modern-approvals)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="4f9cc-123">Autorizzazioni dell'app Approvals Teams</span><span class="sxs-lookup"><span data-stu-id="4f9cc-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="4f9cc-124">L'app Approvals Teams consente di accedere alle caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f9cc-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="4f9cc-125">Ricevere messaggi e dati forniti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="4f9cc-126">Inviarti messaggi e notifiche.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="4f9cc-127">Visualizzare le app e le finestre di dialogo personali senza un'intestazione fornita da Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="4f9cc-128">Accedere alle informazioni del profilo, ad esempio il nome, l'indirizzo di posta elettronica, il nome della società e la lingua preferita.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="4f9cc-129">Ricevere messaggi e dati forniti dai membri del team in un canale.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="4f9cc-130">Inviare messaggi e notifiche in un canale.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="4f9cc-131">Accedere alle informazioni del team:</span><span class="sxs-lookup"><span data-stu-id="4f9cc-131">Access your team's information:</span></span>
  - <span data-ttu-id="4f9cc-132">nome del team</span><span class="sxs-lookup"><span data-stu-id="4f9cc-132">team name</span></span>
  - <span data-ttu-id="4f9cc-133">elenco canali</span><span class="sxs-lookup"><span data-stu-id="4f9cc-133">channel list</span></span>
  - <span data-ttu-id="4f9cc-134">(i nomi e gli indirizzi di posta elettronica dei membri del team).</span><span class="sxs-lookup"><span data-stu-id="4f9cc-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="4f9cc-135">Usare le informazioni del team per contattarlo.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="4f9cc-136">Disabilitare l'app Approvazioni</span><span class="sxs-lookup"><span data-stu-id="4f9cc-136">Disable the Approvals app</span></span>

<span data-ttu-id="4f9cc-137">L'app Approvazioni è disponibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-137">The Approvals app is available by default.</span></span> <span data-ttu-id="4f9cc-138">È possibile disabilitare l'app nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="4f9cc-139">Accedere all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="4f9cc-140">Espandere **le app di Teams** e selezionare Gestisci **app.**</span><span class="sxs-lookup"><span data-stu-id="4f9cc-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="4f9cc-141">Cercare l'app Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-141">Search for the Approvals app.</span></span>

![mostra la struttura di spostamento dell'interfaccia di amministrazione con l'opzione App di Teams > Gestisci app evidenziata](media/manage-approval-apps.png)

  4. <span data-ttu-id="4f9cc-143">Selezionare Approvazioni.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-143">Select Approvals.</span></span>

  5. <span data-ttu-id="4f9cc-144">Seleziona l'interruttore per disabilitare l'app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-144">Select the toggle to disable the app for your organization.</span></span>

![mostra i dettagli per l'app Approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="4f9cc-146">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="4f9cc-146">Retention policy</span></span>

<span data-ttu-id="4f9cc-147">Le approvazioni create dall'app Approvazioni vengono archiviate nell'ambiente CDS predefinito, che al momento non supporta i backup.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="4f9cc-148">Altre informazioni su come eseguire [il backup e il ripristino di ambienti - Power Platform Microsoft \| Docs.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="4f9cc-149">Controllo</span><span class="sxs-lookup"><span data-stu-id="4f9cc-149">Auditing</span></span>

<span data-ttu-id="4f9cc-150">L'app Approvazione registra gli eventi di controllo all'interno del Centro sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="4f9cc-151">È possibile visualizzare il log di controllo.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-151">You can view the audit log.</span></span>

1. <span data-ttu-id="4f9cc-152">Passare al sito conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="4f9cc-153">Selezionare la **sezione** Controllo.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="4f9cc-154">Cercare le attività nelle **attività di approvazione di Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="4f9cc-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="4f9cc-155">È possibile cercare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f9cc-155">You can search for the following activities:</span></span>

- <span data-ttu-id="4f9cc-156">Creare una nuova richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="4f9cc-156">Create new approval request</span></span>

- <span data-ttu-id="4f9cc-157">Visualizzare i dettagli della richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="4f9cc-157">View approval request details</span></span>

- <span data-ttu-id="4f9cc-158">Richiesta di approvazione approvata</span><span class="sxs-lookup"><span data-stu-id="4f9cc-158">Approved approval request</span></span>

- <span data-ttu-id="4f9cc-159">Richiesta di approvazione rifiutata</span><span class="sxs-lookup"><span data-stu-id="4f9cc-159">Rejected approval request</span></span>

- <span data-ttu-id="4f9cc-160">Richiesta di approvazione annullata</span><span class="sxs-lookup"><span data-stu-id="4f9cc-160">Canceled approval request</span></span>

- <span data-ttu-id="4f9cc-161">Richiesta di approvazione condivisa</span><span class="sxs-lookup"><span data-stu-id="4f9cc-161">Shared approval request</span></span>

- <span data-ttu-id="4f9cc-162">File allegato alla richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="4f9cc-162">File attached to approval request</span></span>

- <span data-ttu-id="4f9cc-163">Richiesta di approvazione riassegnata</span><span class="sxs-lookup"><span data-stu-id="4f9cc-163">Reassigned approval request</span></span>

- <span data-ttu-id="4f9cc-164">Aggiunta di una firma elettronica alla richiesta di approvazione</span><span class="sxs-lookup"><span data-stu-id="4f9cc-164">Added e-signature to approval request</span></span>

<span data-ttu-id="4f9cc-165">Per l'accesso ad altre approvazioni di controllo all'interno di Flow, abilitare e configurare il controllo nell'ambiente predefinito per le entità di approvazione principali Approvazione, Richiesta di approvazione e Risposta di approvazione.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="4f9cc-166">Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record Approvazione.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="4f9cc-167">Altre informazioni sui dati di controllo e sulle attività degli utenti per la sicurezza e la [conformità - Documenti Microsoft della piattaforma \| Power.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="4f9cc-168">Il controllo può essere ulteriormente personalizzato nel Centro sicurezza e [conformità di Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="4f9cc-169">Per usare i report preconfigurati, accedere a Sicurezza e conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="4f9cc-170">Selezionare **Ricerche & indagini.**</span><span class="sxs-lookup"><span data-stu-id="4f9cc-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="4f9cc-171">Eseguire ricerche nel log di controllo e selezionare la **scheda Attività di Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="4f9cc-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="4f9cc-172">Altre informazioni sulla registrazione attività delle app basata su modello e [Microsoft Dataverse - Piattaforma Power.](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)</span><span class="sxs-lookup"><span data-stu-id="4f9cc-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="4f9cc-173">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4f9cc-173">Security</span></span>

<span data-ttu-id="4f9cc-174">Dall'app Approvazioni di Teams, gli utenti hanno accesso per creare nuove approvazioni e visualizzare le approvazioni inviate e ricevute.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="4f9cc-175">Gli utenti non hanno accesso alle Approvazioni create da altri, a meno che non siano un risponditore o un visualizzatore della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="4f9cc-176">L'utente avrà il ruolo di visualizzatore di una richiesta se fa parte della chat o del canale in cui è stata creata l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="4f9cc-177">Non sarà possibile intervenire sulla richiesta se al momento della creazione dell'approvazione non è stato assegnato quel ruolo.</span><span class="sxs-lookup"><span data-stu-id="4f9cc-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
