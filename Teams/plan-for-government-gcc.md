---
title: Microsoft 365 Government-distribuzioni di GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Linee guida per i professionisti IT per guidare le distribuzioni di Microsoft 365 in entità che gestiscono i dati soggetti alla regolamentazione del governo degli Stati Uniti
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
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="c8964-103">Pianificare le distribuzioni di Microsoft 365 Government-GCC</span><span class="sxs-lookup"><span data-stu-id="c8964-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="c8964-104">Questa guida è destinata ai professionisti IT che guidano distribuzioni di Microsoft 365 nelle entità governative degli Stati Uniti, in stato, locale, tribale o territoriale o in altre entità che gestiscono i dati soggetti alle normative governative e ai requisiti, in cui l'uso di Microsoft 365 Government-GCC è appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="c8964-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="c8964-105">Nuovo 26 marzo 2020: non perdere la Guida introduttiva scaricabile [per GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span><span class="sxs-lookup"><span data-stu-id="c8964-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8964-106">Microsoft teams sta vivendo un enorme picco nelle chiamate online e nelle conferenze audio/video a causa della pandemia di coronavirus (COVID-19).</span><span class="sxs-lookup"><span data-stu-id="c8964-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="c8964-107">In risposta all'aumento senza precedenti delle chiamate e per garantirne la continuità e la disponibilità, Microsoft consente a Microsoft teams GCC audio/video server di sfruttare la capacità di elaborazione nei nostri datacenter commerciali, oltre che nei datacenter di stato.</span><span class="sxs-lookup"><span data-stu-id="c8964-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="c8964-108">Questi server audio/video si trovano all'interno dei server Microsoft Azure FedRAMP High Accreditation Boundary negli Stati Uniti e non archiviano il contenuto del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8964-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="c8964-109">Tuttavia, questi server elaborano audio e video per le chiamate e le conferenze e operano sotto il nostro personale commerciale durante questo periodo di interim.</span><span class="sxs-lookup"><span data-stu-id="c8964-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="c8964-110">Il personale qualificato e schermato sta monitorando questi server per un potenziale accesso ai dati dei clienti, rivedendo eventuali log-ons interattivi in questi server.</span><span class="sxs-lookup"><span data-stu-id="c8964-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="c8964-111">Il personale qualificato soddisfa i requisiti di GCC per accedere al contenuto del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8964-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="c8964-112">Per informazioni dettagliate sui requisiti di selezione, vedere la [Descrizione del servizio GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span><span class="sxs-lookup"><span data-stu-id="c8964-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="c8964-113">Grazie per il tuo supporto mentre procediamo per garantire che i nostri servizi rimangano disponibili e affidabili in questi tempi straordinari.</span><span class="sxs-lookup"><span data-stu-id="c8964-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="c8964-114">Se l'organizzazione ha già incontrato i requisiti di ammissibilità per il governo di Microsoft 365 e per i quali è stata accettata l'applicazione, è possibile ignorare i passaggi 1 e 2 e passare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c8964-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="c8964-115">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c8964-115">Step 1.</span></span> <span data-ttu-id="c8964-116">Determinare se l'organizzazione ha bisogno di Microsoft 365 Government-GCC e soddisfa i requisiti di ammissibilità.</span><span class="sxs-lookup"><span data-stu-id="c8964-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="c8964-117">L'ambiente Government-GCC Microsoft 365 offre la conformità con i requisiti del governo degli Stati Uniti per i servizi cloud, tra cui FedRAMP moderati e i requisiti per la giustizia penale e i sistemi di informazione federale delle imposte (CJI e FTI).</span><span class="sxs-lookup"><span data-stu-id="c8964-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="c8964-118">Oltre a sfruttare le caratteristiche e le funzionalità di Microsoft 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti che sono univoche per Microsoft 365 Government-GCC:</span><span class="sxs-lookup"><span data-stu-id="c8964-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="c8964-119">Il contenuto del cliente dell'organizzazione viene separato logicamente dal contenuto dei clienti nei servizi Microsoft 365 commerciali di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8964-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="c8964-120">Il contenuto del cliente dell'organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c8964-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="c8964-121">L'accesso al contenuto del cliente dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="c8964-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="c8964-122">Microsoft 365 Government-GCC è conforme alle certificazioni e alle accreditazioni necessarie per i clienti del settore pubblico.</span><span class="sxs-lookup"><span data-stu-id="c8964-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="c8964-123">Per altre informazioni sull'offerta di Microsoft 365 Government-GCC per i clienti del governo degli Stati Uniti, vedere [piani governativi di microsoft 365](https://products.office.com/government/compare-office-365-government-plans), inclusi i [requisiti di ammissibilità](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="c8964-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="c8964-124">La [Descrizione del servizio governativo degli Stati Uniti Microsoft 365](https://technet.microsoft.com/library/mt774581.aspx) descrive i vantaggi della piattaforma, che sono centrati intorno ai requisiti di conformità delle riunioni negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c8964-124">The [Microsoft 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="c8964-125">Potrebbe essere necessario trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: **rilevanti per la mia organizzazione y/n** e **soddisfano le esigenze dell'organizzazione y/n**.</span><span class="sxs-lookup"><span data-stu-id="c8964-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="c8964-126">È quindi possibile rivedere questo elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8964-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c8964-128">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="c8964-128">Decision points</span></span>|<ul><li><span data-ttu-id="c8964-129">Decidere se Microsoft 365 Government-GCC è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8964-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="c8964-130">Verificare che l'organizzazione soddisfi i requisiti di ammissibilità.</span><span class="sxs-lookup"><span data-stu-id="c8964-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="c8964-131">Microsoft 365 Government-GCC è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c8964-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="c8964-132">I clienti di enti pubblici non-americani possono scegliere tra diversi [piani governativi di Microsoft 365](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="c8964-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="c8964-133">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="c8964-133">Step 2.</span></span> <span data-ttu-id="c8964-134">Richiedi Microsoft 365 Government-GCC</span><span class="sxs-lookup"><span data-stu-id="c8964-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="c8964-135">Dopo aver deciso che il servizio è appropriato per l'organizzazione, avviare il processo di [applicazione di questo servizio](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="c8964-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="c8964-136">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c8964-136">Step 3.</span></span> <span data-ttu-id="c8964-137">Informazioni sulle impostazioni di sicurezza predefinite di Microsoft 365-GCC.</span><span class="sxs-lookup"><span data-stu-id="c8964-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="c8964-138">È consigliabile richiedere tempo per esaminare attentamente le impostazioni di [amministratore e sicurezza](enable-features-office-365.md) prima di modificarle e prendere in considerazione gli impatti sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="c8964-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c8964-140">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="c8964-140">Decision point</span></span>|<ul><li><span data-ttu-id="c8964-141">Decidere se modificare le impostazioni di sicurezza di Microsoft 365 Government-GCC predefinite, risolvendo in primo luogo l'impatto delle eventuali modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="c8964-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="c8964-142">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="c8964-142">Step 4.</span></span> <span data-ttu-id="c8964-143">Informazioni sulle funzionalità attualmente non disponibili o disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c8964-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="c8964-144">Per soddisfare le esigenze dei clienti del cloud governativo, esistono alcune differenze tra i piani di Microsoft 365 Government-GCC e Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c8964-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="c8964-145">Fare riferimento alla tabella seguente per vedere quali funzionalità sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="c8964-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="c8964-146">Descrizione del servizio Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8964-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="c8964-147">Una volta che altri carichi di lavoro saranno completamente disponibili nel cloud GCC, questi saranno resi disponibili in teams quando verrà completato il completamento di tutte le operazioni di integrazione.</span><span class="sxs-lookup"><span data-stu-id="c8964-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c8964-149">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="c8964-149">Decision point</span></span>|<ul><li><span data-ttu-id="c8964-150">Decidere se il set di funzionalità teams soddisfa le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8964-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="c8964-151">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="c8964-151">Step 5.</span></span> <span data-ttu-id="c8964-152">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="c8964-152">Plan for governance</span></span>

<span data-ttu-id="c8964-153">Determinare i requisiti per la governance e il modo in cui è possibile conoscerli.</span><span class="sxs-lookup"><span data-stu-id="c8964-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="c8964-154">Per altre informazioni, vedere [pianificare la governance in teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="c8964-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c8964-156">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="c8964-156">Decision point</span></span>|<ul><li><span data-ttu-id="c8964-157">Determinare e documentare i requisiti di governance seguendo le linee guida in [piano per la governance in teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="c8964-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="c8964-158">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="c8964-158">Step 6.</span></span> <span data-ttu-id="c8964-159">Distribuire teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="c8964-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="c8964-160">Dopo aver eseguito l'accesso a Microsoft 365 Government-GCC, seguire il percorso di distribuzione consigliato descritto in [come implementare Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c8964-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="c8964-161">Assicurati di interagire con il team di gestione di adozioni e cambiamenti.</span><span class="sxs-lookup"><span data-stu-id="c8964-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="c8964-162">È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboard del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8964-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="c8964-163">Passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="c8964-163">Step 7.</span></span> <span data-ttu-id="c8964-164">Distribuire Team per riunioni e voci</span><span class="sxs-lookup"><span data-stu-id="c8964-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="c8964-165">Questo è anche il momento ideale per usare team con il gruppo di stakeholder più ampio per iniziare a pianificare le riunioni e le [funzionalità di cloud Voice](cloud-voice-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="c8964-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

