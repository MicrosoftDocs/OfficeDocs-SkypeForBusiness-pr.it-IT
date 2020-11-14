---
title: Introduzione alla registrazione basata sui criteri per i team per chiamare & riunioni
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulla registrazione basata su criteri team per la chiamata di & riunioni
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61fbce79fc528f4b69baed9c08a8dabc9d40ed4a
ms.sourcegitcommit: 76fc38fe1fbbd93bf2815c57e66fc479df34d929
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002198"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="3dbb2-103">Introduzione alla registrazione basata sui criteri per i team per le chiamate & riunioni</span><span class="sxs-lookup"><span data-stu-id="3dbb2-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="3dbb2-104">La registrazione basata su criteri consente alle organizzazioni che adottano Microsoft teams per la chiamata e le riunioni di stabilire, usando un criterio amministrativo, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai pertinenti criteri aziendali o normativi.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="3dbb2-105">Teams è stato migliorato per supportare l'integrazione di soluzioni di registrazione di terze parti, incluse le funzionalità della piattaforma, le esperienze degli utenti e le interfacce amministrative necessarie per creare una soluzione completa per la configurazione, la gestione, la registrazione, l'archiviazione e l'analisi delle comunicazioni di teams.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="3dbb2-106">Sono incluse le API della piattaforma di comunicazione e gli eventi per la registrazione, che offrono:</span><span class="sxs-lookup"><span data-stu-id="3dbb2-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="3dbb2-107">Acquisizione multimediale senza soluzione di continuità e di alta qualità tra dispositivi e tutti gli endpoint supportati per audio, video, condivisione dello schermo e chat.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="3dbb2-108">Supporto per l'acquisizione dell'interazione tra utenti di team e endpoint di chiamata supportati (teams, teams mobile, Skype for business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="3dbb2-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="3dbb2-109">Nuovi criteri amministrativi per la registrazione della conformità, inclusa l'integrazione con i team e i criteri di gestione delle chiamate e delle riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="3dbb2-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="3dbb2-110">La registrazione della conformità può essere abilitata negli utenti Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="3dbb2-111">Le funzionalità di integrazione della soluzione per la registrazione della conformità sono state esaminate anche in Ignite 2019 nella [<span class="underline">sessione di registrazione conformità e Microsoft teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="3dbb2-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="3dbb2-112">Panoramica della registrazione delle interazioni tra Teams</span><span class="sxs-lookup"><span data-stu-id="3dbb2-112">Teams interaction recording overview</span></span>

