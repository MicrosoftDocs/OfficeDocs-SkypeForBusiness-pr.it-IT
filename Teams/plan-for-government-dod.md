---
title: Office 365 Government - Distribuzioni DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare Office 365 distribuzioni in entità che gestiscono dati soggetti alla normativa DoD governativa degli Stati Uniti.
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
ms.openlocfilehash: dd649507c0108e9a3d500f4d30cae46a3181d75d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117854"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="755cc-103">Pianificare le Office 365 Government - Distribuzioni DoD</span><span class="sxs-lookup"><span data-stu-id="755cc-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="755cc-104">Queste indicazioni sono per i professionisti IT che guidano le distribuzioni di Office 365 nelle entità del governo federale degli Stati Uniti o in altre entità che gestiscono dati soggetti a normative e requisiti governativi, in cui l'uso di Office 365 Government – DoD è appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="755cc-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="755cc-105">Se l'organizzazione ha già soddisfatto i requisiti di idoneità di Office 365 Government – DoD e ha applicato e accettato il programma, è possibile saltare i passaggi 1 e 2 e andare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="755cc-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="755cc-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="755cc-106">Step 1.</span></span> <span data-ttu-id="755cc-107">Determinare se l'organizzazione deve Office 365 Government - DoD e soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="755cc-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="755cc-108">L'ambiente Office 365 Government - DoD fornisce la conformità ai requisiti governativi degli Stati Uniti per i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="755cc-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="755cc-109">Oltre a usufruire delle funzionalità e delle funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti specifiche per Office 365 Government - DoD:</span><span class="sxs-lookup"><span data-stu-id="755cc-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="755cc-110">Il contenuto dei clienti dell'organizzazione è logicamente segregato dai contenuti dei clienti nei servizi Office 365 commerciali da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="755cc-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="755cc-111">Il contenuto dei clienti dell'organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="755cc-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="755cc-112">L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="755cc-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="755cc-113">Office 365 Government: DoD è conforme alle certificazioni e accreditamenti necessari per i clienti del settore pubblico degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="755cc-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="755cc-114">Per altre informazioni sull'offerta Office 365 Government - DoD per i [](https://products.office.com/government/compare-office-365-government-plans)clienti del governo degli Stati Uniti, vedere i Office 365 Government, inclusi i requisiti [di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="755cc-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="755cc-115">La [Office 365 del](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) servizio del governo degli Stati Uniti descrive i vantaggi della piattaforma, centrati sui requisiti di conformità degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="755cc-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="755cc-116">È consigliabile trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Rilevanti per l'organizzazione **Y/N** e Soddisfa le esigenze dell'organizzazione **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="755cc-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="755cc-117">È quindi possibile rivedere l'elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="755cc-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="755cc-119">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="755cc-119">Decision points</span></span>|<ul><li><span data-ttu-id="755cc-120">Decidere se Office 365 Government - DoD è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="755cc-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="755cc-121">Verificare che l'organizzazione soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="755cc-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="755cc-122">Office 365 Government - DoD è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="755cc-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="755cc-123">I clienti non governativi degli Stati Uniti possono scegliere tra diversi Office 365 Government [piani.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="755cc-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="755cc-124">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="755cc-124">Step 2.</span></span> <span data-ttu-id="755cc-125">Applica per Office 365 Government - DoD</span><span class="sxs-lookup"><span data-stu-id="755cc-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="755cc-126">Dopo aver deciso che questo servizio è giusto per l'organizzazione, avviare il processo di [richiesta di questo servizio.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="755cc-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="755cc-127">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="755cc-127">Step 3.</span></span> <span data-ttu-id="755cc-128">Informazioni Office 365 Government - Impostazioni di sicurezza predefinite di DoD.</span><span class="sxs-lookup"><span data-stu-id="755cc-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="755cc-129">È consigliabile prendere tempo per [](enable-features-office-365.md) esaminare attentamente le impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="755cc-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="755cc-131">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="755cc-131">Decision point</span></span>|<ul><li><span data-ttu-id="755cc-132">Decidere se è necessario modificare le impostazioni di sicurezza predefinite Office 365 Government - DoD, risolvendo in modo da comprendere prima l'impatto di eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="755cc-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="755cc-133">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="755cc-133">Step 4.</span></span> <span data-ttu-id="755cc-134">Informazioni sulle Teams attualmente disponibili in Office 365 Government - DoD</span><span class="sxs-lookup"><span data-stu-id="755cc-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="755cc-135">Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra Teams in Office 365 Government - DoD e Teams nei piani Enterprise.</span><span class="sxs-lookup"><span data-stu-id="755cc-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="755cc-136">Fare riferimento alla tabella seguente per vedere quali caratteristiche sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="755cc-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="755cc-137">Microsoft Teams servizio</span><span class="sxs-lookup"><span data-stu-id="755cc-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="755cc-138">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="755cc-138">Step 5.</span></span> <span data-ttu-id="755cc-139">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="755cc-139">Plan for governance</span></span>

<span data-ttu-id="755cc-140">Determinare i requisiti per la governance e come soddisfarli.</span><span class="sxs-lookup"><span data-stu-id="755cc-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="755cc-141">Passare a [Pianificare la governance in Teams](plan-teams-governance.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="755cc-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="755cc-142">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="755cc-142">Decision point</span></span> |<ul><li><span data-ttu-id="755cc-143">Determinare e documentare i requisiti di governance seguendo le linee guida in [Pianificare la governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="755cc-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="755cc-144">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="755cc-144">Step 6.</span></span> <span data-ttu-id="755cc-145">Distribuire Teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="755cc-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="755cc-146">Dopo aver eseguito l'onboarded a Office 365 Government - DoD, seguire il percorso di distribuzione consigliato descritto [in](./deploy-overview.md)Come implementare Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="755cc-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="755cc-147">Assicurarsi di interagire con il team di adozione e gestione delle modifiche e Teams campioni.</span><span class="sxs-lookup"><span data-stu-id="755cc-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="755cc-148">È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboarding del servizio.</span><span class="sxs-lookup"><span data-stu-id="755cc-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="755cc-149">Il client Teams Mac per ambienti DOD non è ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="755cc-149">The Mac Teams client for DOD environments is not yet supported.</span></span>