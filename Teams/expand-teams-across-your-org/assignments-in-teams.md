---
title: Assegnazioni per Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Informazioni su come gestire le assegnazioni nell'interfaccia di amministrazione di Microsoft teams per l'istruzione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561052"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="59f90-103">Assegnare attività in Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="59f90-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="59f90-104">Le assegnazioni sono attività o unità di lavoro assegnate a uno studente o a un membro del team in una classe come parte dello studio.</span><span class="sxs-lookup"><span data-stu-id="59f90-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="59f90-105">Puoi creare assegnazioni all'interno della classe teams.</span><span class="sxs-lookup"><span data-stu-id="59f90-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="59f90-106">Leggi [altre informazioni sulle assegnazioni](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="59f90-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="59f90-107">Per informazioni dettagliate sulle assegnazioni di Team su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="59f90-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="59f90-108">Assegnazioni nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59f90-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="59f90-109">Con le impostazioni di amministratore nell'interfaccia di amministrazione di Microsoft teams, è possibile attivare o disattivare le caratteristiche seguenti per essere disponibili per studenti e docenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="59f90-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="59f90-110">Di seguito sono riportate le impostazioni relative alle assegnazioni:</span><span class="sxs-lookup"><span data-stu-id="59f90-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="59f90-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="59f90-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="59f90-112">Digest della posta elettronica Guardian settimanale</span><span class="sxs-lookup"><span data-stu-id="59f90-112">Weekly guardian email digest</span></span>

<span data-ttu-id="59f90-113">I messaggi di posta elettronica conterranno informazioni sulle assegnazioni della settimana precedente e per la settimana successiva e verranno inviate durante il fine settimana.</span><span class="sxs-lookup"><span data-stu-id="59f90-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="59f90-114">Le informazioni sul contenuto della posta elettronica possono essere trovate qui.</span><span class="sxs-lookup"><span data-stu-id="59f90-114">Information about the email content can be found here.</span></span> <span data-ttu-id="59f90-115">I messaggi di posta elettronica devono essere configurati e aggiornati dagli amministratori usando [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span><span class="sxs-lookup"><span data-stu-id="59f90-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="59f90-116">Questa funzionalità popola automaticamente le classi per i team con i roster degli studenti dal SIS (Student Information System) della scuola.</span><span class="sxs-lookup"><span data-stu-id="59f90-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="59f90-117">I passaggi per abilitare questa caratteristica sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="59f90-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="59f90-118">Importare le informazioni di contatto padre tramite la sincronizzazione genitore e tutore in SDS.</span><span class="sxs-lookup"><span data-stu-id="59f90-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="59f90-119">Per istruzioni su come abilitare la sincronizzazione genitore e tutore, vedere [Abilitazione della sincronizzazione genitore e tutore](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="59f90-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="59f90-120">Attivare l'impostazione Guardian nell'interfaccia di amministrazione di Microsoft teams, perché l'impostazione è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="59f90-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="59f90-121">Ciò consentirà agli insegnanti di inviare un digest settimanale.</span><span class="sxs-lookup"><span data-stu-id="59f90-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="59f90-122">Gli insegnanti possono rifiutare l'opt-out del digest deselezionando l'impostazione all'interno del proprio team di classe personale (**Impostazioni assegnazione > messaggi di posta elettronica padre/tutore**).</span><span class="sxs-lookup"><span data-stu-id="59f90-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="59f90-123">Per verificare che i genitori ottengano il messaggio di posta elettronica, i tre elementi seguenti devono essere veri:</span><span class="sxs-lookup"><span data-stu-id="59f90-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="59f90-124">Indirizzo di posta elettronica allegato al profilo studente in SDS e contrassegnati come _padre_ o _tutore_.</span><span class="sxs-lookup"><span data-stu-id="59f90-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="59f90-125">Per informazioni dettagliate, vedere [formato di file di sincronizzazione padre e tutore](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="59f90-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="59f90-126">Gli studenti appartengono ad almeno una classe in cui il messaggio di posta elettronica non viene disabilitato dall'insegnante nelle [impostazioni di assegnazione](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span><span class="sxs-lookup"><span data-stu-id="59f90-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="59f90-127">I messaggi di posta elettronica conterranno informazioni sulle assegnazioni che avevano una data di scadenza nella settimana precedente o nella settimana successiva.</span><span class="sxs-lookup"><span data-stu-id="59f90-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="59f90-128">Questa impostazione è disinserita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="59f90-128">This setting is off by default.</span></span>


<span data-ttu-id="59f90-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="59f90-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="59f90-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="59f90-130">MakeCode</span></span>
<span data-ttu-id="59f90-131">Microsoft MakeCode è una piattaforma di codifica basata su blocchi che consente di portare in vita l'informatica per tutti gli studenti.</span><span class="sxs-lookup"><span data-stu-id="59f90-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="59f90-132">MakeCode è un prodotto Microsoft soggetto alle [condizioni d'uso](https://go.microsoft.com/fwlink/?LinkID=206977) e ai criteri di [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59f90-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="59f90-133">Questa impostazione è disinserita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="59f90-133">This setting is off by default.</span></span> <span data-ttu-id="59f90-134">Per abilitare le assegnazioni di MakeCode in teams, nell'interfaccia di **amministrazione di teams** passare alla sezione **assegnazioni** e attivare l'opzione toggle MakeCode **su** attivato.</span><span class="sxs-lookup"><span data-stu-id="59f90-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="59f90-135">Fare clic su **Salva** e attendere alcune ore per rendere effettive queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="59f90-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="59f90-136">Per altre informazioni sul funzionamento di questa funzionalità, vedere questa [dimostrazione video](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="59f90-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="59f90-137">Leggi [altre informazioni su MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="59f90-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="59f90-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="59f90-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="59f90-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="59f90-139">Turnitin</span></span>

<span data-ttu-id="59f90-140">Turnitin è un servizio di rilevamento del plagio.</span><span class="sxs-lookup"><span data-stu-id="59f90-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="59f90-141">Si tratta di un prodotto o un servizio di terze parti soggetto ai propri termini e alla propria politica sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="59f90-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="59f90-142">L'utente è responsabile dell'uso di prodotti e servizi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="59f90-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="59f90-143">Questa impostazione è disinserita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="59f90-143">This setting is off by default.</span></span>

<span data-ttu-id="59f90-144">Per abilitare correttamente Turnitin per l'organizzazione, è necessario avere già un abbonamento a Turnitin.</span><span class="sxs-lookup"><span data-stu-id="59f90-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="59f90-145">Sarà necessario immettere le informazioni aggiuntive seguenti, che si trovano nella console di amministrazione di Turnitin:</span><span class="sxs-lookup"><span data-stu-id="59f90-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="59f90-146">**TurnitinApiKey**: questo è un GUID di 32-character trovato nella console di amministrazione in Integrations.</span><span class="sxs-lookup"><span data-stu-id="59f90-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="59f90-147">**TurnitinApiUrl**: questo è l'URL HTTPS della console di amministrazione di Turnitin.</span><span class="sxs-lookup"><span data-stu-id="59f90-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="59f90-148">Ecco alcune istruzioni utili per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="59f90-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="59f90-149">**TurnitinApiUrl** è l'indirizzo host della console di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="59f90-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="59f90-150">Esempio `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="59f90-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="59f90-151">La console di amministrazione è la posizione in cui è possibile creare un'integrazione e una chiave API associata all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="59f90-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="59f90-152">Selezionare **integrazioni** dal menu laterale, quindi fare clic su **Aggiungi integrazione** e assegnare un nome all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="59f90-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="59f90-154">Il **TurnitinApiKey** verrà assegnato dopo aver seguito le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="59f90-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="59f90-155">Copiare la chiave API e incollarla nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="59f90-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="59f90-156">Questa è l'unica volta che è possibile visualizzare la chiave.</span><span class="sxs-lookup"><span data-stu-id="59f90-156">This is the only time you can view the key.</span></span>

![Schermata che mostra la copia della chiave API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="59f90-158">Dopo aver fatto clic sul pulsante **Salva** nell'interfaccia di amministrazione per questa impostazione, attendere alcune ore per rendere effettive queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="59f90-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="59f90-159">Pronti per iniziare a usare l'integrazione di Turnitin in teams?</span><span class="sxs-lookup"><span data-stu-id="59f90-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="59f90-160">Iscriversi al [programma Early Access](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span><span class="sxs-lookup"><span data-stu-id="59f90-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