<span data-ttu-id="3dbb2-113">I casi di utilizzo della registrazione delle interazioni possono essere effettivamente separati in quattro categorie principali di funzionalità di registrazione: convenienza, funzionalità, organizzazione e intercettazione lecite, come illustrato nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="3dbb2-114">![Screenshot che mostra la registrazione delle interazioni che cosa e perché.](media/recording-taxonomy.png "L'immagine mostra le categorie di registrazione.")</span><span class="sxs-lookup"><span data-stu-id="3dbb2-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="3dbb2-115">Ognuna delle categorie comporta requisiti diversi per il modo in cui vengono avviate le registrazioni, cosa viene registrato, in cui vengono archiviate le registrazioni, chi viene avvisato, chi controlla l'accesso e come viene gestito il mantenimento.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="3dbb2-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="3dbb2-116">Type</span></span>                   | <span data-ttu-id="3dbb2-117">Convenienza</span><span class="sxs-lookup"><span data-stu-id="3dbb2-117">Convenience</span></span>        | <span data-ttu-id="3dbb2-118">Funzionale</span><span class="sxs-lookup"><span data-stu-id="3dbb2-118">Functional</span></span>         | <span data-ttu-id="3dbb2-119">Org-generale</span><span class="sxs-lookup"><span data-stu-id="3dbb2-119">Org - General</span></span>      | <span data-ttu-id="3dbb2-120">Org-regolato</span><span class="sxs-lookup"><span data-stu-id="3dbb2-120">Org - Regulated</span></span> | <span data-ttu-id="3dbb2-121">Intercettazione legale</span><span class="sxs-lookup"><span data-stu-id="3dbb2-121">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="3dbb2-122">Iniziatore</span><span class="sxs-lookup"><span data-stu-id="3dbb2-122">Initiator</span></span>              | <span data-ttu-id="3dbb2-123">Utente</span><span class="sxs-lookup"><span data-stu-id="3dbb2-123">User</span></span>               | <span data-ttu-id="3dbb2-124">App/soluzione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-124">App/Solution</span></span>       | <span data-ttu-id="3dbb2-125">Amministratore (sistema)</span><span class="sxs-lookup"><span data-stu-id="3dbb2-125">Admin (system)</span></span>     | <span data-ttu-id="3dbb2-126">Amministratore (sistema)</span><span class="sxs-lookup"><span data-stu-id="3dbb2-126">Admin (system)</span></span>  | <span data-ttu-id="3dbb2-127">LEA</span><span class="sxs-lookup"><span data-stu-id="3dbb2-127">LEA</span></span>                |
| <span data-ttu-id="3dbb2-128">Destinazione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-128">Target</span></span>                 | <span data-ttu-id="3dbb2-129">Per chiamata/riunione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-129">Per-call / meeting</span></span> | <span data-ttu-id="3dbb2-130">Per chiamata/riunione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-130">Per-call / meeting</span></span> | <span data-ttu-id="3dbb2-131">Per chiamata/riunione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-131">Per-call / meeting</span></span> | <span data-ttu-id="3dbb2-132">Per utente</span><span class="sxs-lookup"><span data-stu-id="3dbb2-132">Per-user</span></span>        | <span data-ttu-id="3dbb2-133">Per-endpoint/DID</span><span class="sxs-lookup"><span data-stu-id="3dbb2-133">Per-endpoint / DID</span></span> |
| <span data-ttu-id="3dbb2-134">Proprietario dello spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-134">Storage owner</span></span>          | <span data-ttu-id="3dbb2-135">Utente</span><span class="sxs-lookup"><span data-stu-id="3dbb2-135">User</span></span>               | <span data-ttu-id="3dbb2-136">App</span><span class="sxs-lookup"><span data-stu-id="3dbb2-136">App</span></span>                | <span data-ttu-id="3dbb2-137">Admin</span><span class="sxs-lookup"><span data-stu-id="3dbb2-137">Admin</span></span>              | <span data-ttu-id="3dbb2-138">Conformità</span><span class="sxs-lookup"><span data-stu-id="3dbb2-138">Compliance</span></span>      | <span data-ttu-id="3dbb2-139">LEA</span><span class="sxs-lookup"><span data-stu-id="3dbb2-139">LEA</span></span>                |
| <span data-ttu-id="3dbb2-140">Notifica obbligatoria?</span><span class="sxs-lookup"><span data-stu-id="3dbb2-140">Notification required?</span></span> | <span data-ttu-id="3dbb2-141">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-141">Yes</span></span>                | <span data-ttu-id="3dbb2-142">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-142">Yes</span></span>                | <span data-ttu-id="3dbb2-143">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-143">Yes</span></span>                | <span data-ttu-id="3dbb2-144">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-144">Yes</span></span>             | <span data-ttu-id="3dbb2-145">No</span><span class="sxs-lookup"><span data-stu-id="3dbb2-145">No</span></span>                 |
| <span data-ttu-id="3dbb2-146">Proprietario di Access</span><span class="sxs-lookup"><span data-stu-id="3dbb2-146">Access Owner</span></span>           | <span data-ttu-id="3dbb2-147">Utente</span><span class="sxs-lookup"><span data-stu-id="3dbb2-147">User</span></span>               | <span data-ttu-id="3dbb2-148">App</span><span class="sxs-lookup"><span data-stu-id="3dbb2-148">App</span></span>                | <span data-ttu-id="3dbb2-149">Admin</span><span class="sxs-lookup"><span data-stu-id="3dbb2-149">Admin</span></span>              | <span data-ttu-id="3dbb2-150">Conformità</span><span class="sxs-lookup"><span data-stu-id="3dbb2-150">Compliance</span></span>      | <span data-ttu-id="3dbb2-151">LEA</span><span class="sxs-lookup"><span data-stu-id="3dbb2-151">LEA</span></span>                |
| <span data-ttu-id="3dbb2-152">Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-152">Retention Policy?</span></span>      | <span data-ttu-id="3dbb2-153">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="3dbb2-153">Optional</span></span>           | <span data-ttu-id="3dbb2-154">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-154">Yes</span></span>                | <span data-ttu-id="3dbb2-155">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-155">Yes</span></span>                | <span data-ttu-id="3dbb2-156">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-156">Yes</span></span>             | <span data-ttu-id="3dbb2-157">Sì</span><span class="sxs-lookup"><span data-stu-id="3dbb2-157">Yes</span></span>                |

