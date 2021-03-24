---
title: Introduzione alla registrazione basata su criteri di Teams per le chiamate & riunioni
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
description: Informazioni sulla registrazione basata su criteri di Teams per le chiamate & riunioni
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
ms.openlocfilehash: fd2b83c5b96ab9049783a774c56297b51179e68e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094036"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="79096-103">Introduzione alla registrazione basata su criteri di Teams per le chiamate & riunioni</span><span class="sxs-lookup"><span data-stu-id="79096-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="79096-104">La registrazione basata su criteri consente alle organizzazioni che adottano Microsoft Teams per le chiamate e le riunioni di stabilire, usando un criterio amministrativo, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai criteri aziendali o normativi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="79096-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="79096-105">Teams è stato migliorato per supportare l'integrazione di soluzioni di registrazione di terze parti, incluse le funzionalità della piattaforma, le esperienze utente e le interfacce amministrative necessarie per fornire una soluzione end-to-end per la configurazione, la gestione, la registrazione, l'archiviazione e l'analisi delle comunicazioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="79096-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="79096-106">I miglioramenti includono API ed eventi della piattaforma di comunicazione per la registrazione, che offre:</span><span class="sxs-lookup"><span data-stu-id="79096-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="79096-107">Acquisizione multimediale fluida e di alta qualità su tutti i dispositivi e tutti gli endpoint supportati per audio, video, condivisione dello schermo e chat.</span><span class="sxs-lookup"><span data-stu-id="79096-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="79096-108">Supporto per l'acquisizione dell'interazione tra gli utenti di Teams e gli endpoint di chiamata supportati (Teams, Teams Mobile, Skype for Business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="79096-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="79096-109">Nuovi criteri amministrativi per la registrazione della conformità, inclusa l'integrazione con gli strumenti e i criteri esistenti per le chiamate amministrative e le riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="79096-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="79096-110">La registrazione della conformità può essere abilitata per gli utenti di Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="79096-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="79096-111">Le funzionalità di integrazione della soluzione di registrazione della conformità sono state esaminate anche in Ignite 2019 nella sessione Registrazione conformità [<span class="underline">e Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)</span><span class="sxs-lookup"><span data-stu-id="79096-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="79096-112">Panoramica della registrazione delle interazioni di Teams</span><span class="sxs-lookup"><span data-stu-id="79096-112">Teams interaction recording overview</span></span>

<span data-ttu-id="79096-113">I casi di utilizzo della registrazione delle interazioni possono essere suddivisi in quattro categorie principali di funzionalità di registrazione: Convenienza, Funzionalità, Organizzazione e Intercetta legale, come illustrato nell'immagine:</span><span class="sxs-lookup"><span data-stu-id="79096-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="79096-114">![Screenshot che mostra l'interazione che registra cosa e perché.](media/recording-taxonomy.png "L'immagine mostra le categorie di registrazione.")</span><span class="sxs-lookup"><span data-stu-id="79096-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="79096-115">Ognuna di queste categorie richiede requisiti diversi per l'avvio delle registrazioni, gli elementi registrati, la posizione in cui vengono archiviate le registrazioni, chi viene avvisato, chi controlla l'accesso e come viene gestita la conservazione.</span><span class="sxs-lookup"><span data-stu-id="79096-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="79096-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="79096-116">Type</span></span>                   | <span data-ttu-id="79096-117">Convenienza (registrazione regolare di Teams)</span><span class="sxs-lookup"><span data-stu-id="79096-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="79096-118">Organizzazione - Regolamentata (Registrazione conformità)</span><span class="sxs-lookup"><span data-stu-id="79096-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="79096-119">Iniziatore</span><span class="sxs-lookup"><span data-stu-id="79096-119">Initiator</span></span>              | <span data-ttu-id="79096-120">Utente</span><span class="sxs-lookup"><span data-stu-id="79096-120">User</span></span>               | <span data-ttu-id="79096-121">Amministratore (sistema)</span><span class="sxs-lookup"><span data-stu-id="79096-121">Admin (system)</span></span>  |
| <span data-ttu-id="79096-122">Destinazione</span><span class="sxs-lookup"><span data-stu-id="79096-122">Target</span></span>                 | <span data-ttu-id="79096-123">Per chiamata/riunione</span><span class="sxs-lookup"><span data-stu-id="79096-123">Per-call / meeting</span></span> | <span data-ttu-id="79096-124">Per utente</span><span class="sxs-lookup"><span data-stu-id="79096-124">Per-user</span></span>        |
| <span data-ttu-id="79096-125">Proprietario dello spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="79096-125">Storage owner</span></span>          | <span data-ttu-id="79096-126">Utente</span><span class="sxs-lookup"><span data-stu-id="79096-126">User</span></span>               | <span data-ttu-id="79096-127">Conformità</span><span class="sxs-lookup"><span data-stu-id="79096-127">Compliance</span></span>      |
| <span data-ttu-id="79096-128">È necessaria una notifica?</span><span class="sxs-lookup"><span data-stu-id="79096-128">Notification required?</span></span> | <span data-ttu-id="79096-129">Sì</span><span class="sxs-lookup"><span data-stu-id="79096-129">Yes</span></span>                | <span data-ttu-id="79096-130">Sì</span><span class="sxs-lookup"><span data-stu-id="79096-130">Yes</span></span>             |
| <span data-ttu-id="79096-131">Proprietario dell'accesso</span><span class="sxs-lookup"><span data-stu-id="79096-131">Access Owner</span></span>           | <span data-ttu-id="79096-132">Utente</span><span class="sxs-lookup"><span data-stu-id="79096-132">User</span></span>               | <span data-ttu-id="79096-133">Conformità</span><span class="sxs-lookup"><span data-stu-id="79096-133">Compliance</span></span>      |
| <span data-ttu-id="79096-134">Criteri di conservazione?</span><span class="sxs-lookup"><span data-stu-id="79096-134">Retention Policy?</span></span>      | <span data-ttu-id="79096-135">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="79096-135">Optional</span></span>           | <span data-ttu-id="79096-136">Sì</span><span class="sxs-lookup"><span data-stu-id="79096-136">Yes</span></span>             |

