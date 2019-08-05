---
title: Usare Network Planner per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Informazioni su come usare Network Planner per determinare i requisiti di rete per Microsoft teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea6a4a5989df0a780f75220ec314439f7dafcbe
ms.sourcegitcommit: 384e123f3b5cf1600ebd5ddd69bd022f9b8ba0f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "36185071"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="788f4-103">Usare Network Planner per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="788f4-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="788f4-104">Network Planner è un nuovo strumento disponibile nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="788f4-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="788f4-105">È possibile trovarlo accedendo a **Impostazioni** > di**rete**a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="788f4-105">It can be found by going to **Org-wide settings** > **Network planner**.</span></span> <span data-ttu-id="788f4-106">In pochi passaggi, la pianificazione della rete può aiutare a determinare e organizzare i requisiti di rete per la connessione degli utenti di Microsoft teams all'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="788f4-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="788f4-107">Quando fornisci i dettagli della rete e l'uso dei team, Network Planner calcola i requisiti di rete per la distribuzione di team e la voce cloud tra le posizioni fisiche dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="788f4-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Screenshot di Network Planner](media/network-planner.png)

<span data-ttu-id="788f4-109">Network Planner consente di:</span><span class="sxs-lookup"><span data-stu-id="788f4-109">Network Planner allows you to:</span></span>

- <span data-ttu-id="788f4-110">Creare rappresentazioni dell'organizzazione usando i siti e gli utenti tipo consigliati Microsoft (dipendenti di Office, operatori remoti e sistema room di Teams).</span><span class="sxs-lookup"><span data-stu-id="788f4-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="788f4-111">Gli utenti tipo consigliati sono stati sviluppati in base a dati provenienti da scenari di uso ottimale dei team e modelli di utilizzo tipici.</span><span class="sxs-lookup"><span data-stu-id="788f4-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="788f4-112">Puoi tuttavia creare fino a tre utenti personalizzati oltre ai tre utenti tipo consigliati.</span><span class="sxs-lookup"><span data-stu-id="788f4-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="788f4-113">Generare report e calcolare i requisiti di larghezza di banda per l'utilizzo dei team.</span><span class="sxs-lookup"><span data-stu-id="788f4-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="788f4-114">Per usare Network Planner, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore delle comunicazioni di teams.</span><span class="sxs-lookup"><span data-stu-id="788f4-114">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="788f4-115">Creare un utente personalizzato</span><span class="sxs-lookup"><span data-stu-id="788f4-115">Create a custom persona</span></span>

<span data-ttu-id="788f4-116">Seguire questa procedura per creare una persona personalizzata:</span><span class="sxs-lookup"><span data-stu-id="788f4-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="788f4-117">Accedere a Network Planner nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="788f4-117">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="788f4-118">Nella scheda **personas** fare clic su **+ persona personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="788f4-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="788f4-119">Nel riquadro **nuova persona personalizzata** aggiungere un nome e una descrizione per il nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="788f4-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="788f4-120">Selezionare le autorizzazioni che l'utente utilizzerà nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="788f4-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="788f4-121">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="788f4-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="788f4-122">Creare un piano</span><span class="sxs-lookup"><span data-stu-id="788f4-122">Build your plan</span></span>

