---
title: Distribuire il servizio vocale cloud di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scaricare il sito Web Enablement PlayBook per pianificare l'implementazione dei team e accelerare e ottimizzare l'adozione, la percezione della qualità e la soddisfazione degli utenti.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e77127d6840473cfb6238d9150ac692230181e1
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610048"
---
# <a name="deploy-my-service"></a><span data-ttu-id="40d18-103">Implementare il servizio</span><span class="sxs-lookup"><span data-stu-id="40d18-103">Deploy my service</span></span>

<span data-ttu-id="40d18-104">Questo articolo offre una panoramica dei requisiti per la distribuzione corretta di servizi Voice cloud.</span><span class="sxs-lookup"><span data-stu-id="40d18-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="40d18-105">Seguendo le indicazioni prescrittivi per la distribuzione dei servizi cloud Voice, è possibile verificare che tutti i requisiti vengano convalidati e fornire risultati ripetibili.</span><span class="sxs-lookup"><span data-stu-id="40d18-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="40d18-106">PlayBook per l'abilitazione del sito per i carichi di lavoro vocali di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40d18-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="40d18-107">Usa questo PlayBook per aiutare l'organizzazione a pianificare ed eseguire correttamente l'implementazione delle funzionalità vocali di Microsoft teams in base al sito.</span><span class="sxs-lookup"><span data-stu-id="40d18-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="40d18-108">Includendo tutte le attività richieste, le sequenze temporali consigliate e i collegamenti alle linee guida corrispondenti per ogni attività, questo PlayBook include le indicazioni finali per garantire una distribuzione vocale di teams di successo per un sito specifico, concentrandosi su fattori importanti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="40d18-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="40d18-109">Completando le attività in questo PlayBook, l'organizzazione può:</span><span class="sxs-lookup"><span data-stu-id="40d18-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="40d18-110">Pianificare e pianificare efficacemente l'implementazione del team.</span><span class="sxs-lookup"><span data-stu-id="40d18-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="40d18-111">Accelerare e ottimizzare l'adozione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="40d18-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="40d18-112">Ridurre le esigenze di supporto e aumentare la soddisfazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="40d18-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="40d18-113">Questo articolo e il PlayBook associato non sono progettati per descrivere ogni passaggio di configurazione tecnica necessario per l'abilitazione del servizio o per fornire un tono di chiamata a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="40d18-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="40d18-114">Si occupano invece delle attività e delle attività consigliate per gli utenti a bordo in modo semplice e consentono di iniziare a usare i carichi di lavoro vocali di teams attraverso una transizione veloce e fluida con un tasso di adozione elevato, riducendo al minimo i requisiti di supporto.</span><span class="sxs-lookup"><span data-stu-id="40d18-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="40d18-115">Per informazioni tecniche su come configurare al meglio l'ambiente per i team Voice, vedere gli elenchi di controllo onboarding per la [configurazione dei workload vocali di teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), la [configurazione del routing diretto in team](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), le [funzionalità di base di teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), la creazione [di reti per i team](prepare-network.md)e l'attivazione di [Microsoft 365 o Office 365](onboarding-checklist-enable-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="40d18-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="40d18-116">Aree di interesse di PlayBook</span><span class="sxs-lookup"><span data-stu-id="40d18-116">Playbook focus areas</span></span>

<span data-ttu-id="40d18-117">Lo scopo del PlayBook è quello di affrontare i fattori che influenzano la percezione dell'utente di una distribuzione vocale di teams.</span><span class="sxs-lookup"><span data-stu-id="40d18-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="40d18-118">Le attività e le attività sono raggruppate nelle aree di interesse seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d18-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="40d18-119">Convalida della disponibilità del servizio</span><span class="sxs-lookup"><span data-stu-id="40d18-119">Validation of service readiness</span></span>
    - <span data-ttu-id="40d18-120">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="40d18-120">Audio Conferencing</span></span>
    - <span data-ttu-id="40d18-121">Piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="40d18-121">Calling Plans</span></span>
    - <span data-ttu-id="40d18-122">Routing diretto</span><span class="sxs-lookup"><span data-stu-id="40d18-122">Direct Routing</span></span>

-   <span data-ttu-id="40d18-123">Abilitazione dell'utente</span><span class="sxs-lookup"><span data-stu-id="40d18-123">User enablement</span></span>

-   <span data-ttu-id="40d18-124">Endpoint</span><span class="sxs-lookup"><span data-stu-id="40d18-124">Endpoints</span></span>

-   <span data-ttu-id="40d18-125">Uso e qualità</span><span class="sxs-lookup"><span data-stu-id="40d18-125">Usage and quality</span></span>

-   <span data-ttu-id="40d18-126">Adozione</span><span class="sxs-lookup"><span data-stu-id="40d18-126">Adoption</span></span>

<span data-ttu-id="40d18-127">Il [sito Web Enablement PlayBook for Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) è una cartella di lavoro di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="40d18-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="40d18-128">Ognuna di queste cinque aree di interesse è un foglio separato nella cartella di lavoro e ogni attività di distribuzione è raggruppata su uno di questi fogli.</span><span class="sxs-lookup"><span data-stu-id="40d18-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="40d18-129">![Screenshot del PlayBook per l'abilitazione del sito](media/deploy-my-service-image1.png "Screenshot del PlayBook")</span><span class="sxs-lookup"><span data-stu-id="40d18-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="40d18-130">Creerai un'istanza distinta del PlayBook per ogni sito in ambito per l'implementazione del team.</span><span class="sxs-lookup"><span data-stu-id="40d18-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="40d18-131">Come usare il PlayBook</span><span class="sxs-lookup"><span data-stu-id="40d18-131">How to use the playbook</span></span>

<span data-ttu-id="40d18-132">Indipendentemente dalle dimensioni e dalla complessità della posizione, l'abilitazione di ogni sito richiede la pianificazione di attività e attività abbastanza presto, nonché l'esecuzione in ordine ottimale, prima, durante e dopo l'implementazione effettiva del servizio.</span><span class="sxs-lookup"><span data-stu-id="40d18-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="40d18-133">Ti consigliamo di seguire questa procedura mentre pianifichi ed Esegui il tuo viaggio a Microsoft teams Voice.</span><span class="sxs-lookup"><span data-stu-id="40d18-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="40d18-134">Scaricare il [sito Enablement PlayBook for Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per Microsoft teams Voice.</span><span class="sxs-lookup"><span data-stu-id="40d18-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="40d18-135">Creare una copia separata del PlayBook per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="40d18-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="40d18-136">Nella scheda del foglio denominato **PlayBook per {nomesito-codice}** sostituire **{nomesito-codice}** con il nome del sito e/o il codice del sito attinente.</span><span class="sxs-lookup"><span data-stu-id="40d18-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="40d18-137">Immettere il **nome del sito, il codice del sito**e la **Data di avvio pianificata**, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="40d18-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="40d18-138">Questo è un passaggio cruciale, perché regola le scadenze consigliate per ogni attività nel PlayBook.</span><span class="sxs-lookup"><span data-stu-id="40d18-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="40d18-139">![Esempio con nome sito, codice sito e data di avvio pianificata](media/deploy-my-service-image2.png "Esempio con il nome del sito di New York, il codice del sito NY01 e la data di avvio prevista del 20-mar-18")</span><span class="sxs-lookup"><span data-stu-id="40d18-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="40d18-140">Esaminare ogni attività, eseguire le azioni necessarie e aggiornare lo stato man mano che si cammina nella sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="40d18-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="40d18-141">Lo stato è rappresentato graficamente, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="40d18-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="40d18-142">![Illustrazione di un segno di spunta verde ](media/deploy-my-service-image3.png) **Sì o non applicabile (verde):** l'attività è stata completata oppure non è applicabile per il sito e non è necessaria alcuna ulteriore azione.</span><span class="sxs-lookup"><span data-stu-id="40d18-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="40d18-143">![Illustrazione di un punto esclamativo giallo ](media/deploy-my-service-image4.png) <strong>l'attività non è ancora stata completata (giallo):</strong> l'attività non è ancora stata completata e deve essere aggiornata a Sì o no nella programmazione.</span><span class="sxs-lookup"><span data-stu-id="40d18-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="40d18-144">![Immagine di una X rossa che indica No ](media/deploy-my-service-image5.png) <strong>No (rosso):</strong> l'attività non può essere completata a causa di un problema e deve essere eseguita nella riunione dello stato del progetto.</span><span class="sxs-lookup"><span data-stu-id="40d18-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="40d18-145">Lo stato viene arrotolato all'interno di ogni sezione e l'intestazione di sezione è formattata con uno di questi indicatori di stato.</span><span class="sxs-lookup"><span data-stu-id="40d18-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="40d18-146">Anche **lo stato settimanale** viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40d18-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="40d18-147">![Screenshot dei rilevamenti settimanali di stato nel PlayBook](media/deploy-my-service-image6.png "Screenshot dei rilevamenti settimanali di stato nel PlayBook")</span><span class="sxs-lookup"><span data-stu-id="40d18-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="40d18-148">Ripetere i passaggi descritti sopra per tutte le posizioni presenti.</span><span class="sxs-lookup"><span data-stu-id="40d18-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40d18-149">Alcuni passaggi potrebbero non essere applicabili a tutte le posizioni e i siti.</span><span class="sxs-lookup"><span data-stu-id="40d18-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="40d18-150">Se un'attività specifica non è pertinente per un sito, è necessario selezionare **non applicabile** per questa attività.</span><span class="sxs-lookup"><span data-stu-id="40d18-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="40d18-151">Non **eliminare** righe nel PlayBook; in questo caso, le formule per il rollup dello stato non funzionano.</span><span class="sxs-lookup"><span data-stu-id="40d18-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="40d18-152">Prestare attenzione alle attività che potrebbero richiedere più tempo del previsto, ad esempio la portabilità dei numeri e le attività di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="40d18-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="40d18-153">Queste attività possono influire negativamente sulla sequenza temporale di distribuzione del sito.</span><span class="sxs-lookup"><span data-stu-id="40d18-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="40d18-154">Assicurarsi di rivedere e aggiornare l'elenco attività e la sequenza temporale associata ogni settimana e presentarle alle [riunioni del comitato direttivo](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) per verificare che gli stakeholder siano a conoscenza dello stato di ogni sito e delle eventuali deviazioni dalla pianificazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40d18-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="40d18-155">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="40d18-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="40d18-156">Decidere se il PlayBook per l'attivazione del sito è necessario per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40d18-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="40d18-157">Decidere chi sarà responsabile della personalizzazione del sito Web Enablement PlayBook per Microsoft teams per ogni sito che verrà distribuito.</span><span class="sxs-lookup"><span data-stu-id="40d18-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="40d18-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="40d18-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="40d18-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Scaricare il PlayBook per l'abilitazione del sito</a>.</span><span class="sxs-lookup"><span data-stu-id="40d18-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="40d18-160">Personalizzare il PlayBook per l'abilitazione del sito per il primo sito.</span><span class="sxs-lookup"><span data-stu-id="40d18-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="40d18-161">Ripetere le richieste per altri siti.</span><span class="sxs-lookup"><span data-stu-id="40d18-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->