<span data-ttu-id="79096-137">Teams offre varie funzionalità per [<span class="underline">la registrazione pratica</span>](./cloud-recording.md) e funzionale per riunioni ed eventi live.</span><span class="sxs-lookup"><span data-stu-id="79096-137">Teams provides various capabilities for [<span class="underline">convenient</span>](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="79096-138">Registrazione organizzativa significa consentire alle organizzazioni che adottano Teams per le chiamate e le riunioni di stabilire, tramite criteri amministrativi, quando le chiamate e le riunioni online devono essere registrate e acquisite automaticamente per l'elaborazione e la conservazione successive, come richiesto dai criteri aziendali o normativi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="79096-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="79096-139">Gli utenti ai sensi di questo criterio saranno consapevoli del fatto che le interazioni digitali con Teams vengono registrate, ma non saranno in grado di disabilitare la registrazione e non avranno accesso alla registrazione al termine dell'interazione.</span><span class="sxs-lookup"><span data-stu-id="79096-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="79096-140">La registrazione diventa parte dell'archivio aziendale disponibile per il personale legale e di conformità per eDiscovery, il blocco legale e altri usi di conservazione aziendale.</span><span class="sxs-lookup"><span data-stu-id="79096-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="79096-141">Esigenze degli utenti di esempio</span><span class="sxs-lookup"><span data-stu-id="79096-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="79096-142"><strong>Persona</strong></span><span class="sxs-lookup"><span data-stu-id="79096-142"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="79096-143"><strong>Esigenze</strong></span><span class="sxs-lookup"><span data-stu-id="79096-143"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="79096-144">Utenti registrati</span><span class="sxs-lookup"><span data-stu-id="79096-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="79096-145">Ricevere una notifica quando è in corso la registrazione.</span><span class="sxs-lookup"><span data-stu-id="79096-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="79096-146">Essere informati quando l'errore del criterio e/o del registratore causa modifiche al comportamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79096-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="79096-147">Amministratore delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="79096-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="79096-148">Comprendere perché e come applicare/applicare criteri di registrazione agli utenti/endpoint di Teams.</span><span class="sxs-lookup"><span data-stu-id="79096-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="79096-149">Configurare e gestire i criteri di registrazione di Teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79096-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="79096-150">Monitorare e risolvere i problemi relativi alla registrazione con le chiamate e le riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="79096-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="79096-151">Supportare il responsabile della conformità interna con analisi operative sull'utilizzo, la qualità e l'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="79096-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="79096-152">Responsabile della conformità</span><span class="sxs-lookup"><span data-stu-id="79096-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="79096-153">Raccogliere tutte le comunicazioni di Teams nel modo richiesto per rispettare gli obblighi di conformità nei confini regionali appropriati.</span><span class="sxs-lookup"><span data-stu-id="79096-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="79096-154">Cercare le interazioni in base ai metadati correlati alla comunicazione o al contenuto dell'interazione.</span><span class="sxs-lookup"><span data-stu-id="79096-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="79096-155">Di seguito sono riportati alcuni esempi comuni:</span><span class="sxs-lookup"><span data-stu-id="79096-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="79096-156"><strong>Metadati</strong> - Partecipanti, orario, direzione, numero composto, numero di origine, dati aziendali personalizzati</span><span class="sxs-lookup"><span data-stu-id="79096-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="79096-157"><strong>Contenuto:</strong> trascrizione, valutazione, fonetica, interazioni correlate</span><span class="sxs-lookup"><span data-stu-id="79096-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="79096-158">Analizzare e interagire con le comunicazioni raccolte, inclusa la possibilità di monitorare le interazioni durante la raccolta.</span><span class="sxs-lookup"><span data-stu-id="79096-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="79096-159">Garantire la sicurezza delle comunicazioni raccolte ed evitare manomissioni in tutte le fasi.</span><span class="sxs-lookup"><span data-stu-id="79096-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="79096-160">Panoramica dell'architettura della soluzione</span><span class="sxs-lookup"><span data-stu-id="79096-160">Solution architecture overview</span></span>

<span data-ttu-id="79096-161">Le soluzioni di registrazione della conformità sono integrate con Teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="79096-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="79096-162">![Screenshot che mostra l'impostazione dell'app personalizzata del team](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Le immagini mostrano il flusso quando viene inviata e ricevuta una riunione o una chiamata di Teams.")</span><span class="sxs-lookup"><span data-stu-id="79096-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="79096-163">Registratore</span><span class="sxs-lookup"><span data-stu-id="79096-163">Recorder</span></span>

