---
title: Distribuire il servizio vocale cloud di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scarica Playbook per l'abilitazione del sito per pianificare l'implementazione di Teams e accelerare e ottimizzare l'adozione da parte degli utenti, la soddisfazione e la qualità.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae9a1e6abf7dbf97e625be4eb69a0ef95b1910da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532573"
---
# <a name="deploy-my-service"></a><span data-ttu-id="4b02c-103">Implementare il servizio</span><span class="sxs-lookup"><span data-stu-id="4b02c-103">Deploy my service</span></span>

<span data-ttu-id="4b02c-104">Questo articolo offre una panoramica dei requisiti per la corretta distribuzione dei servizi vocali cloud.</span><span class="sxs-lookup"><span data-stu-id="4b02c-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="4b02c-105">Seguendo le indicazioni prescriptive per la distribuzione dei servizi vocali cloud, è possibile assicurarsi di soddisfare tutti i requisiti e fornire risultati ripetibili.</span><span class="sxs-lookup"><span data-stu-id="4b02c-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="4b02c-106">Playbook di abilitazione del sito per i carichi di lavoro vocali di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b02c-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="4b02c-107">Usare questo playbook per aiutare l'organizzazione a pianificare ed eseguire correttamente l'implementazione delle funzionalità vocali di Microsoft Teams su base sito.</span><span class="sxs-lookup"><span data-stu-id="4b02c-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="4b02c-108">Incluse tutte le attività richieste, le sequenze temporali consigliate e i collegamenti alle indicazioni corrispondenti per ogni attività, questo playbook illustra le linee guida end-to-end per assicurare una distribuzione vocale di Teams corretta per un determinato sito, concentrandosi sui fattori importanti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4b02c-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="4b02c-109">Completando le attività in questo playbook, l'organizzazione può:</span><span class="sxs-lookup"><span data-stu-id="4b02c-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="4b02c-110">Pianificare e pianificare in modo efficace l'implementazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4b02c-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="4b02c-111">Accelerare e ottimizzare l'adozione da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4b02c-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="4b02c-112">Ridurre le esigenze di supporto e aumentare la soddisfazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4b02c-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="4b02c-113">Questo articolo e il playbook associato non hanno lo scopo di descrivere ogni passaggio di configurazione tecnica necessario per l'abilitazione del servizio o l'impostazione del tono di chiamata a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="4b02c-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="4b02c-114">Si focalizzano invece sulle attività e sulle attività consigliate agli utenti di onboarding con facilità e devono iniziare a consumare i carichi di lavoro vocali di Teams attraverso una transizione veloce e fluida con un tasso di adozione elevato, riducendo al minimo i requisiti di supporto.</span><span class="sxs-lookup"><span data-stu-id="4b02c-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="4b02c-115">Per indicazioni tecniche su come configurare al meglio l'ambiente per la voce di Teams, vedere gli elenchi di controllo di onboarding per la configurazione dei carichi di lavoro vocali di [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)la configurazione del routing diretto [in Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)le funzionalità principali di [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)la rete per [Teams](prepare-network.md)e l'abilitazione di [Microsoft 365 o Office 365.](onboarding-checklist-enable-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="4b02c-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="4b02c-116">Aree di interesse di Playbook</span><span class="sxs-lookup"><span data-stu-id="4b02c-116">Playbook focus areas</span></span>

<span data-ttu-id="4b02c-117">L'obiettivo del playbook è risolvere i fattori che influenzano la distribuzione vocale di Teams da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4b02c-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="4b02c-118">Le attività e le attività sono raggruppate nelle aree di interesse seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b02c-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="4b02c-119">Convalida della conformità dei servizi</span><span class="sxs-lookup"><span data-stu-id="4b02c-119">Validation of service readiness</span></span>
    - <span data-ttu-id="4b02c-120">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4b02c-120">Audio Conferencing</span></span>
    - <span data-ttu-id="4b02c-121">Piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="4b02c-121">Calling Plans</span></span>
    - <span data-ttu-id="4b02c-122">Routing diretto</span><span class="sxs-lookup"><span data-stu-id="4b02c-122">Direct Routing</span></span>

-   <span data-ttu-id="4b02c-123">Abilitazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="4b02c-123">User enablement</span></span>

-   <span data-ttu-id="4b02c-124">Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b02c-124">Endpoints</span></span>

-   <span data-ttu-id="4b02c-125">Utilizzo e qualità</span><span class="sxs-lookup"><span data-stu-id="4b02c-125">Usage and quality</span></span>

-   <span data-ttu-id="4b02c-126">Adozione</span><span class="sxs-lookup"><span data-stu-id="4b02c-126">Adoption</span></span>

<span data-ttu-id="4b02c-127">Playbook [for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per l'abilitazione del sito è una cartella di lavoro di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4b02c-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="4b02c-128">Ognuna di queste cinque aree di interesse è un foglio distinto nella cartella di lavoro e ogni attività e attività di distribuzione è raggruppata in uno di questi fogli.</span><span class="sxs-lookup"><span data-stu-id="4b02c-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="4b02c-129">![Screenshot del playbook di abilitazione del sito](media/deploy-my-service-image1.png "Screenshot del playbook")</span><span class="sxs-lookup"><span data-stu-id="4b02c-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="4b02c-130">Verrà creata un'istanza distinta del playbook per ogni sito nell'ambito per l'implementazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4b02c-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="4b02c-131">Come usare il playbook</span><span class="sxs-lookup"><span data-stu-id="4b02c-131">How to use the playbook</span></span>

<span data-ttu-id="4b02c-132">Indipendentemente dalle dimensioni e dalla complessità della posizione, l'abilitazione di ogni sito richiede di pianificare le attività e le attività in anticipo, ed eseguirle in ordine ottimale, prima, durante e dopo l'implementazione effettiva del servizio.</span><span class="sxs-lookup"><span data-stu-id="4b02c-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="4b02c-133">È consigliabile seguire questi passaggi durante la pianificazione e l'esecuzione del percorso verso la voce di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4b02c-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="4b02c-134">Scaricare [playbook di abilitazione del sito per la voce (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="4b02c-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="4b02c-135">Creare una copia separata del playbook per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="4b02c-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="4b02c-136">Nella scheda del foglio denominato Playbook per **{SiteName-Code}** sostituire **{SiteName-Code}** con il nome del sito e/o il codice del sito pertinente.</span><span class="sxs-lookup"><span data-stu-id="4b02c-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="4b02c-137">Immettere il **nome del sito, il codice del sito** e la data di lancio **pianificata,** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4b02c-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="4b02c-138">Si tratta di un passaggio fondamentale, perché modifica le scadenze consigliate per ogni attività nel playbook.</span><span class="sxs-lookup"><span data-stu-id="4b02c-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="4b02c-139">![Esempio con il nome del sito, il codice del sito e la data di lancio pianificata](media/deploy-my-service-image2.png "Esempio con il nome del sito di New York, il codice del sito NY01 e la data di lancio pianificata del 20 marzo 18")</span><span class="sxs-lookup"><span data-stu-id="4b02c-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="4b02c-140">Esaminare le attività, eseguire le azioni necessarie e aggiornare lo stato mentre si esamina la sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="4b02c-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="4b02c-141">Lo stato viene rappresentato graficamente, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="4b02c-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="4b02c-142">![Illustrazione di un segno di spunta verde Sì o non applicabile ](media/deploy-my-service-image3.png) **(verde):** l'attività è stata completata o non è applicabile per questo sito e non sono necessarie altre azioni.</span><span class="sxs-lookup"><span data-stu-id="4b02c-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="4b02c-143">![Illustrazione di un punto esclamativo giallo L'attività non è stata ancora completata ](media/deploy-my-service-image4.png) <strong>(gialla): l'attività</strong> non è stata ancora completata e deve essere aggiornata in Sì o No nella relativa pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4b02c-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="4b02c-144">![Illustrazione di una X rossa che indica no ](media/deploy-my-service-image5.png) <strong>(rosso):</strong> l'attività non può essere completata a causa di un problema e deve essere riportata nella riunione sullo stato del progetto.</span><span class="sxs-lookup"><span data-stu-id="4b02c-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="4b02c-145">Lo stato viene visualizzato all'interno di ogni sezione e l'intestazione della sezione è formattata con uno di questi indicatori di stato.</span><span class="sxs-lookup"><span data-stu-id="4b02c-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="4b02c-146">**Anche lo stato** settimanale viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4b02c-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="4b02c-147">![Screenshot dei rieliminazioni settimanali dello stato nel playbook](media/deploy-my-service-image6.png "Screenshot dei rieliminazioni settimanali dello stato nel playbook")</span><span class="sxs-lookup"><span data-stu-id="4b02c-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="4b02c-148">Ripetere i passaggi precedenti per tutte le posizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="4b02c-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b02c-149">Alcuni passaggi potrebbero non essere applicabili a tutti i siti e posizioni.</span><span class="sxs-lookup"><span data-stu-id="4b02c-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="4b02c-150">Se un'attività specifica non è pertinente per un sito, è necessario selezionare **Non applicabile** per questa attività.</span><span class="sxs-lookup"><span data-stu-id="4b02c-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="4b02c-151">**NON ELIMINARE righe** nel playbook; in caso contrario, le formule di rollup dello stato non funzionano.</span><span class="sxs-lookup"><span data-stu-id="4b02c-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="4b02c-152">Prestare attenzione alle attività che potrebbero richiedere più tempo di quanto previsto, ad esempio le attività di portabilità e approvvigionamento del numero.</span><span class="sxs-lookup"><span data-stu-id="4b02c-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="4b02c-153">Queste attività possono influire negativamente sulla sequenza temporale della distribuzione del sito.</span><span class="sxs-lookup"><span data-stu-id="4b02c-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="4b02c-154">Rivedere e aggiornare l'elenco attività e la sequenza temporale [](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) associata ogni settimana e presentarli durante le riunioni del comitato per assicurarsi che gli stakeholder siano a conoscenza dello stato di ogni sito e di eventuali deviazioni dalla pianificazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4b02c-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="4b02c-155">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="4b02c-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="4b02c-156">Decidere se è necessario playbook per l'abilitazione del sito per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4b02c-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="4b02c-157">Decidere chi sarà responsabile della personalizzazione del playbook di abilitazione del sito per Microsoft Teams per ogni sito da distribuire.</span><span class="sxs-lookup"><span data-stu-id="4b02c-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="4b02c-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4b02c-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="4b02c-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Scaricare playbook per l'abilitazione del sito.</a></span><span class="sxs-lookup"><span data-stu-id="4b02c-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="4b02c-160">Personalizzare il playbook di abilitazione del sito per il primo sito.</span><span class="sxs-lookup"><span data-stu-id="4b02c-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="4b02c-161">Ripetere l'operazione in base alle esigenze per altri siti.</span><span class="sxs-lookup"><span data-stu-id="4b02c-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->