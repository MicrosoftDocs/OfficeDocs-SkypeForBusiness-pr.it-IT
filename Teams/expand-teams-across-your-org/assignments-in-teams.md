---
title: Assegnazioni per Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616910"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="eb936-103">Assegnare attività in Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="eb936-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="eb936-104">Le funzionalità di assegnazione e classificazione in teams per l'istruzione consentono agli insegnanti di assegnare attività, lavoro o quiz agli studenti.</span><span class="sxs-lookup"><span data-stu-id="eb936-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="eb936-105">Gli insegnanti possono gestire le sequenze temporali delle assegnazioni, le istruzioni, aggiungere risorse per l'attivazione, il grado con le rubriche e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="eb936-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="eb936-106">Possono anche tenere traccia dello stato di avanzamento delle lezioni e dei singoli studenti nella scheda voti.</span><span class="sxs-lookup"><span data-stu-id="eb936-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="eb936-107">Leggi [altre informazioni sulle assegnazioni e i voti in teams per l'istruzione](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="eb936-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="eb936-108">Per informazioni dettagliate sulle assegnazioni di Team su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="eb936-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="eb936-109">Integrazioni delle assegnazioni nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb936-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="eb936-110">Usando le impostazioni di amministratore nell'interfaccia di amministrazione di Microsoft teams, è possibile attivare o disattivare le funzionalità per gli insegnanti all'interno dell'organizzazione e dei loro studenti.</span><span class="sxs-lookup"><span data-stu-id="eb936-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="eb936-111">Di seguito sono riportate le impostazioni relative alle assegnazioni:</span><span class="sxs-lookup"><span data-stu-id="eb936-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="eb936-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="eb936-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="eb936-113">Digest della posta elettronica Guardian settimanale</span><span class="sxs-lookup"><span data-stu-id="eb936-113">Weekly guardian email digest</span></span>


<span data-ttu-id="eb936-114">I messaggi di posta elettronica Guardian vengono inviati ogni fine settimana a genitori o tutori.</span><span class="sxs-lookup"><span data-stu-id="eb936-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="eb936-115">Il messaggio di posta elettronica contiene informazioni sulle assegnazioni della settimana precedente e per la settimana successiva.</span><span class="sxs-lookup"><span data-stu-id="eb936-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="eb936-116">La sincronizzazione genitore e tutore può essere eseguita tramite [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span><span class="sxs-lookup"><span data-stu-id="eb936-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="eb936-117">Importare le informazioni di contatto padre tramite la sincronizzazione genitore e tutore in SDS.</span><span class="sxs-lookup"><span data-stu-id="eb936-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="eb936-118">Per istruzioni su come abilitare la sincronizzazione genitore e tutore, vedere [Abilitazione della sincronizzazione genitore e tutore](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="eb936-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="eb936-119">Attivare l'impostazione Guardian nell'interfaccia di amministrazione di Microsoft teams, perché l'impostazione è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eb936-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="eb936-120">Ciò consentirà agli insegnanti di inviare un digest settimanale.</span><span class="sxs-lookup"><span data-stu-id="eb936-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="eb936-121">Gli insegnanti possono rifiutare l'opt-out del digest deselezionando l'impostazione all'interno del proprio team di classe personale (**Impostazioni assegnazione > messaggi di posta elettronica padre/tutore**).</span><span class="sxs-lookup"><span data-stu-id="eb936-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="eb936-122">Per verificare che i genitori ottengano il messaggio di posta elettronica, i tre elementi seguenti devono essere veri:</span><span class="sxs-lookup"><span data-stu-id="eb936-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="eb936-123">Indirizzo di posta elettronica allegato al profilo studente in SDS e contrassegnati come _padre_ o _tutore_.</span><span class="sxs-lookup"><span data-stu-id="eb936-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="eb936-124">Per informazioni dettagliate, vedere [formato di file di sincronizzazione padre e tutore](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="eb936-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="eb936-125">Gli studenti appartengono ad almeno una classe in cui il messaggio di posta elettronica non viene disabilitato dall'insegnante nelle [impostazioni di assegnazione](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span><span class="sxs-lookup"><span data-stu-id="eb936-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="eb936-126">I messaggi di posta elettronica conterranno informazioni sulle assegnazioni che avevano una data di scadenza nella settimana precedente o nella settimana successiva.</span><span class="sxs-lookup"><span data-stu-id="eb936-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="eb936-127">L'impostazione predefinita per questa caratteristica è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="eb936-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="eb936-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="eb936-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="eb936-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="eb936-129">MakeCode</span></span>
<span data-ttu-id="eb936-130">Microsoft MakeCode è una piattaforma di codifica basata su blocchi che consente di portare in vita l'informatica per tutti gli studenti.</span><span class="sxs-lookup"><span data-stu-id="eb936-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="eb936-131">MakeCode è un prodotto Microsoft soggetto alle [condizioni d'uso](https://go.microsoft.com/fwlink/?LinkID=206977) e ai criteri di [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb936-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="eb936-132">L'impostazione predefinita per questa caratteristica è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="eb936-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="eb936-133">Per abilitare le assegnazioni di MakeCode in teams, passare all'interfaccia di **amministrazione di teams**, passare alla sezione **assegnazioni** e attivare l'opzione toggle MakeCode **su** attivato.</span><span class="sxs-lookup"><span data-stu-id="eb936-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="eb936-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eb936-134">Click **Save**.</span></span> <span data-ttu-id="eb936-135">Per rendere effettive queste impostazioni, attendere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="eb936-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="eb936-136">Per altre informazioni sul funzionamento di questa funzionalità, vedere questa [dimostrazione video](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="eb936-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="eb936-137">Leggi [altre informazioni su MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="eb936-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="eb936-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="eb936-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="eb936-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="eb936-139">Turnitin</span></span>

<span data-ttu-id="eb936-140">[Turnitin](https://www.turnitin.com/) è un servizio di integrità accademica.</span><span class="sxs-lookup"><span data-stu-id="eb936-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="eb936-141">Si tratta di un prodotto o un servizio di terze parti soggetto ai propri termini e alla propria politica sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="eb936-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="eb936-142">L'utente è responsabile dell'uso di prodotti e servizi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="eb936-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="eb936-143">L'impostazione predefinita per questa caratteristica è- **off**.</span><span class="sxs-lookup"><span data-stu-id="eb936-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="eb936-144">Per abilitare Turnitin per l'organizzazione, sarà necessario un abbonamento a Turnitin.</span><span class="sxs-lookup"><span data-stu-id="eb936-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="eb936-145">Puoi quindi inserire le informazioni seguenti, che possono essere trovate nella console di amministrazione di Turnitin:</span><span class="sxs-lookup"><span data-stu-id="eb936-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="eb936-146">**TurnitinApiKey**: questo è un GUID di 32-character trovato nella console di amministrazione in Integrations.</span><span class="sxs-lookup"><span data-stu-id="eb936-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="eb936-147">**TurnitinApiUrl**: questo è l'URL HTTPS della console di amministrazione di Turnitin.</span><span class="sxs-lookup"><span data-stu-id="eb936-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="eb936-148">Ecco alcune istruzioni utili per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="eb936-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="eb936-149">**TurnitinApiUrl** è l'indirizzo host della console di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="eb936-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="eb936-150">Esempio `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="eb936-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="eb936-151">La console di amministrazione è la posizione in cui è possibile creare un'integrazione e una chiave API associata all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="eb936-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="eb936-152">Selezionare **integrazioni** dal menu laterale, quindi fare clic su **Aggiungi integrazione** e assegnare un nome all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="eb936-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="eb936-154">Il **TurnitinApiKey** verrà assegnato dopo aver seguito le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="eb936-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="eb936-155">Copiare la chiave API e incollarla nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="eb936-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="eb936-156">Questa è l'unica volta che è possibile visualizzare la chiave.</span><span class="sxs-lookup"><span data-stu-id="eb936-156">This is the only time you can view the key.</span></span>

![Schermata che mostra la copia della chiave API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="eb936-158">Dopo aver fatto clic sul pulsante **Salva** nell'interfaccia di amministrazione per questa impostazione, è possibile che le impostazioni siano effettive in poche ore.</span><span class="sxs-lookup"><span data-stu-id="eb936-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