<span data-ttu-id="788f4-123">Seguire questa procedura per iniziare a creare il piano di rete:</span><span class="sxs-lookup"><span data-stu-id="788f4-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="788f4-124">Accedere a Network Planner nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="788f4-124">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="788f4-125">Nella scheda **piano di rete** fare clic su **Aggiungi piano di rete**.</span><span class="sxs-lookup"><span data-stu-id="788f4-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="788f4-126">Immettere un nome e una descrizione per il piano di rete.</span><span class="sxs-lookup"><span data-stu-id="788f4-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="788f4-127">Il piano di rete verrà visualizzato nell'elenco dei piani disponibili.</span><span class="sxs-lookup"><span data-stu-id="788f4-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="788f4-128">Fare clic sul nome del piano per selezionare il nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="788f4-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="788f4-129">Aggiungere siti per creare una rappresentazione della configurazione di rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="788f4-129">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="788f4-130">A seconda della rete dell'organizzazione, è consigliabile usare i siti per rappresentare un edificio, una posizione di Office o qualcos'altro.</span><span class="sxs-lookup"><span data-stu-id="788f4-130">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="788f4-131">I siti potrebbero essere connessi da una rete WAN per consentire la condivisione di connessioni Internet e/o PSTN.</span><span class="sxs-lookup"><span data-stu-id="788f4-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="788f4-132">Per ottenere risultati ottimali, creare siti con connessioni locali prima di creare siti che si connettono in remoto a Internet o PSTN.</span><span class="sxs-lookup"><span data-stu-id="788f4-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="788f4-133">Per creare un sito:</span><span class="sxs-lookup"><span data-stu-id="788f4-133">To create a site:</span></span>

    1. <span data-ttu-id="788f4-134">Aggiungere un nome e una descrizione per il sito.</span><span class="sxs-lookup"><span data-stu-id="788f4-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="788f4-135">In **impostazioni di rete**aggiungere il numero di utenti di rete in tale sito (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="788f4-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="788f4-136">Aggiungere dettagli di rete: abilitato per WAN, capacità WAN, uscita Internet (**locale** o **remoto**) e uscita PSTN (nessuno, locale o remoto).</span><span class="sxs-lookup"><span data-stu-id="788f4-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="788f4-137">È necessario aggiungere numeri di capacità WAN e Internet per visualizzare suggerimenti specifici sulla larghezza di banda quando si genera un report.</span><span class="sxs-lookup"><span data-stu-id="788f4-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="788f4-138">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="788f4-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="788f4-139">Creare un report</span><span class="sxs-lookup"><span data-stu-id="788f4-139">Create a report</span></span>

<span data-ttu-id="788f4-140">Dopo aver aggiunto tutti i siti, è possibile creare un report, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="788f4-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="788f4-141">Nella scheda **report** fare clic su **Avvia report**.</span><span class="sxs-lookup"><span data-stu-id="788f4-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="788f4-142">Per ogni sito creato, distribuire il numero di utenti in tutte le persone disponibili.</span><span class="sxs-lookup"><span data-stu-id="788f4-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="788f4-143">Se si usano gli utenti di Microsoft recommended, il numero verrà distribuito automaticamente (80% di Office Worker e 20% remote Worker).</span><span class="sxs-lookup"><span data-stu-id="788f4-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="788f4-144">Dopo aver completato la distribuzione, fare clic su **genera report**.</span><span class="sxs-lookup"><span data-stu-id="788f4-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="788f4-145">Il report generato visualizzerà i requisiti di larghezza di banda in diverse visualizzazioni in modo da poter comprendere chiaramente l'output:</span><span class="sxs-lookup"><span data-stu-id="788f4-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="788f4-146">Una tabella con singoli calcoli visualizzerà i requisiti di larghezza di banda per ogni attività consentita.</span><span class="sxs-lookup"><span data-stu-id="788f4-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="788f4-147">In una visualizzazione aggiuntiva verranno visualizzate le esigenze generali della larghezza di banda con le raccomandazioni.</span><span class="sxs-lookup"><span data-stu-id="788f4-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="788f4-148">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="788f4-148">Click **Save**.</span></span> <span data-ttu-id="788f4-149">Il report sarà disponibile nell'elenco report per la visualizzazione successiva.</span><span class="sxs-lookup"><span data-stu-id="788f4-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="788f4-150">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="788f4-150">Example scenario</span></span>

<span data-ttu-id="788f4-151">Per un esempio di come usare la pianificazione della rete per configurare un piano di rete e generare un report usando questi passaggi, scaricare il [Deck di PowerPoint di Planner di rete](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo in inglese).</span><span class="sxs-lookup"><span data-stu-id="788f4-151">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
