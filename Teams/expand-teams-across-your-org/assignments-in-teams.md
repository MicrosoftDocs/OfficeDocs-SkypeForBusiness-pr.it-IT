---
title: Attività per Teams
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
description: Informazioni su come gestire le attività nell'Microsoft Teams di amministrazione di Teams per l'istruzione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: abf17b12e8555ce12642627093d856f917dce439
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004148"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="d2b0b-103">Assegnare attività in Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="d2b0b-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="d2b0b-104">Le funzionalità Attività e voti in Teams per l'istruzione i docenti possono assegnare attività, lavoro o quiz agli studenti.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="d2b0b-105">I docenti possono gestire le sequenze temporali delle assegnazioni, le istruzioni, aggiungere risorse per l'assegnazione, classificare con le rubriche e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="d2b0b-106">Possono anche tenere traccia dello stato di avanzamento della classe e dei singoli studenti nella scheda Voti.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="d2b0b-107">[Altre informazioni su Attività e voti in Teams per l'istruzione.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)</span><span class="sxs-lookup"><span data-stu-id="d2b0b-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="d2b0b-108">Per informazioni dettagliate Teams attività su piattaforme diverse, vedere Teams [funzionalità per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="d2b0b-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d2b0b-109">Integrazioni di assegnazioni nell'interfaccia Microsoft Teams di amministrazione</span><span class="sxs-lookup"><span data-stu-id="d2b0b-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="d2b0b-110">Usando le impostazioni di amministrazione nell'Microsoft Teams di amministrazione, è possibile attivare o disattivare le funzionalità per i docenti all'interno dell'organizzazione e per i loro studenti.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="d2b0b-111">Di seguito sono riportate le impostazioni relative alle attività:</span><span class="sxs-lookup"><span data-stu-id="d2b0b-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="d2b0b-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="d2b0b-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="d2b0b-113">Digest della posta elettronica del tutore settimanale</span><span class="sxs-lookup"><span data-stu-id="d2b0b-113">Weekly guardian email digest</span></span>


<span data-ttu-id="d2b0b-114">I messaggi di posta elettronica dei tutori vengono inviati ogni fine settimana a genitori o tutori.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="d2b0b-115">Il messaggio di posta elettronica contiene informazioni sulle attività della settimana precedente e della settimana successiva.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="d2b0b-116">La sincronizzazione padre e tutore può essere impostata [usando School Data Sync.](/schooldatasync/parent-contact-sync)</span><span class="sxs-lookup"><span data-stu-id="d2b0b-116">The Parent and Guardian Sync can be setup using [School Data Sync](/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="d2b0b-117">Importare le informazioni sul contatto padre tramite Parent e Guardian Sync in SDS.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="d2b0b-118">Per istruzioni su come abilitare la sincronizzazione padre e tutore, vedere [Abilitazione della sincronizzazione padre e tutore.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)</span><span class="sxs-lookup"><span data-stu-id="d2b0b-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="d2b0b-119">Attivare l'impostazione Guardiano nell'Microsoft Teams di amministrazione, perché l'impostazione è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="d2b0b-120">In questo modo gli insegnanti potranno inviare un riepilogo settimanale.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d2b0b-121">Gli insegnanti possono rifiutare esplicitamente il digest deselezionando l'impostazione all'interno del proprio team di classe personale ( Attività Impostazioni >**e-mail genitori/tutori**).</span><span class="sxs-lookup"><span data-stu-id="d2b0b-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="d2b0b-122">Per verificare che genitori otterrà il messaggio di posta elettronica, i tre elementi seguenti devono essere veri:</span><span class="sxs-lookup"><span data-stu-id="d2b0b-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="d2b0b-123">Indirizzo di posta elettronica allegato al profilo dello studente in SDS e contrassegnato _come_ genitore o _tutore._</span><span class="sxs-lookup"><span data-stu-id="d2b0b-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="d2b0b-124">Per informazioni dettagliate, vedere [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="d2b0b-124">For details, see [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="d2b0b-125">Gli studenti appartengono ad almeno una classe in cui la posta elettronica non è disabilitata dal docente nelle [impostazioni dell'attività.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)</span><span class="sxs-lookup"><span data-stu-id="d2b0b-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="d2b0b-126">I messaggi di posta elettronica conterranno informazioni sulle attività che hanno una data di scadenza nella settimana precedente o nella settimana successiva.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="d2b0b-127">L'impostazione predefinita per questa funzionalità è - **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="d2b0b-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="d2b0b-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="d2b0b-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="d2b0b-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="d2b0b-129">MakeCode</span></span>
<span data-ttu-id="d2b0b-130">Microsoft MakeCode è una piattaforma di codifica basata su blocchi che dà vita all'informatica per tutti gli studenti.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="d2b0b-131">MakeCode è un prodotto Microsoft soggetto alle condizioni per l'uso [e](https://go.microsoft.com/fwlink/?LinkID=206977) alle condizioni [di privacy](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="d2b0b-132">L'impostazione predefinita per questa funzionalità è - **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="d2b0b-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="d2b0b-133">Per abilitare le assegnazioni MakeCode in Teams, passare all'interfaccia di  amministrazione di **Teams**, passare alla sezione Attività e impostare l'interruttore MakeCode su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="d2b0b-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-134">Click **Save**.</span></span> <span data-ttu-id="d2b0b-135">Consentire l'applicazione di queste impostazioni per alcune ore.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="d2b0b-136">Per altre informazioni sul funzionamento di questa funzionalità, vedere questa [dimostrazione video.](https://makecode.com/blog/teams/teams-assignments)</span><span class="sxs-lookup"><span data-stu-id="d2b0b-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="d2b0b-137">[Altre informazioni su MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="d2b0b-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="d2b0b-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="d2b0b-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="d2b0b-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="d2b0b-139">Turnitin</span></span>

<span data-ttu-id="d2b0b-140">[Turnitin è](https://www.turnitin.com/) un servizio di integrità accademica.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="d2b0b-141">Si tratta di un prodotto o servizio di terze parti soggetto alle proprie condizioni e all'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="d2b0b-142">L'utente è responsabile dell'uso di prodotti e servizi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="d2b0b-143">L'impostazione predefinita per questa caratteristica è - **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="d2b0b-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="d2b0b-144">Per abilitare Turnitin per l'organizzazione, è necessario un abbonamento Turnitin.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="d2b0b-145">È quindi possibile immettere le informazioni seguenti, disponibili nella console di amministrazione di Turnitin:</span><span class="sxs-lookup"><span data-stu-id="d2b0b-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="d2b0b-146">**TurnitinApiKey:** GUID di 32 caratteri trovato nella console di amministrazione in Integrazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="d2b0b-147">**TurnitinApiUrl:** URL HTTPS della console di amministrazione di Turnitin.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="d2b0b-148">Ecco alcune istruzioni per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="d2b0b-149">**TurnitinApiUrl è** l'indirizzo host della console di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="d2b0b-150">Esempio: `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="d2b0b-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="d2b0b-151">La console di amministrazione consente di creare un'integrazione e una chiave API associata all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="d2b0b-152">Selezionare **Integrazioni** dal menu laterale, quindi selezionare **Aggiungi** integrazione e assegnare un nome all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="d2b0b-154">**L'oggetto TurnitinApiKey** verrà assegnato dopo aver seguito le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="d2b0b-155">Copiare la chiave API e incollarla nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="d2b0b-156">Questa è l'unica volta in cui è possibile visualizzare la chiave.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-156">This is the only time you can view the key.</span></span>

![Screenshot che mostra la copia della chiave API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="d2b0b-158">Dopo aver fatto **clic sul pulsante** Salva nell'interfaccia di amministrazione per questa impostazione, consentire l'applicazione di queste impostazioni per alcune ore.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

### <a name="removing-assignments-and-grades"></a><span data-ttu-id="d2b0b-159">Rimozione di attività e voti</span><span class="sxs-lookup"><span data-stu-id="d2b0b-159">Removing Assignments and Grades</span></span>
<span data-ttu-id="d2b0b-160">È possibile usare i Teams per rimuovere assegnazioni e voti per un utente specifico o per l'intero tenant.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-160">You can use Teams policies to remove Assignments and Grades for a specific user or for your entire tenant.</span></span> 

<span data-ttu-id="d2b0b-161">Per rimuovere assegnazioni e voti per un singolo utente, passare **all'interfaccia** di amministrazione di Teams e passare alle app Teams **>** Criteri di autorizzazione per creare una nuova definizione dei criteri di autorizzazione delle app.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-161">To remove Assignments and Grades for an individual user, go to **Teams Admin Center** and navigate to **Teams apps > Permission policies** to create a new app permission policy definition.</span></span>  <span data-ttu-id="d2b0b-162">Quando si crea la nuova definizione dei  criteri, impostare i criteri delle **app Microsoft** su Blocca app specifiche e consentire a tutti gli altri utenti e aggiungere Attività **all'elenco** delle applicazioni bloccate.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-162">When creating the new policy definition, set the **Microsoft apps** policy to _Block specific apps and allow all others_ and add **Assignments** to the list of blocked applications.</span></span> <span data-ttu-id="d2b0b-163">Dopo aver salvato la nuova definizione dei criteri, assegnarla agli utenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-163">Once your new policy definition is saved, assign it to the appropriate users.</span></span>

<span data-ttu-id="d2b0b-164">Per rimuovere attività e voti per l'intero tenant, passare **Teams** Interfaccia di amministrazione, passare Teams app > Gestisci  **app** e cercare e selezionare Attività nell'elenco delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-164">To remove Assignments and Grades for your entire tenant, go to **Teams Admin Center**, navigate to **Teams apps > Manage apps**, and search for and select **Assignments** from the application list.</span></span> <span data-ttu-id="d2b0b-165">Modificare l'impostazione dello stato nella pagina Delle impostazioni dell'applicazione Assegnazione su _Bloccato_.</span><span class="sxs-lookup"><span data-stu-id="d2b0b-165">Change the status setting within the Assignment application settings page to _Blocked_.</span></span> 
