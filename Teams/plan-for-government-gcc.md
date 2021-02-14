---
title: Microsoft 365 Government - Distribuzioni GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare le distribuzioni di Microsoft 365 in entità che gestiscono i dati soggetti alle normative del governo degli Stati Uniti
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085610"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="36969-103">Pianificare le distribuzioni di Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="36969-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="36969-104">Queste indicazioni sono per i professionisti IT che guidano le distribuzioni di Microsoft 365 in entità federali, statali, locali, locali o territoriali o di enti governativi o di altre entità che gestiscono i dati soggetti a normative e requisiti governativi, dove l'uso di Microsoft 365 Government - GCC è appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="36969-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="36969-105">Nuovo 26 marzo 2020: non perderti la nostra guida introduttiva scaricabile [per GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)</span><span class="sxs-lookup"><span data-stu-id="36969-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36969-106">Microsoft Teams sta riscontrando un picco incredibile nelle chiamate online e nelle audioconferenze/videoconferenze a causa del pandemico coronavirus (COVID-19).</span><span class="sxs-lookup"><span data-stu-id="36969-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="36969-107">In risposta all'aumento continuo delle chiamate e per garantire continuità e disponibilità, Microsoft consente ai server audio/video GCC di Microsoft Teams di sfruttare la capacità di elaborazione sia nei data center commerciali che nei data center governativi.</span><span class="sxs-lookup"><span data-stu-id="36969-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="36969-108">Questi server audio/video si trovano nei server di confine per l'accredito Microsoft Azure FedRAMP High negli Stati Uniti e non archiviano contenuti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="36969-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="36969-109">Tuttavia, questi server elaborano audio e video per chiamate e conferenze e operano nel personale commerciale durante questo periodo provvisorio.</span><span class="sxs-lookup"><span data-stu-id="36969-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="36969-110">Il personale qualificato e esaminato controlla questi server per ottenere un potenziale accesso ai dati dei clienti esaminando eventuali accessi interattivi a questi server.</span><span class="sxs-lookup"><span data-stu-id="36969-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="36969-111">Il personale qualificato soddisfa i requisiti GCC per l'accesso al contenuto del cliente.</span><span class="sxs-lookup"><span data-stu-id="36969-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="36969-112">Per informazioni dettagliate sui requisiti di selezione, vedere la [descrizione del servizio GCC.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="36969-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="36969-113">Grazie per il supporto durante l'applicazione delle misure necessarie per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.</span><span class="sxs-lookup"><span data-stu-id="36969-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="36969-114">Se l'organizzazione ha già soddisfatto i requisiti di idoneità per Microsoft 365 Government - GCC e l'ha applicata e accettata nel programma, è possibile ignorare i passaggi 1 e 2 e andare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="36969-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="36969-115">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="36969-115">Step 1.</span></span> <span data-ttu-id="36969-116">Determinare se l'organizzazione ha bisogno di Microsoft 365 Government - GCC e soddisfa i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="36969-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="36969-117">L'ambiente Microsoft 365 Government - GCC fornisce la conformità ai requisiti del governo degli Stati Uniti per i servizi cloud, tra cui FedRAMP Moderate e i requisiti per il sistema penale e i sistemi federali di informazioni fiscali (tipi di dati CJI e FTI).</span><span class="sxs-lookup"><span data-stu-id="36969-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="36969-118">Oltre a usufruire delle caratteristiche e funzionalità di Microsoft 365, le organizzazioni beneficiano delle caratteristiche seguenti, specifiche di Microsoft 365 Government - GCC:</span><span class="sxs-lookup"><span data-stu-id="36969-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="36969-119">Il contenuto dei clienti dell'organizzazione è logicamente isolato dal contenuto dei clienti nei servizi commerciali di Microsoft 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36969-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="36969-120">Il contenuto dei clienti della tua organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="36969-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="36969-121">L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="36969-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="36969-122">Microsoft 365 Government - GCC è conforme alle certificazioni e ai crediti richiesti per i clienti del settore pubblico degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="36969-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="36969-123">Nei piani Microsoft 365 Government sono disponibili altre informazioni sull'offerta di Microsoft 365 Government - GCC per i clienti dei piani [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i requisiti [di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="36969-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="36969-124">La descrizione del servizio [Microsoft 365 US Government](https://technet.microsoft.com/library/mt774581.aspx) descrive i vantaggi della piattaforma, che sono centrati rispetto ai requisiti di conformità all'interno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="36969-124">The [Microsoft 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="36969-125">È possibile trasferire le tabelle delle informazioni della descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Pertinente per l'organizzazione **Y/N** e soddisfa le esigenze **dell'organizzazione Y/N.**</span><span class="sxs-lookup"><span data-stu-id="36969-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="36969-126">È quindi possibile rivedere l'elenco con i colleghi per verificare che questo servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36969-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="36969-128">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="36969-128">Decision points</span></span>|<ul><li><span data-ttu-id="36969-129">Decidere se Microsoft 365 Government - GCC è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36969-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="36969-130">Verificare che l'organizzazione soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="36969-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="36969-131">Microsoft 365 Government - GCC è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="36969-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="36969-132">I clienti non statunitensi del governo degli Stati Uniti possono scegliere tra diversi piani [di Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="36969-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="36969-133">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="36969-133">Step 2.</span></span> <span data-ttu-id="36969-134">Richiedere Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="36969-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="36969-135">Dopo aver stabilito che questo servizio è la scelta giusta per la tua organizzazione, avvia qui il processo di richiesta [per questo servizio.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="36969-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="36969-136">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="36969-136">Step 3.</span></span> <span data-ttu-id="36969-137">Informazioni su Microsoft 365 Government : impostazioni di sicurezza predefinite per GCC.</span><span class="sxs-lookup"><span data-stu-id="36969-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="36969-138">È consigliabile rivedere attentamente le [](enable-features-office-365.md) impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="36969-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="36969-140">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="36969-140">Decision point</span></span>|<ul><li><span data-ttu-id="36969-141">Decidere se modificare una delle impostazioni di sicurezza predefinite di Microsoft 365 Government - GCC, risolvendo prima di tutto l'impatto di eventuali modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="36969-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="36969-142">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="36969-142">Step 4.</span></span> <span data-ttu-id="36969-143">Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="36969-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="36969-144">Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra i piani Microsoft 365 Government - GCC ed Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36969-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="36969-145">Fare riferimento alla tabella seguente per informazioni sulle caratteristiche disponibili.</span><span class="sxs-lookup"><span data-stu-id="36969-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="36969-146">Descrizione del servizio Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36969-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="36969-147">Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, diventeranno disponibili in Teams al completamento di tutte le attività di integrazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="36969-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="36969-149">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="36969-149">Decision point</span></span>|<ul><li><span data-ttu-id="36969-150">Decidere se il set di funzionalità di Teams soddisfa le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36969-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="36969-151">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="36969-151">Step 5.</span></span> <span data-ttu-id="36969-152">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="36969-152">Plan for governance</span></span>

<span data-ttu-id="36969-153">Determinare i requisiti per la governance e come soddisfarli.</span><span class="sxs-lookup"><span data-stu-id="36969-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="36969-154">Per altre [informazioni, vedere Pianificare la governance in Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="36969-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="36969-156">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="36969-156">Decision point</span></span>|<ul><li><span data-ttu-id="36969-157">Determinare e documentare i requisiti di governance, seguendo le linee guida del [Piano per la governance in Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="36969-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="36969-158">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="36969-158">Step 6.</span></span> <span data-ttu-id="36969-159">Distribuire Teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="36969-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="36969-160">Dopo aver eseguito l'onboarded a Microsoft 365 Government - GCC, segui il percorso di distribuzione consigliato descritto in [Come implementare Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="36969-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="36969-161">Assicurarsi di coinvolgere il team di adozione e gestione delle modifiche e gli campioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="36969-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="36969-162">È anche possibile usare [FastTrack](https://www.microsoft.com/fasttrack) o il partner scelto per eseguire l'onboarding del servizio.</span><span class="sxs-lookup"><span data-stu-id="36969-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="36969-163">Passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="36969-163">Step 7.</span></span> <span data-ttu-id="36969-164">Distribuire Teams per riunioni e voce</span><span class="sxs-lookup"><span data-stu-id="36969-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="36969-165">È anche il momento giusto per usare Teams con il gruppo degli stakeholder più ampio per iniziare a pianificare l'implementazione di riunioni e [funzionalità vocali nel cloud.](cloud-voice-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="36969-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