<span data-ttu-id="79096-164">Il componente principale della soluzione di registrazione della conformità è il registratore.</span><span class="sxs-lookup"><span data-stu-id="79096-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="79096-165">I registratori sono creati come servizi scalabili basati su Azure (bot) che sfruttano la piattaforma di comunicazione [<span class="underline">Microsoft</span>](/graph/cloud-communications-concept-overview) e si registrano come applicazioni con Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="79096-165">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="79096-166">Il registratore fornisce l'interazione diretta con le [<span class="underline">API</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) della piattaforma di comunicazione di chiamate e riunioni di Teams e fornisce l'endpoint per l'inserimento di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="79096-166">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="79096-167">È [<span class="underline">disponibile un'applicazione di registrazione conformità</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) di esempio che mostra come configurare il bot, creare l'istanza dell'app e assegnare i criteri di conformità.</span><span class="sxs-lookup"><span data-stu-id="79096-167">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="79096-168">L'esempio include anche esempi sull'utilizzo dell'API per la registrazione di interazioni [<span class="underline">specifiche,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)ad esempio la gestione del [<span class="underline">routing</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) delle chiamate in arrivo, la modifica degli stati di registrazione e la rimozione dell'utente che [<span class="underline">viene registrato.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)</span><span class="sxs-lookup"><span data-stu-id="79096-168">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="79096-169">La documentazione del grafico sulle API specifiche è disponibile qui per [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) e [<span class="underline">incomingContext.</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="79096-169">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="79096-170">L'implementazione esatta del servizio di registrazione varia in base al partner, ma deve essere progettata per supportare più registratori per ottenere la disponibilità elevata e la distribuzione geografica della distribuzione per ridurre la latenza da Teams al registratore.</span><span class="sxs-lookup"><span data-stu-id="79096-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="79096-171">Inoltre, è previsto che i registratori stessi siano progettati in base alla resilienza e alla ridondanza.</span><span class="sxs-lookup"><span data-stu-id="79096-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="79096-172">I partner devono confermare la versione minima richiesta delle API di comunicazione e degli SDK di Microsoft Graph con Microsoft prima di inviare la soluzione per la certificazione per assicurarsi che tutti i requisiti di integrazione della registrazione della conformità siano supportati.</span><span class="sxs-lookup"><span data-stu-id="79096-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="79096-173">Due requisiti specifici fondamentali per lo scenario di registrazione della conformità sono:</span><span class="sxs-lookup"><span data-stu-id="79096-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="79096-174">Il bot registratore deve essere distribuito in Azure</span><span class="sxs-lookup"><span data-stu-id="79096-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="79096-175">Il bot registratore deve essere eseguito in una macchina virtuale Windows in Azure</span><span class="sxs-lookup"><span data-stu-id="79096-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="79096-176">I requisiti di Azure e della macchina virtuale di Windows si applicano solo al componente Bot di Teams, il che significa che un partner può implementare il resto della piattaforma di propria scelta a condizione che soddisfi i requisiti di prestazioni e funzionalità pertinenti per la registrazione della conformità.</span><span class="sxs-lookup"><span data-stu-id="79096-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="79096-177">Assegnazione e provisioning dei criteri di registrazione della conformità</span><span class="sxs-lookup"><span data-stu-id="79096-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="79096-178">Gli amministratori IT possono determinare quali utenti devono essere registrati e quale registratore verrà usato per ogni utente, creando e assegnando criteri di registrazione di conformità.</span><span class="sxs-lookup"><span data-stu-id="79096-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="79096-179">I registratori vengono invitati automaticamente a partecipare alle conversazioni in base alla configurazione di questi criteri quando si verifica un'interazione di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="79096-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="79096-180">I criteri di registrazione della conformità vengono gestiti [<span class="underline">con Microsoft PowerShell</span>](./teams-powershell-overview.md) e possono essere applicati a livello di tenant, per utente e gruppo di sicurezza per ogni organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79096-180">Compliance recording policies are managed using [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="79096-181">Per altre informazioni, vedere Microsoft Docs for [<span class="underline">Meeting policies,</span>](./meeting-policies-in-teams.md) [<span class="underline">calling policies</span>](./teams-calling-policy.md) e [<span class="underline">group policies.</span>](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="79096-181">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](./meeting-policies-in-teams.md), [<span class="underline">calling policies</span>](./teams-calling-policy.md) and  [<span class="underline">group policies</span>](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="79096-182">Creare un'istanza dell'applicazione nel tenant.</span><span class="sxs-lookup"><span data-stu-id="79096-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="79096-183">Creare criteri di registrazione conformità.</span><span class="sxs-lookup"><span data-stu-id="79096-183">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="79096-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="79096-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="79096-185">Assegnare i criteri registrazione conformità a un utente.</span><span class="sxs-lookup"><span data-stu-id="79096-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="79096-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="79096-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="79096-187">Esperienze utente</span><span class="sxs-lookup"><span data-stu-id="79096-187">User experiences</span></span>

