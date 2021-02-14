---
title: Usare Pianificazione reti per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: L'amministratore può imparare a usare Network Planner per determinare i requisiti di rete per Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611800"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="7f70a-103">Usare Pianificazione reti per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f70a-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="7f70a-104">Network Planner è un nuovo strumento disponibile nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7f70a-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="7f70a-105">Per trovare questa scheda, vedere **Pianificazione rete**  >  **planner.**</span><span class="sxs-lookup"><span data-stu-id="7f70a-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="7f70a-106">In pochi passaggi, Network Planner consente di determinare e organizzare i requisiti di rete per connettere gli utenti di Microsoft Teams all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f70a-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="7f70a-107">Quando fornisci i dettagli della rete e l'utilizzo di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e della voce sul cloud nelle posizioni fisiche della tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f70a-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Screenshot di Pianificazione rete](media/network-planner.png)

<span data-ttu-id="7f70a-109">Pianificazione rete consente di:</span><span class="sxs-lookup"><span data-stu-id="7f70a-109">Network planner allows you to:</span></span>

- <span data-ttu-id="7f70a-110">Creare rappresentazioni dell'organizzazione usando siti e utenti tipo consigliati da Microsoft (utenti dell'ufficio, lavoratori remoti e teams room system).</span><span class="sxs-lookup"><span data-stu-id="7f70a-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f70a-111">I utenti tipo consigliati sono stati sviluppati sulla base dei dati degli scenari di utilizzo ottimali di Teams e dei modelli di utilizzo tipici.</span><span class="sxs-lookup"><span data-stu-id="7f70a-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="7f70a-112">È tuttavia possibile creare fino a tre utenti tipo personalizzati in aggiunta ai tre tipi di utenti tipo consigliati.</span><span class="sxs-lookup"><span data-stu-id="7f70a-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="7f70a-113">Generare report e calcolare i requisiti di larghezza di banda per l'utilizzo di Teams.</span><span class="sxs-lookup"><span data-stu-id="7f70a-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="7f70a-114">Per usare Pianificazione rete, è necessario essere un amministratore globale, un amministratore dei servizi di Teams o un amministratore delle comunicazioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="7f70a-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="7f70a-115">Creare un utente tipo personalizzato</span><span class="sxs-lookup"><span data-stu-id="7f70a-115">Create a custom persona</span></span>

<span data-ttu-id="7f70a-116">Seguire questa procedura per creare un utente tipo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="7f70a-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="7f70a-117">Passare a Pianificazione reti nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7f70a-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="7f70a-118">Nella scheda **Utenti tipo** fare clic su + Utente **tipo personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="7f70a-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="7f70a-119">Nel riquadro **Nuovo utente tipo** personalizzato aggiungere un nome e una descrizione per il nuovo utente tipo.</span><span class="sxs-lookup"><span data-stu-id="7f70a-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="7f70a-120">Selezionare le autorizzazioni che questo utente tipo userà all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f70a-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="7f70a-121">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7f70a-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="7f70a-122">Creare il piano</span><span class="sxs-lookup"><span data-stu-id="7f70a-122">Build your plan</span></span>

