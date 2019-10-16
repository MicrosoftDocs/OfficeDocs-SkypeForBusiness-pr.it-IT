---
title: Preparare la distribuzione del servizio vocale cloud di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare gli elenchi di controllo onboarding per preparare Office 365 per i team e configurare le funzionalità di base di teams, le reti e i workload vocali cloud.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 653b5cf46e0b079af47c282b4110b181e76be915
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517065"
---
# <a name="prepare-my-service"></a><span data-ttu-id="7275c-103">Preparare il servizio</span><span class="sxs-lookup"><span data-stu-id="7275c-103">Prepare my service</span></span>

<span data-ttu-id="7275c-104">Questo articolo offre una panoramica dei requisiti per preparare i servizi cloud Voice per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7275c-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="7275c-105">Preparando in modo corretto, puoi essere sicuro di essere pronto per garantire funzionalità di cloud Voice alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7275c-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="7275c-106">Elenchi di controllo onboarding per i carichi di lavoro vocali di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7275c-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="7275c-107">Gli elenchi di controllo seguenti illustrano la procedura per l'implementazione di servizi di audioconferenza, sistema telefonico con piani di chiamata ("piani di chiamata") e funzionalità di routing diretto del sistema telefonico ("Direct routing") in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="7275c-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="7275c-108">Preparare Office 365 per Teams</span><span class="sxs-lookup"><span data-stu-id="7275c-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="7275c-109">Configurare le funzionalità di base di Teams</span><span class="sxs-lookup"><span data-stu-id="7275c-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="7275c-110">Configurare la rete</span><span class="sxs-lookup"><span data-stu-id="7275c-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="7275c-111">Configurare i carichi di lavoro cloud Voice in teams</span><span class="sxs-lookup"><span data-stu-id="7275c-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="7275c-112">Configurare il routing diretto in teams</span><span class="sxs-lookup"><span data-stu-id="7275c-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="7275c-113">Attività e attività in questi elenchi di controllo sono gli elementi principali "da fare" che si applicano a ogni distribuzione di funzionalità di cloud Voice con teams.</span><span class="sxs-lookup"><span data-stu-id="7275c-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="7275c-114">È possibile personalizzare gli elenchi di controllo per includere le attività e le attività specifiche per il proprio viaggio in teams.</span><span class="sxs-lookup"><span data-stu-id="7275c-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="7275c-115">Questa guida si basa esclusivamente su piani di chiamata, servizi di audioconferenza e routing diretto.</span><span class="sxs-lookup"><span data-stu-id="7275c-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="7275c-116">Per i nuovi team, vedere [Panoramica di Microsoft teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7275c-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="7275c-117">Per indicazioni generali per la pianificazione della distribuzione dei team, iniziare con l' [implementazione di chat, team, canali e app in Microsoft teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="7275c-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="7275c-118">Usare gli elenchi di controllo forniti per tenere traccia dello stato di ogni singola attività e attività e per assicurarsi che non siano stati ignorati i passaggi critici.</span><span class="sxs-lookup"><span data-stu-id="7275c-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="7275c-119">Ogni attività include una descrizione dettagliata delle azioni necessarie e dei riferimenti ad altre informazioni che è possibile usare per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="7275c-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="7275c-120">Anche se ti consigliamo di seguire gli elenchi di controllo in ordine, la sequenza esatta dipenderà dall'ambito della distribuzione e dalla configurazione e dalla complessità dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7275c-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="7275c-121">Sono organizzati per supportare la distribuzione di Team "Greenfield" (uno senza la presenza di Skype for business online precedente) o la migrazione da Skype for business online a teams.</span><span class="sxs-lookup"><span data-stu-id="7275c-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="7275c-122">Se si sta eseguendo la migrazione da Skype for business online, è possibile che siano già state completate alcune di queste attività e che ora possano ignorarle.</span><span class="sxs-lookup"><span data-stu-id="7275c-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="7275c-123">Quando si è a bordo degli utenti in base al sito, è consigliabile usare il [sito di Enablement PlayBook per Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) come guida complementare a questi elenchi di controllo.</span><span class="sxs-lookup"><span data-stu-id="7275c-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="7275c-124">La maggior parte delle impostazioni di configurazione è comune tra teams e Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="7275c-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="7275c-125">Puoi usare l'interfaccia di amministrazione di Microsoft 365 e l'interfaccia di amministrazione di Microsoft teams per configurare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7275c-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="7275c-126">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="7275c-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="7275c-127">Chi avrà il compito di sorvegliare il completamento degli elenchi di controllo onboarding?</span><span class="sxs-lookup"><span data-stu-id="7275c-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="7275c-128">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7275c-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="7275c-129">Scaricare gli elenchi di controllo onboarding.</span><span class="sxs-lookup"><span data-stu-id="7275c-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="7275c-130">È possibile usare le voci di elenco di controllo onboarding in base al piano di distribuzione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7275c-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="7275c-131">Continuare a bordo</span><span class="sxs-lookup"><span data-stu-id="7275c-131">Continue onboarding</span></span>

<span data-ttu-id="7275c-132">Dopo aver completato questi elenchi di controllo, le funzionalità vocali verranno aggiunte correttamente alla distribuzione dei team.</span><span class="sxs-lookup"><span data-stu-id="7275c-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="7275c-133">Come passaggio successivo, usa il [sito Web Enablement PlayBook per Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per aiutarti a bordo degli utenti in ogni sito e per assicurarti di pianificare ed eseguire importanti attività specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="7275c-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="7275c-134">Piano di implementazione sito pronto per sito</span><span class="sxs-lookup"><span data-stu-id="7275c-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="7275c-135">Creare un processo di gestione dei servizi</span><span class="sxs-lookup"><span data-stu-id="7275c-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="7275c-136">Eseguire test e correzione</span><span class="sxs-lookup"><span data-stu-id="7275c-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="7275c-137">Testare i carichi di lavoro Voice cloud in teams</span><span class="sxs-lookup"><span data-stu-id="7275c-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="7275c-138">Dopo aver definito e documentato i piani per il successo e l'implementazione tecnica del team cloud Voice in fase di previdenza e aver effettuato la configurazione desiderata nell'interfaccia di amministrazione, il passaggio successivo consiste nel verificare che l'organizzazione sia le aspettative e i requisiti vengono soddisfatti tramite funzionalità, funzionalità e usabilità.</span><span class="sxs-lookup"><span data-stu-id="7275c-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="7275c-139">È consigliabile eseguire questo passaggio di convalida prima di distribuire una distribuzione pilota o finale nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="7275c-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="7275c-140">È possibile sfruttare il piano di successo aziendale definito durante la fase di previsione per fungere da base per determinare le attività, le aspettative, i casi di prova di funzionalità/funzionalità e l'ambito generale da valutare durante la fase di test.</span><span class="sxs-lookup"><span data-stu-id="7275c-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="7275c-141">Definire l'approccio di testing</span><span class="sxs-lookup"><span data-stu-id="7275c-141">Define your testing approach</span></span>

<span data-ttu-id="7275c-142">Nella sua forma più semplice, l'approccio di testing si basa sulla revisione delle funzionalità delle funzionalità di audioconferenza, piani di chiamata o servizio di routing diretto e sviluppo di un piano di test per verificare che i requisiti di funzionalità vengano soddisfatti per gli utenti nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="7275c-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="7275c-143">Di seguito è riportato un esempio di piano di test per la fase di bordo di un'implementazione di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7275c-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="7275c-144">Funzionalità di conferenza audio da testare</span><span class="sxs-lookup"><span data-stu-id="7275c-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="7275c-145">Riepilogo dei risultati</span><span class="sxs-lookup"><span data-stu-id="7275c-145">Results summary</span></span> | <span data-ttu-id="7275c-146">Note aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7275c-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="7275c-147">Pianificare una riunione ad hoc per i team che contiene informazioni di accesso esterno per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="7275c-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="7275c-148">Superato/non superato</span><span class="sxs-lookup"><span data-stu-id="7275c-148">Pass/Fail</span></span>   | <span data-ttu-id="7275c-149">DA definire</span><span class="sxs-lookup"><span data-stu-id="7275c-149">TBD</span></span> |
| <span data-ttu-id="7275c-150">Usare un telefono per l'audio della riunione componendo una riunione dalla rete PSTN con le informazioni di accesso esterno fornite</span><span class="sxs-lookup"><span data-stu-id="7275c-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="7275c-151">Superato/non superato</span><span class="sxs-lookup"><span data-stu-id="7275c-151">Pass/Fail</span></span> | <span data-ttu-id="7275c-152">DA definire</span><span class="sxs-lookup"><span data-stu-id="7275c-152">TBD</span></span> |
| <span data-ttu-id="7275c-153">Partecipare ad altre persone a una riunione esistente effettuando la chiamata tramite PSTN</span><span class="sxs-lookup"><span data-stu-id="7275c-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="7275c-154">Superato/non superato</span><span class="sxs-lookup"><span data-stu-id="7275c-154">Pass/Fail</span></span> | <span data-ttu-id="7275c-155">DA definire</span><span class="sxs-lookup"><span data-stu-id="7275c-155">TBD</span></span> |



| <span data-ttu-id="7275c-156">Piani di chiamata o funzionalità di routing diretto da testare</span><span class="sxs-lookup"><span data-stu-id="7275c-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="7275c-157">Riepilogo dei risultati</span><span class="sxs-lookup"><span data-stu-id="7275c-157">Results summary</span></span> | <span data-ttu-id="7275c-158">Note aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7275c-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="7275c-159">Effettuare una chiamata PSTN componendo un numero PSTN</span><span class="sxs-lookup"><span data-stu-id="7275c-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="7275c-160">Superato/non superato</span><span class="sxs-lookup"><span data-stu-id="7275c-160">Pass/Fail</span></span>       | <span data-ttu-id="7275c-161">DA definire</span><span class="sxs-lookup"><span data-stu-id="7275c-161">TBD</span></span> |
| <span data-ttu-id="7275c-162">Ricevere una chiamata PSTN componendo il numero PSTN da una linea esterna (mobile, rete fissa)</span><span class="sxs-lookup"><span data-stu-id="7275c-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="7275c-163">Superato/non superato</span><span class="sxs-lookup"><span data-stu-id="7275c-163">Pass/Fail</span></span> | <span data-ttu-id="7275c-164">DA definire</span><span class="sxs-lookup"><span data-stu-id="7275c-164">TBD</span></span>|
| <span data-ttu-id="7275c-165">Trasferire una chiamata PSTN da un utente di team a un altro</span><span class="sxs-lookup"><span data-stu-id="7275c-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="7275c-166">Superato/non superato</span><span class="sxs-lookup"><span data-stu-id="7275c-166">Pass/Fail</span></span> | <span data-ttu-id="7275c-167">DA definire</span><span class="sxs-lookup"><span data-stu-id="7275c-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="7275c-168">Per facilitare la creazione di test case come punto di partenza, vedere l'elenco delle indicazioni per gli utenti disponibili in [riunioni e chiamate di teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="7275c-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="7275c-169">Configurare i carichi di lavoro cloud Voice per i team</span><span class="sxs-lookup"><span data-stu-id="7275c-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="7275c-170">Ora che hai definito l'approccio di testing, il passaggio successivo consiste nel configurare l'ambiente di servizio e gli utenti nell'ambito delle funzionalità vocali del cloud teams.</span><span class="sxs-lookup"><span data-stu-id="7275c-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="7275c-171">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="7275c-171">For additional information, see:</span></span>

- [<span data-ttu-id="7275c-172">Pianificazione tecnica per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="7275c-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="7275c-173">Configurare servizi di audioconferenza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7275c-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="7275c-174">Pianificazione tecnica per il sistema telefonico con piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="7275c-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="7275c-175">Configurare piani per chiamate per Skype for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7275c-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="7275c-176">Pianificare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="7275c-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="7275c-177">Configurare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="7275c-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="7275c-178">Eseguire il piano di test</span><span class="sxs-lookup"><span data-stu-id="7275c-178">Execute the test plan</span></span>

[//]: # (Modifica OK? "Utente" Mi è sembrato un po' ambiguo.)
<span data-ttu-id="7275c-180">Dopo aver configurato l'ambiente utente e il servizio, l'ultimo passaggio del test include l'esecuzione del piano di test con lo stato attivo sulla convalida delle caratteristiche e delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7275c-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="7275c-181">**Servizi di audioconferenza che testano prerequisiti e presupposti per gli utenti e i siti nell'ambito:**</span><span class="sxs-lookup"><span data-stu-id="7275c-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="7275c-182">La definizione dei casi di utilizzo aziendale per il servizio di audioconferenza è stata completata.</span><span class="sxs-lookup"><span data-stu-id="7275c-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="7275c-183">Le licenze necessarie per i servizi di audioconferenza sono disponibili e sono state assegnate.</span><span class="sxs-lookup"><span data-stu-id="7275c-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="7275c-184">L'elenco dei siti dell'organizzazione e i gruppi di utenti sono stati identificati.</span><span class="sxs-lookup"><span data-stu-id="7275c-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="7275c-185">L'elenco dei servizi di audioconferenza dedicati e condivisi in numeri con preferenza lingua sono stati identificati e configurati.</span><span class="sxs-lookup"><span data-stu-id="7275c-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="7275c-186">I crediti per le [comunicazioni](what-are-communications-credits.md) (se necessario) sono stati configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7275c-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="7275c-187">Sono state identificate e configurate le impostazioni del Bridge conferenza di audioconferenza (lunghezza del PIN, notifiche di entrata/uscita, preferenza di notifica di abilitazione).</span><span class="sxs-lookup"><span data-stu-id="7275c-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="7275c-188">Sono stati identificati, configurati e applicati i criteri di conferenza tenant e le impostazioni di dial plan che supportano scenari di accesso esterno per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7275c-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="7275c-189">I requisiti di conformità dei servizi di audioconferenza sono stati identificati e configurati.</span><span class="sxs-lookup"><span data-stu-id="7275c-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="7275c-190">**Piani di chiamata per testare i prerequisiti e i presupposti per gli utenti e i siti nell'ambito:**</span><span class="sxs-lookup"><span data-stu-id="7275c-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="7275c-191">È stata completata la definizione dei casi di utilizzo aziendale per il servizio piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="7275c-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="7275c-192">Le licenze necessarie per i piani di chiamata sono disponibili e sono state assegnate.</span><span class="sxs-lookup"><span data-stu-id="7275c-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="7275c-193">L'elenco dei siti dell'organizzazione e i gruppi di utenti sono stati identificati.</span><span class="sxs-lookup"><span data-stu-id="7275c-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="7275c-194">I numeri di telefono da assegnare agli utenti sono stati acquisiti o trasferiti a Microsoft e sono disponibili nel portale del tenant.</span><span class="sxs-lookup"><span data-stu-id="7275c-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="7275c-195">I crediti per le [comunicazioni](what-are-communications-credits.md) (se necessario) sono stati configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7275c-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="7275c-196">Criteri per gli utenti del tenant e le impostazioni di dial plan che supportano scenari di piani di chiamata sono stati identificati, configurati e applicati.</span><span class="sxs-lookup"><span data-stu-id="7275c-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="7275c-197">I requisiti di conformità dei piani di chiamata sono stati identificati e configurati.</span><span class="sxs-lookup"><span data-stu-id="7275c-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="7275c-198">**Direct routing testing prerequisiti e presupposti per gli utenti e i siti nell'ambito:**</span><span class="sxs-lookup"><span data-stu-id="7275c-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="7275c-199">La definizione dei casi di utilizzo aziendale per il servizio di routing diretto è stata completata.</span><span class="sxs-lookup"><span data-stu-id="7275c-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="7275c-200">Le licenze necessarie per il routing diretto sono disponibili e sono state assegnate.</span><span class="sxs-lookup"><span data-stu-id="7275c-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="7275c-201">L'elenco dei siti dell'organizzazione e i gruppi di utenti sono stati identificati.</span><span class="sxs-lookup"><span data-stu-id="7275c-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="7275c-202">Un [SBC (Session Border Controller) certificato](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) è stato distribuito, configurato e associato al sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="7275c-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="7275c-203">Enterprise Voice è stata abilitata e i numeri di telefono sono stati assegnati.</span><span class="sxs-lookup"><span data-stu-id="7275c-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="7275c-204">I criteri di routing vocale sono stati identificati, configurati e assegnati.</span><span class="sxs-lookup"><span data-stu-id="7275c-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="7275c-205">Microsoft teams è stato impostato come client chiamante preferito per gli utenti nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="7275c-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="7275c-206">I requisiti di conformità del routing diretto sono stati identificati e configurati.</span><span class="sxs-lookup"><span data-stu-id="7275c-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="7275c-207">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="7275c-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="7275c-208">Decidere quali funzionalità di conferenza audio verranno distribuite (decisione del servizio).</span><span class="sxs-lookup"><span data-stu-id="7275c-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="7275c-209">Identificare i requisiti di funzionalità utente per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7275c-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="7275c-210">Identificare i requisiti di configurazione del servizio per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7275c-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="7275c-211">Decidere se distribuire e configurare piani di routing o chiamate dirette.</span><span class="sxs-lookup"><span data-stu-id="7275c-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="7275c-212">Decidere quali funzionalità del sistema telefonico verranno distribuite (decisione del servizio).</span><span class="sxs-lookup"><span data-stu-id="7275c-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="7275c-213">Identificare i requisiti di funzionalità utente per i piani di chiamata o il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="7275c-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="7275c-214">Identificare i requisiti di configurazione del servizio per le chiamate o il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="7275c-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="7275c-215">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7275c-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="7275c-216">Sviluppare e documentare l'approccio del piano di test.</span><span class="sxs-lookup"><span data-stu-id="7275c-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="7275c-217">Preparare l'ambiente di servizio e gli utenti nell'ambito delle funzionalità di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="7275c-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="7275c-218">Preparare l'ambiente e gli utenti del servizio in ambito per la chiamata di piani o funzionalità di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="7275c-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="7275c-219">Eseguire la convalida dei test per le funzionalità di audioconferenza che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="7275c-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="7275c-220">Eseguire la convalida dei test per i piani di chiamata o le caratteristiche di routing diretto che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="7275c-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="7275c-221">Per qualsiasi errore di test, verificare che la configurazione sia corretta, rivedere gli articoli della community e, se necessario, generare un caso di supporto.</span><span class="sxs-lookup"><span data-stu-id="7275c-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="7275c-222">Per altre informazioni dettagliate su come eseguire test per la conferenza audio in teams, vedere la [Guida ai test dettagliati per i servizi di audioconferenza](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="7275c-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="7275c-223">Per altre indicazioni dettagliate su come eseguire test per la chiamata di piani in teams, vedere la [Guida ai test dettagliati per il sistema telefonico](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="7275c-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
