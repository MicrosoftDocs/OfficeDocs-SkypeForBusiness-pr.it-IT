---
title: Microsoft 365 Pubblica amministrazione - GCC distribuzione
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare Microsoft 365 distribuzioni in entità che gestiscono dati soggetti alla normativa governativa degli Stati Uniti
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
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117834"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="d034a-103">Pianificare distribuzioni Microsoft 365 government - GCC</span><span class="sxs-lookup"><span data-stu-id="d034a-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="d034a-104">Queste indicazioni sono per i professionisti IT che stanno guidando le distribuzioni di Microsoft 365 in enti governativi federali, statali, locali, locali, locali o territoriali o altre entità che gestiscono dati soggetti a normative e requisiti governativi, in cui l'uso di Microsoft 365 Government - GCC è appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="d034a-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="d034a-105">Nuovo 26 marzo 2020: Non perderti la guida introduttiva scaricabile per [GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span><span class="sxs-lookup"><span data-stu-id="d034a-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d034a-106">Microsoft Teams sta riscontrando un enorme picco nelle chiamate online e nelle conferenze audio/video a causa della pandemia del coronavirus (COVID-19).</span><span class="sxs-lookup"><span data-stu-id="d034a-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="d034a-107">In risposta all'aumento senza precedenti delle chiamate e per garantire continuità e disponibilità, Microsoft consente ai server audio/video di Microsoft Teams GCC di sfruttare la capacità di elaborazione nei data center commerciali e nei data center governativi.</span><span class="sxs-lookup"><span data-stu-id="d034a-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="d034a-108">Questi server audio/video si trovano all'interno Microsoft Azure fedRAMP High accreditation boundary servers negli Stati Uniti e non archiviano contenuti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="d034a-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="d034a-109">Tuttavia, questi server elaborano audio e video per chiamate e conferenze e operano sotto il nostro personale commerciale durante questo periodo provvisorio.</span><span class="sxs-lookup"><span data-stu-id="d034a-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="d034a-110">Personale qualificato e schermato sta monitorando questi server per un potenziale accesso ai dati dei clienti esaminando eventuali accessi interattivi a questi server.</span><span class="sxs-lookup"><span data-stu-id="d034a-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="d034a-111">Il personale qualificato soddisfa GCC requisiti per l'accesso al contenuto dei clienti.</span><span class="sxs-lookup"><span data-stu-id="d034a-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="d034a-112">Per informazioni dettagliate sui requisiti di screening, vedere la [GCC del servizio.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="d034a-112">For details about screening requirements, see the [GCC service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="d034a-113">Grazie per il supporto dato che microsoft prende le misure necessarie per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.</span><span class="sxs-lookup"><span data-stu-id="d034a-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="d034a-114">Se l'organizzazione ha già soddisfatto i requisiti di idoneità di Microsoft 365 Government - GCC e ha applicato e accettato il programma, è possibile ignorare i passaggi 1 e 2 e andare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d034a-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="d034a-115">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d034a-115">Step 1.</span></span> <span data-ttu-id="d034a-116">Determinare se l'organizzazione deve Microsoft 365 government - GCC e soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="d034a-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="d034a-117">L'ambiente Microsoft 365 Government - GCC fornisce la conformità ai requisiti governativi degli Stati Uniti per i servizi cloud, tra cui FedRAMP Moderate, e i requisiti per la giustizia penale e i sistemi di informazioni fiscali federali (tipi di dati CJI e FTI).</span><span class="sxs-lookup"><span data-stu-id="d034a-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="d034a-118">Oltre a usufruire delle funzionalità e delle funzionalità di Microsoft 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti specifiche di Microsoft 365 Government - GCC:</span><span class="sxs-lookup"><span data-stu-id="d034a-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="d034a-119">Il contenuto dei clienti dell'organizzazione è logicamente segregato dai contenuti dei clienti nei servizi Microsoft 365 commerciali da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d034a-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="d034a-120">Il contenuto dei clienti dell'organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d034a-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="d034a-121">L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="d034a-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="d034a-122">Microsoft 365 Enti pubblici: GCC con certificazioni e accreditamenti necessari per i clienti del settore pubblico degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d034a-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="d034a-123">Per altre informazioni sull'offerta Microsoft 365 Government - GCC per i clienti del governo degli Stati Uniti, vedere i piani [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i requisiti di [idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="d034a-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="d034a-124">La [Microsoft 365 del](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) servizio del governo degli Stati Uniti descrive i vantaggi della piattaforma, che sono centrati sulla conformità dei requisiti all'interno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d034a-124">The [Microsoft 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="d034a-125">È consigliabile trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Rilevanti per l'organizzazione **Y/N** e Soddisfa le esigenze dell'organizzazione **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="d034a-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="d034a-126">È quindi possibile rivedere l'elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d034a-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d034a-128">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="d034a-128">Decision points</span></span>|<ul><li><span data-ttu-id="d034a-129">Decidere se Microsoft 365 government - GCC è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d034a-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="d034a-130">Verificare che l'organizzazione soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="d034a-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="d034a-131">Microsoft 365 Government - GCC è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d034a-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="d034a-132">I clienti non governativi degli Stati Uniti possono scegliere tra una serie di Microsoft 365 [per enti pubblici.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="d034a-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="d034a-133">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d034a-133">Step 2.</span></span> <span data-ttu-id="d034a-134">Candidarsi Microsoft 365 governo - GCC</span><span class="sxs-lookup"><span data-stu-id="d034a-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="d034a-135">Dopo aver deciso che questo servizio è giusto per l'organizzazione, avviare il processo di richiesta di questo [servizio qui](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="d034a-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="d034a-136">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d034a-136">Step 3.</span></span> <span data-ttu-id="d034a-137">Informazioni Microsoft 365 government- GCC di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="d034a-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="d034a-138">È consigliabile prendere tempo per [](enable-features-office-365.md) esaminare attentamente le impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="d034a-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d034a-140">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="d034a-140">Decision point</span></span>|<ul><li><span data-ttu-id="d034a-141">Decidere se si modificherà una delle impostazioni di sicurezza Microsoft 365 Government - GCC, risolvendo prima di tutto l'impatto di eventuali modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="d034a-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="d034a-142">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="d034a-142">Step 4.</span></span> <span data-ttu-id="d034a-143">Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d034a-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="d034a-144">Per soddisfare i requisiti dei clienti cloud per enti pubblici, esistono alcune differenze tra i piani Microsoft 365 government- GCC e Enterprise government.</span><span class="sxs-lookup"><span data-stu-id="d034a-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="d034a-145">Fare riferimento alla tabella seguente per vedere quali caratteristiche sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="d034a-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="d034a-146">Microsoft Teams servizio</span><span class="sxs-lookup"><span data-stu-id="d034a-146">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="d034a-147">Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, saranno disponibili in Teams al termine di tutte le altre attività di integrazione.</span><span class="sxs-lookup"><span data-stu-id="d034a-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d034a-149">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="d034a-149">Decision point</span></span>|<ul><li><span data-ttu-id="d034a-150">Decidere se il set Teams caratteristiche soddisfa le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d034a-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="d034a-151">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="d034a-151">Step 5.</span></span> <span data-ttu-id="d034a-152">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="d034a-152">Plan for governance</span></span>

<span data-ttu-id="d034a-153">Determinare i requisiti per la governance e come soddisfarli.</span><span class="sxs-lookup"><span data-stu-id="d034a-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="d034a-154">Passare a [Pianificare la governance in Teams](plan-teams-governance.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d034a-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d034a-156">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="d034a-156">Decision point</span></span>|<ul><li><span data-ttu-id="d034a-157">Determinare e documentare i requisiti di governance seguendo le linee guida in [Pianificare la governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="d034a-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="d034a-158">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="d034a-158">Step 6.</span></span> <span data-ttu-id="d034a-159">Distribuire Teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="d034a-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="d034a-160">Dopo aver eseguito l'onboarded a Microsoft 365 Government - GCC, seguire il percorso di distribuzione consigliato descritto [in](./deploy-overview.md)Come implementare Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="d034a-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="d034a-161">Assicurarsi di interagire con il team di adozione e gestione delle modifiche e Teams campioni.</span><span class="sxs-lookup"><span data-stu-id="d034a-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="d034a-162">È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboarding del servizio.</span><span class="sxs-lookup"><span data-stu-id="d034a-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="d034a-163">Passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="d034a-163">Step 7.</span></span> <span data-ttu-id="d034a-164">Distribuire Teams per le riunioni e la voce</span><span class="sxs-lookup"><span data-stu-id="d034a-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="d034a-165">Questo è anche il momento ideale per usare Teams con il gruppo di stakeholder più ampio per iniziare a pianificare la distribuzione di riunioni e [funzionalità vocali cloud.](./cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="d034a-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](./cloud-voice-landing-page.md).</span></span>