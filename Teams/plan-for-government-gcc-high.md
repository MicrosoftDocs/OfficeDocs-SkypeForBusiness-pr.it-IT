---
title: Microsoft 365 Government - GCC High deployments
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Indicazioni per i professionisti IT per guidare Office 365 distribuzioni in entità che gestiscono dati soggetti alle normative governative degli Stati Uniti.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e5f8df087ca7ad999a9756467925be68c60e96f
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718057"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="ee066-103">Pianificare distribuzioni Office 365 Government - GCC high</span><span class="sxs-lookup"><span data-stu-id="ee066-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="ee066-104">Queste indicazioni sono per i professionisti IT che guidano le distribuzioni di Office 365 nelle entità del governo federale degli Stati Uniti o in altre entità che gestiscono dati soggetti a normative e requisiti governativi, in cui l'uso di Office 365 Government – GCC High è appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="ee066-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="ee066-105">Se l'organizzazione ha già soddisfatto i requisiti di idoneità Office 365 Government - GCC Alta idoneità e ha applicato e accettato il programma, è possibile saltare i passaggi 1 e 2 e andare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ee066-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="ee066-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ee066-106">Step 1.</span></span> <span data-ttu-id="ee066-107">Determinare se l'organizzazione deve Office 365 Government - GCC alta e soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="ee066-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="ee066-108">L'Office 365 Government - GCC high fornisce la conformità ai requisiti governativi degli Stati Uniti per i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="ee066-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="ee066-109">Oltre a usufruire delle funzionalità e delle funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti specifiche per Office 365 Government - GCC High:</span><span class="sxs-lookup"><span data-stu-id="ee066-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="ee066-110">Il contenuto dei clienti dell'organizzazione è logicamente segregato dai contenuti dei clienti nei servizi Office 365 commerciali da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee066-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="ee066-111">Il contenuto dei clienti dell'organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ee066-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="ee066-112">L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="ee066-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="ee066-113">Office 365 Government: GCC High è conforme alle certificazioni e accreditamenti necessari per i clienti del settore pubblico degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ee066-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="ee066-114">Per altre informazioni sull'offerta Office 365 Government - GCC High per i clienti del governo degli Stati Uniti, vedere i piani [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i requisiti [di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="ee066-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="ee066-115">La [Office 365 del](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) servizio del governo degli Stati Uniti descrive i vantaggi della piattaforma, centrati sui requisiti di conformità degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ee066-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="ee066-116">È consigliabile trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Rilevanti per l'organizzazione **Y/N** e Soddisfa le esigenze dell'organizzazione **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="ee066-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="ee066-117">È quindi possibile rivedere l'elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee066-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ee066-119">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="ee066-119">Decision points</span></span>|<ul><li><span data-ttu-id="ee066-120">Decidere se Office 365 Government - GCC alta è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee066-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="ee066-121">Verificare che l'organizzazione soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="ee066-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="ee066-122">Office 365 Government - GCC High è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ee066-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="ee066-123">I clienti non governativi degli Stati Uniti possono scegliere tra diversi Office 365 Government [piani.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="ee066-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="ee066-124">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ee066-124">Step 2.</span></span> <span data-ttu-id="ee066-125">Applica per Office 365 Government - GCC Alta</span><span class="sxs-lookup"><span data-stu-id="ee066-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="ee066-126">Dopo aver deciso che questo servizio è giusto per l'organizzazione, avviare il processo di [richiesta di questo servizio.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="ee066-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="ee066-127">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ee066-127">Step 3.</span></span> <span data-ttu-id="ee066-128">Informazioni Office 365 Government - GCC di sicurezza predefinite elevate.</span><span class="sxs-lookup"><span data-stu-id="ee066-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="ee066-129">È consigliabile prendere tempo per [](enable-features-office-365.md) esaminare attentamente le impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="ee066-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ee066-131">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="ee066-131">Decision point</span></span>|<ul><li><span data-ttu-id="ee066-132">Decidere se è necessario modificare una delle impostazioni di sicurezza predefinite Office 365 Government - GCC Alta, risolvendo prima di tutto l'impatto di eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="ee066-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="ee066-133">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ee066-133">Step 4.</span></span> <span data-ttu-id="ee066-134">Informazioni sulle Teams attualmente disponibili in Office 365 Government - GCC High</span><span class="sxs-lookup"><span data-stu-id="ee066-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="ee066-135">Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra Teams in Office 365 Government - GCC High e Teams nei piani Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ee066-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="ee066-136">Fare riferimento alla tabella seguente per vedere quali caratteristiche sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="ee066-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="ee066-137">Microsoft Teams servizio</span><span class="sxs-lookup"><span data-stu-id="ee066-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="ee066-138">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="ee066-138">Step 5.</span></span> <span data-ttu-id="ee066-139">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="ee066-139">Plan for governance</span></span>

<span data-ttu-id="ee066-140">Determinare i requisiti per la governance e come soddisfarli.</span><span class="sxs-lookup"><span data-stu-id="ee066-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="ee066-141">Passare a [Pianificare la governance in Teams](plan-teams-governance.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="ee066-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="ee066-142">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="ee066-142">Decision point</span></span> |<ul><li><span data-ttu-id="ee066-143">Determinare e documentare i requisiti di governance seguendo le linee guida in [Pianificare la governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="ee066-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="ee066-144">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="ee066-144">Step 6.</span></span> <span data-ttu-id="ee066-145">Distribuire Teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="ee066-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="ee066-146">Dopo aver eseguito l'onboarded a Office 365 Government - GCC High, seguire il percorso di distribuzione consigliato descritto [in](./deploy-overview.md)Come implementare Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="ee066-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="ee066-147">Assicurarsi di interagire con il team di adozione e gestione delle modifiche e Teams campioni.</span><span class="sxs-lookup"><span data-stu-id="ee066-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="ee066-148">È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboarding del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee066-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