<span data-ttu-id="3dbb2-158">Teams offre varie funzionalità per [<span class="underline">una registrazione comoda</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) e funzionale per riunioni e eventi live.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-158">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="3dbb2-159">La registrazione organizzativa consente alle organizzazioni che adottano team per la chiamata e le riunioni di stipulare, tramite criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai pertinenti criteri aziendali o normativi.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-159">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="3dbb2-160">Gli utenti in questo criterio sapranno che le loro interazioni digitali con i team vengono registrate ma non saranno in grado di disabilitare la registrazione e non avranno accesso alla registrazione dopo il completamento dell'interazione.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-160">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="3dbb2-161">La registrazione diventa parte dell'archivio organizzativo disponibile per la conformità e il personale legale per eDiscovery, blocco legale e altri usi di conservazione aziendale.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-161">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="3dbb2-162">Esempio di esigenze degli utenti</span><span class="sxs-lookup"><span data-stu-id="3dbb2-162">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbb2-163"><strong>Utente tipo</strong></span><span class="sxs-lookup"><span data-stu-id="3dbb2-163"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="3dbb2-164"><strong>Deve</strong></span><span class="sxs-lookup"><span data-stu-id="3dbb2-164"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3dbb2-165">Utenti registrati</span><span class="sxs-lookup"><span data-stu-id="3dbb2-165">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="3dbb2-166">Ricevere una notifica quando la registrazione è in corso.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-166">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-167">Essere informati quando i criteri e/o l'errore del registratore causano modifiche al comportamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-167">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3dbb2-168">Amministratore delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="3dbb2-168">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="3dbb2-169">Capire perché e come applicare/applicare i criteri di registrazione agli utenti/endpoint di teams.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-169">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-170">Configurare e gestire i criteri di registrazione dei team per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-170">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-171">Monitorare e risolvere i problemi relativi alla registrazione con le chiamate e le riunioni del team.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-171">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-172">Supportare Internal Compliance Officer con analisi operativa sull'uso, la qualità e l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-172">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3dbb2-173">Responsabile della conformità</span><span class="sxs-lookup"><span data-stu-id="3dbb2-173">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="3dbb2-174">Raccogliere tutte le comunicazioni di Teams nel modo necessario per rispettare gli obblighi di conformità nei limiti regionali appropriati.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-174">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-175">Cercare interazioni basate su metadati correlati alla comunicazione o sul contenuto di interazione.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-175">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="3dbb2-176">Gli esempi comuni includono:</span><span class="sxs-lookup"><span data-stu-id="3dbb2-176">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3dbb2-177"><strong>Metadati</strong> - Partecipanti, ora, direzione, numero di telefono, numero di origine, dati aziendali personalizzati</span><span class="sxs-lookup"><span data-stu-id="3dbb2-177"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-178"><strong>Contenuto</strong> : trascrizione, sentimento, fonetica, interazioni correlate</span><span class="sxs-lookup"><span data-stu-id="3dbb2-178"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="3dbb2-179">Analizzare e interagire con le comunicazioni raccolte, inclusa la possibilità di monitorare le interazioni Man mano che vengono raccolte.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-179">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="3dbb2-180">Garantire la sicurezza delle comunicazioni raccolte e impedire manomissioni in tutte le fasi.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-180">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="3dbb2-181">Panoramica dell'architettura della soluzione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-181">Solution architecture overview</span></span>