<span data-ttu-id="79096-188">Il supporto per le notifiche è abilitato usando le esperienze client di Teams.</span><span class="sxs-lookup"><span data-stu-id="79096-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="79096-189">Le esperienze possono essere visive o audio.</span><span class="sxs-lookup"><span data-stu-id="79096-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="79096-190">**Client di Teams - avviso visivo**</span><span class="sxs-lookup"><span data-stu-id="79096-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="79096-191">Desktop/Web</span><span class="sxs-lookup"><span data-stu-id="79096-191">Desktop/web</span></span>
- <span data-ttu-id="79096-192">Mobile (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="79096-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="79096-193">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="79096-193">Teams phones</span></span>
- <span data-ttu-id="79096-194">Sale di Teams</span><span class="sxs-lookup"><span data-stu-id="79096-194">Teams rooms</span></span>

<span data-ttu-id="79096-195">**Altri endpoint - avviso audio**</span><span class="sxs-lookup"><span data-stu-id="79096-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="79096-196">Telefoni SIP</span><span class="sxs-lookup"><span data-stu-id="79096-196">SIP phones</span></span>
- <span data-ttu-id="79096-197">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="79096-197">Skype for Business</span></span>
- <span data-ttu-id="79096-198">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="79096-198">Audio conferencing</span></span>
- <span data-ttu-id="79096-199">Chiamanti PSTN</span><span class="sxs-lookup"><span data-stu-id="79096-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="79096-200">Registrazione della conformità per i programmi di certificazione di Teams</span><span class="sxs-lookup"><span data-stu-id="79096-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="79096-201">Oltre a pubblicare API disponibili pubblicamente che consentono ai partner di sviluppare e integrare soluzioni CCaaS con Teams, abbiamo sviluppato la registrazione della conformità per il programma di certificazione Microsoft Teams per fornire ai clienti la certezza che la soluzione di ogni partner partecipante sia stata testata e verificata per fornire la qualità, la compatibilità e l'affidabilità che si aspettano dalle soluzioni Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79096-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="79096-202">I partner seguenti hanno certificato la propria soluzione per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79096-202">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="79096-203">Partner</span><span class="sxs-lookup"><span data-stu-id="79096-203">Partner</span></span>|<span data-ttu-id="79096-204">Sito Web della soluzione</span><span class="sxs-lookup"><span data-stu-id="79096-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="79096-205">ASC Technologies</span><span class="sxs-lookup"><span data-stu-id="79096-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="79096-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="79096-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="79096-207">Dubber</span><span class="sxs-lookup"><span data-stu-id="79096-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="79096-208">NIZZA</span><span class="sxs-lookup"><span data-stu-id="79096-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="79096-209">I partner seguenti stanno certificando la soluzione per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79096-209">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="79096-210">Partner</span><span class="sxs-lookup"><span data-stu-id="79096-210">Partner</span></span>|<span data-ttu-id="79096-211">Sito Web della soluzione</span><span class="sxs-lookup"><span data-stu-id="79096-211">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="79096-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="79096-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="79096-213">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="79096-213">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="79096-214">Luware</span><span class="sxs-lookup"><span data-stu-id="79096-214">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="79096-215">Numonix</span><span class="sxs-lookup"><span data-stu-id="79096-215">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="79096-216">Innovazione quercia</span><span class="sxs-lookup"><span data-stu-id="79096-216">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="79096-217">Casella rossa</span><span class="sxs-lookup"><span data-stu-id="79096-217">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="79096-218">Verint</span><span class="sxs-lookup"><span data-stu-id="79096-218">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="79096-219">Questo elenco verrà aggiornato man appena altri partner si uniranno e soddisfino i criteri di certificazione.</span><span class="sxs-lookup"><span data-stu-id="79096-219">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="79096-220">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="79096-220">Next steps</span></span>

<span data-ttu-id="79096-221">Se si è un fornitore che cerca di partecipare al programma di certificazione, inviare un messaggio di posta <a href= "mailto:Teamscategorypartner@microsoft.com">elettronica Teamscategorypartner@microsoft.com.</a></span><span class="sxs-lookup"><span data-stu-id="79096-221">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>