<span data-ttu-id="7f70a-123">Seguire questa procedura per iniziare a creare il piano di rete:</span><span class="sxs-lookup"><span data-stu-id="7f70a-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="7f70a-124">Passare a Pianificazione reti nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7f70a-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="7f70a-125">Nella scheda **Piano di rete** fare clic su Aggiungi un piano di **rete.**</span><span class="sxs-lookup"><span data-stu-id="7f70a-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="7f70a-126">Immettere un nome e una descrizione per il piano di rete.</span><span class="sxs-lookup"><span data-stu-id="7f70a-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="7f70a-127">Il piano di rete verrà visualizzato nell'elenco dei piani disponibili.</span><span class="sxs-lookup"><span data-stu-id="7f70a-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="7f70a-128">Fare clic sul nome del piano per selezionare il nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="7f70a-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="7f70a-129">Aggiungere siti per creare una rappresentazione della configurazione di rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f70a-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="7f70a-130">A seconda della rete dell'organizzazione, è possibile usare i siti per rappresentare un edificio, una sede o altro.</span><span class="sxs-lookup"><span data-stu-id="7f70a-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="7f70a-131">I siti potrebbero essere connessi tramite una WAN per consentire la condivisione di connessioni Internet e/o PSTN.</span><span class="sxs-lookup"><span data-stu-id="7f70a-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="7f70a-132">Per risultati ottimali, creare siti con connessioni locali prima di creare siti che si connettono in remoto a Internet o PSTN.</span><span class="sxs-lookup"><span data-stu-id="7f70a-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="7f70a-133">Per creare un sito:</span><span class="sxs-lookup"><span data-stu-id="7f70a-133">To create a site:</span></span>

    1. <span data-ttu-id="7f70a-134">Aggiungere un nome e una descrizione per il sito.</span><span class="sxs-lookup"><span data-stu-id="7f70a-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="7f70a-135">In **Impostazioni di** rete aggiungere il numero di utenti di rete nel sito (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f70a-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="7f70a-136">Aggiungere dettagli di rete: abilitato per WAN, capacità WAN, uscita Internet **(locale** o **remota)** e uscita PSTN (nessuna, locale o remota).</span><span class="sxs-lookup"><span data-stu-id="7f70a-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="7f70a-137">È necessario aggiungere i numeri wan e la capacità Internet per visualizzare consigli specifici per la larghezza di banda quando si genera un report.</span><span class="sxs-lookup"><span data-stu-id="7f70a-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="7f70a-138">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7f70a-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="7f70a-139">Creare un report</span><span class="sxs-lookup"><span data-stu-id="7f70a-139">Create a report</span></span>

<span data-ttu-id="7f70a-140">Dopo aver aggiunto tutti i siti, è possibile creare un report nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="7f70a-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="7f70a-141">Nella scheda **Report** fare clic su **Avvia un report.**</span><span class="sxs-lookup"><span data-stu-id="7f70a-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="7f70a-142">Per ogni sito creato, distribuire il numero di utenti tra i tipi di utenti tipo disponibili.</span><span class="sxs-lookup"><span data-stu-id="7f70a-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="7f70a-143">Se si usano i gruppi di utenti tipo consigliati da Microsoft, il numero verrà distribuito automaticamente (80% di lavoratori in ufficio e 20% di lavoratori remoti).</span><span class="sxs-lookup"><span data-stu-id="7f70a-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="7f70a-144">Dopo aver completato la distribuzione, fare clic **su Genera report.**</span><span class="sxs-lookup"><span data-stu-id="7f70a-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="7f70a-145">Il report generato mostrerà i requisiti di larghezza di banda in diverse visualizzazioni diverse, in modo da poter comprendere chiaramente l'output:</span><span class="sxs-lookup"><span data-stu-id="7f70a-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="7f70a-146">Una tabella con singoli calcoli visualizza i requisiti di larghezza di banda per ogni attività consentita.</span><span class="sxs-lookup"><span data-stu-id="7f70a-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="7f70a-147">Una visualizzazione aggiuntiva mostra le esigenze di larghezza di banda complessive con consigli.</span><span class="sxs-lookup"><span data-stu-id="7f70a-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="7f70a-148">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7f70a-148">Click **Save**.</span></span> <span data-ttu-id="7f70a-149">Il report sarà disponibile nell'elenco dei report per poter essere visualizzato successivamente.</span><span class="sxs-lookup"><span data-stu-id="7f70a-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="7f70a-150">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="7f70a-150">Example scenario</span></span>

<span data-ttu-id="7f70a-151">Per un esempio su come usare Pianificazione rete per configurare un piano di rete e generare un report con questa procedura, scaricare Network [Planner How-To PowerPoint Deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo in inglese).</span><span class="sxs-lookup"><span data-stu-id="7f70a-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
