---
title: Office 365 Government - Distribuzioni DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Indicazioni per i professionisti IT per guidare le distribuzioni di Office 365 in entità che gestiscono i dati soggetti alle normative DoD del governo degli Stati Uniti.
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
ms.openlocfilehash: 954eb24cd0d6c79ab3fd30e22521660d2afeb08e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909160"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="84028-103">Pianificare le distribuzioni di Office 365 Government - DoD</span><span class="sxs-lookup"><span data-stu-id="84028-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="84028-104">Queste indicazioni sono per i professionisti IT che guidano le distribuzioni di Office 365 nelle entità federali del governo degli Stati Uniti o in altre entità che gestiscono i dati soggetti a normative e requisiti governativi, nei casi in cui l'uso di Office 365 Government - DoD sia appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="84028-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="84028-105">Se l'organizzazione ha già soddisfatto i requisiti di idoneità per Office 365 Government - DoD e l'ha applicata e accettata nel programma, è possibile ignorare i passaggi 1 e 2 e andare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="84028-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="84028-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="84028-106">Step 1.</span></span> <span data-ttu-id="84028-107">Determinare se l'organizzazione ha bisogno di Office 365 Government - DoD e soddisfa i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="84028-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="84028-108">L'ambiente Office 365 Government - DoD fornisce la conformità ai requisiti del governo degli Stati Uniti per i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="84028-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="84028-109">Oltre a usufruire delle caratteristiche e funzionalità di Office 365, le organizzazioni beneficiano delle caratteristiche seguenti che sono specifiche di Office 365 Government - DoD:</span><span class="sxs-lookup"><span data-stu-id="84028-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="84028-110">Il contenuto dei clienti dell'organizzazione è logicamente isolato dal contenuto dei clienti nei servizi commerciali di Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84028-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="84028-111">Il contenuto dei clienti della tua organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="84028-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="84028-112">L'accesso al contenuto dei clienti dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="84028-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="84028-113">Office 365 Government – DoD è conforme alle certificazioni e ai crediti richiesti per i clienti del settore pubblico degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="84028-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="84028-114">Nei piani Office 365 Government sono disponibili altre informazioni sull'offerta di Office 365 Government - DoD per i clienti dei piani [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)inclusi i requisiti [di idoneità.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="84028-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="84028-115">La descrizione del servizio [Office 365 US Government](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descrive i vantaggi della piattaforma, centrati sui requisiti di conformità negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="84028-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="84028-116">È possibile trasferire le tabelle delle informazioni della descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: Pertinente per l'organizzazione **Y/N** e soddisfa le esigenze **dell'organizzazione Y/N.**</span><span class="sxs-lookup"><span data-stu-id="84028-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="84028-117">È quindi possibile rivedere l'elenco con i colleghi per verificare che questo servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84028-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="84028-119">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="84028-119">Decision points</span></span>|<ul><li><span data-ttu-id="84028-120">Decidere se Office 365 Government - DoD è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84028-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="84028-121">Verificare che l'organizzazione soddisfi i requisiti di idoneità.</span><span class="sxs-lookup"><span data-stu-id="84028-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="84028-122">Office 365 Government - DoD è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="84028-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="84028-123">I clienti non statunitensi del governo degli Stati Uniti possono scegliere tra diversi piani [di Office 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="84028-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="84028-124">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="84028-124">Step 2.</span></span> <span data-ttu-id="84028-125">Richiedere Office 365 Government - DoD</span><span class="sxs-lookup"><span data-stu-id="84028-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="84028-126">Dopo aver stabilito che questo servizio è la scelta giusta per la propria organizzazione, avviare il processo di [richiesta per questo servizio.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="84028-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="84028-127">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="84028-127">Step 3.</span></span> <span data-ttu-id="84028-128">Informazioni su Office 365 Government: impostazioni di sicurezza predefinite di DoD.</span><span class="sxs-lookup"><span data-stu-id="84028-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="84028-129">È consigliabile rivedere attentamente le [](enable-features-office-365.md) impostazioni di sicurezza e di amministrazione prima di modificarle e valutare l'impatto sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="84028-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="84028-131">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="84028-131">Decision point</span></span>|<ul><li><span data-ttu-id="84028-132">Decidere se è necessario modificare le impostazioni di sicurezza di Office 365 Government - DoD predefinite, risolvendo prima di tutto l'impatto di eventuali modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="84028-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="84028-133">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="84028-133">Step 4.</span></span> <span data-ttu-id="84028-134">Informazioni sulle funzionalità di Teams attualmente disponibili in Office 365 Government - DoD</span><span class="sxs-lookup"><span data-stu-id="84028-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="84028-135">Per soddisfare i requisiti dei clienti cloud governativi, esistono alcune differenze tra Teams nei piani Office 365 Government - DoD e Teams nei piani Enterprise.</span><span class="sxs-lookup"><span data-stu-id="84028-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="84028-136">Fare riferimento alla tabella seguente per informazioni sulle caratteristiche disponibili.</span><span class="sxs-lookup"><span data-stu-id="84028-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="84028-137">Descrizione del servizio Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84028-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="84028-138">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="84028-138">Step 5.</span></span> <span data-ttu-id="84028-139">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="84028-139">Plan for governance</span></span>

<span data-ttu-id="84028-140">Determinare i requisiti per la governance e come soddisfarli.</span><span class="sxs-lookup"><span data-stu-id="84028-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="84028-141">Per altre [informazioni, vedere Pianificare la governance in Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="84028-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="84028-142">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="84028-142">Decision point</span></span> |<ul><li><span data-ttu-id="84028-143">Determinare e documentare i requisiti di governance, seguendo le linee guida del [Piano per la governance in Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="84028-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="84028-144">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="84028-144">Step 6.</span></span> <span data-ttu-id="84028-145">Distribuire Teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="84028-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="84028-146">Dopo aver eseguito l'onboarded a Office 365 Government - DoD, segui il percorso di distribuzione consigliato descritto in [Come implementare Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="84028-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="84028-147">Assicurarsi di coinvolgere il team di adozione e gestione delle modifiche e gli campioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="84028-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="84028-148">È anche possibile usare [FastTrack](https://www.microsoft.com/fasttrack) o il partner scelto per eseguire l'onboarding del servizio.</span><span class="sxs-lookup"><span data-stu-id="84028-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="84028-149">Il client Mac Teams per ambienti DOD non è ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="84028-149">The Mac Teams client for DOD environments is not yet supported.</span></span>