<span data-ttu-id="3dbb2-182">Le soluzioni di registrazione conformità sono integrate con i team, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="3dbb2-182">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="3dbb2-183">![Schermata che mostra l'impostazione dell'app personalizzata del team](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Le immagini mostrano il flusso quando viene inviata e ricevuta una riunione o una chiamata di teams.")</span><span class="sxs-lookup"><span data-stu-id="3dbb2-183">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="3dbb2-184">Registratore</span><span class="sxs-lookup"><span data-stu-id="3dbb2-184">Recorder</span></span>

<span data-ttu-id="3dbb2-185">Il componente principale della soluzione di registrazione della conformità è il registratore.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-185">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="3dbb2-186">I registratori vengono creati come servizi basati su Azure scalabili (bot) che [<span class="underline">sfruttano la piattaforma di comunicazioni Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) e si iscrivono come applicazioni con Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-186">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="3dbb2-187">Il registratore fornisce l'interazione diretta con le [<span class="underline">API della piattaforma di comunicazione</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) per le chiamate e le riunioni di teams e fornisce l'endpoint per l'ingestione media.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-187">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="3dbb2-188">[<span class="underline">È disponibile un'applicazione di registrazione di conformità di esempio</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) che Mostra come configurare il bot, creare l'istanza dell'app e assegnare i criteri di conformità.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-188">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="3dbb2-189">L'esempio contiene anche esempi sull'uso delle API per la registrazione di interazioni specifiche, ad esempio la gestione del routing delle [<span class="underline">chiamate in arrivo</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , la [<span class="underline">modifica degli Stati di registrazione</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)e [<span class="underline">la rimozione dell'utente che viene registrato</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="3dbb2-189">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="3dbb2-190">La documentazione del grafico sulle API specifiche può essere trovata qui per [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) e [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="3dbb2-190">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="3dbb2-191">L'implementazione esatta del servizio registratore varia in base al partner, ma deve essere progettata per supportare più Recorder per ottenere elevata disponibilità e distribuzione geografica della distribuzione per ridurre la latenza dei team al registratore.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-191">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="3dbb2-192">Si prevede inoltre che i registratori siano progettati con flessibilità e ridondanza.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-192">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="3dbb2-193">I partner devono confermare la versione minima richiesta di Microsoft Graph Communications API e SDK con Microsoft prima di inviare la soluzione per la certificazione per assicurarsi che siano supportati tutti i requisiti di integrazione della registrazione di conformità.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-193">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="3dbb2-194">Due requisiti specifici fondamentali per lo scenario di registrazione della conformità sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3dbb2-194">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="3dbb2-195">Recorder bot deve essere distribuito in Azure</span><span class="sxs-lookup"><span data-stu-id="3dbb2-195">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="3dbb2-196">Recorder bot deve essere eseguito in una VM di Windows in Azure</span><span class="sxs-lookup"><span data-stu-id="3dbb2-196">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="3dbb2-197">I requisiti di Azure e Windows VM si applicano solo al componente teams bot, il che significa che un partner può implementare il resto della piattaforma di propria scelta purché soddisfi i requisiti di prestazioni e funzionalità necessari per la registrazione della conformità.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-197">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="3dbb2-198">Assegnazione e provisioning dei criteri di registrazione conformità</span><span class="sxs-lookup"><span data-stu-id="3dbb2-198">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="3dbb2-199">Gli amministratori IT possono determinare gli utenti da registrare e il registratore che verrà usato per ogni utente, creando e assegnando criteri di registrazione della conformità.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-199">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="3dbb2-200">I registratori vengono automaticamente invitati a partecipare alle conversazioni in base alla configurazione di questi criteri quando si verifica un'interazione di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-200">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="3dbb2-201">I criteri di registrazione della conformità vengono gestiti con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) e possono essere applicati a livello di tenant, per utente e gruppo di sicurezza per ogni organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-201">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="3dbb2-202">Per altre informazioni, vedere documenti Microsoft per [<span class="underline">criteri di riunione</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), criteri di [<span class="underline">chiamata</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) e  [<span class="underline">criteri di gruppo</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="3dbb2-202">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="3dbb2-203">Creare un'istanza dell'applicazione nel tenant.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-203">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="3dbb2-204">Creare un criterio di registrazione conformità.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-204">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="3dbb2-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="3dbb2-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="3dbb2-206">Assegnare i criteri di registrazione conformità a un utente.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-206">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="3dbb2-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="3dbb2-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="3dbb2-208">Esperienze utente</span><span class="sxs-lookup"><span data-stu-id="3dbb2-208">User experiences</span></span>

<span data-ttu-id="3dbb2-209">Il supporto per le notifiche viene abilitato tramite le esperienze del client teams.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-209">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="3dbb2-210">Le esperienze possono essere visive o audio.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-210">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="3dbb2-211">**Client teams-avviso visivo**</span><span class="sxs-lookup"><span data-stu-id="3dbb2-211">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="3dbb2-212">Desktop/Web</span><span class="sxs-lookup"><span data-stu-id="3dbb2-212">Desktop/web</span></span>
- <span data-ttu-id="3dbb2-213">Dispositivi mobili (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="3dbb2-213">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="3dbb2-214">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="3dbb2-214">Teams phones</span></span>
- <span data-ttu-id="3dbb2-215">Sale Teams</span><span class="sxs-lookup"><span data-stu-id="3dbb2-215">Teams rooms</span></span>

<span data-ttu-id="3dbb2-216">**Altri endpoint-avviso audio**</span><span class="sxs-lookup"><span data-stu-id="3dbb2-216">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="3dbb2-217">Telefoni SIP</span><span class="sxs-lookup"><span data-stu-id="3dbb2-217">SIP phones</span></span>
- <span data-ttu-id="3dbb2-218">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3dbb2-218">Skype for Business</span></span>
- <span data-ttu-id="3dbb2-219">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3dbb2-219">Audio conferencing</span></span>
- <span data-ttu-id="3dbb2-220">Chiamanti PSTN</span><span class="sxs-lookup"><span data-stu-id="3dbb2-220">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="3dbb2-221">Registrazione della conformità per i programmi di certificazione Teams</span><span class="sxs-lookup"><span data-stu-id="3dbb2-221">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="3dbb2-222">Oltre a pubblicare le API pubblicamente disponibili per consentire ai partner di sviluppare e integrare soluzioni CCaaS con teams, abbiamo sviluppato la registrazione di conformità per il programma di certificazione Microsoft teams per garantire ai clienti la garanzia che la soluzione di ogni partner sia stata testata e verificata per garantire la qualità, la compatibilità e l'affidabilità che si aspettano da soluzioni Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-222">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="3dbb2-223">I partner seguenti hanno certificato la soluzione per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-223">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="3dbb2-224">Partner</span><span class="sxs-lookup"><span data-stu-id="3dbb2-224">Partner</span></span>|<span data-ttu-id="3dbb2-225">Sito Web della soluzione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-225">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="3dbb2-226">PIACEVOLE</span><span class="sxs-lookup"><span data-stu-id="3dbb2-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="3dbb2-227">I partner seguenti sono in procinto di certificare la loro soluzione per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-227">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="3dbb2-228">Partner</span><span class="sxs-lookup"><span data-stu-id="3dbb2-228">Partner</span></span>|<span data-ttu-id="3dbb2-229">Sito Web della soluzione</span><span class="sxs-lookup"><span data-stu-id="3dbb2-229">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="3dbb2-230">ASC Technologies</span><span class="sxs-lookup"><span data-stu-id="3dbb2-230">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="3dbb2-231">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="3dbb2-231">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="3dbb2-232">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="3dbb2-232">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="3dbb2-233">Doppiatore</span><span class="sxs-lookup"><span data-stu-id="3dbb2-233">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="3dbb2-234">Tecnologie Landis</span><span class="sxs-lookup"><span data-stu-id="3dbb2-234">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="3dbb2-235">Luware</span><span class="sxs-lookup"><span data-stu-id="3dbb2-235">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="3dbb2-236">Numonix</span><span class="sxs-lookup"><span data-stu-id="3dbb2-236">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="3dbb2-237">Innovazione per Oak</span><span class="sxs-lookup"><span data-stu-id="3dbb2-237">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="3dbb2-238">Casella rossa</span><span class="sxs-lookup"><span data-stu-id="3dbb2-238">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="3dbb2-239">Verit</span><span class="sxs-lookup"><span data-stu-id="3dbb2-239">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="3dbb2-240">Questo elenco verrà aggiornato man mano che altri partner partecipano e soddisfano i criteri di certificazione.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-240">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3dbb2-241">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3dbb2-241">Next steps</span></span>

<span data-ttu-id="3dbb2-242">Se si è un fornitore che cerca di partecipare al programma di certificazione, inviare la posta  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="3dbb2-242">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
