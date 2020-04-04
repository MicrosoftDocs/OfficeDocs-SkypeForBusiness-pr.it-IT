---
title: Distribuzioni governative Microsoft 365-DoD
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Linee guida per i professionisti IT per guidare le distribuzioni di Office 365 in entità che gestiscono i dati soggetti al regolamento della difesa del governo degli Stati Uniti.
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
ms.openlocfilehash: 33c3afcde009a6a8cedb1226dbc6383e29e76730
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137796"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a><span data-ttu-id="d3740-103">Pianificare le distribuzioni di Microsoft 365 Government-DoD</span><span class="sxs-lookup"><span data-stu-id="d3740-103">Plan for Microsoft 365 Government - DoD deployments</span></span>

<span data-ttu-id="d3740-104">Questa guida è destinata ai professionisti IT che guidano le distribuzioni di Office 365 nelle entità governative degli Stati Uniti o in altre entità che gestiscono i dati soggetti alle normative governative e ai requisiti, in cui l'uso di Microsoft 365 Government-DoD è appropriato per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="d3740-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="d3740-105">Se l'organizzazione ha già incontrato il governo Microsoft 365-requisiti per l'ammissibilità alla difesa e richiesto e accettato nel programma, è possibile ignorare i passaggi 1 e 2 e passare direttamente al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d3740-105">If your organization has already met the Microsoft 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="d3740-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d3740-106">Step 1.</span></span> <span data-ttu-id="d3740-107">Determinare se l'organizzazione ha bisogno di Microsoft 365 Government-DoD e soddisfa i requisiti di ammissibilità.</span><span class="sxs-lookup"><span data-stu-id="d3740-107">Determine whether your organization needs Microsoft 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="d3740-108">L'ambiente Microsoft 365 Government-DoD offre la conformità con i requisiti del governo degli Stati Uniti per i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="d3740-108">The Microsoft 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="d3740-109">Oltre a sfruttare le caratteristiche e le funzionalità di Office 365, le organizzazioni traggono vantaggio dalle caratteristiche seguenti che sono univoche per Microsoft 365 Government-DoD:</span><span class="sxs-lookup"><span data-stu-id="d3740-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – DoD:</span></span>

- <span data-ttu-id="d3740-110">Il contenuto del cliente dell'organizzazione viene separato logicamente dal contenuto dei clienti nei servizi commerciali di Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3740-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="d3740-111">Il contenuto del cliente dell'organizzazione è archiviato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d3740-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="d3740-112">L'accesso al contenuto del cliente dell'organizzazione è limitato al personale Microsoft schermato.</span><span class="sxs-lookup"><span data-stu-id="d3740-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="d3740-113">Microsoft 365 Government-DoD è conforme alle certificazioni e alle accreditazioni necessarie per i clienti del settore pubblico.</span><span class="sxs-lookup"><span data-stu-id="d3740-113">Microsoft 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="d3740-114">Per altre informazioni su Microsoft 365 Government-DoD offering for US Government Customers in [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), inclusi i [requisiti di ammissibilità](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="d3740-114">You can find more information about the Microsoft 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="d3740-115">La [Descrizione del servizio governativo degli Stati Uniti di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descrive i vantaggi della piattaforma, che sono centrati sui requisiti di conformità delle riunioni negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d3740-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="d3740-116">Potrebbe essere necessario trasferire le tabelle di informazioni nella descrizione del servizio in una cartella di lavoro di Excel e aggiungere due colonne: **rilevanti per la mia organizzazione y/n** e **soddisfano le esigenze dell'organizzazione y/n**.</span><span class="sxs-lookup"><span data-stu-id="d3740-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="d3740-117">È quindi possibile rivedere questo elenco con i colleghi per verificare che il servizio soddisfi le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d3740-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d3740-119">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="d3740-119">Decision points</span></span>|<ul><li><span data-ttu-id="d3740-120">Decidere se Microsoft 365 Government-DoD è appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d3740-120">Decide whether Microsoft 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="d3740-121">Verificare che l'organizzazione soddisfi i requisiti di ammissibilità.</span><span class="sxs-lookup"><span data-stu-id="d3740-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="d3740-122">Microsoft 365 Government-DoD è disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d3740-122">Microsoft 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="d3740-123">I clienti di enti pubblici non-americani possono scegliere tra diversi [piani governativi di Office 365](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="d3740-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---dod"></a><span data-ttu-id="d3740-124">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d3740-124">Step 2.</span></span> <span data-ttu-id="d3740-125">Richiedi Microsoft 365 Government-DoD</span><span class="sxs-lookup"><span data-stu-id="d3740-125">Apply for Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="d3740-126">Dopo aver deciso che il servizio è appropriato per l'organizzazione, avviare il processo di [applicazione per questo servizio](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="d3740-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a><span data-ttu-id="d3740-127">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d3740-127">Step 3.</span></span> <span data-ttu-id="d3740-128">Informazioni sulle impostazioni di sicurezza predefinite di Microsoft 365 Government-DoD.</span><span class="sxs-lookup"><span data-stu-id="d3740-128">Understand Microsoft 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="d3740-129">È consigliabile richiedere tempo per esaminare attentamente le impostazioni di [amministratore e sicurezza](enable-features-office-365.md) prima di modificarle e prendere in considerazione gli impatti sulla conformità prima di apportare modifiche alle impostazioni di sicurezza predefinite.</span><span class="sxs-lookup"><span data-stu-id="d3740-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d3740-131">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="d3740-131">Decision point</span></span>|<ul><li><span data-ttu-id="d3740-132">Decidere se è necessario modificare le impostazioni di sicurezza governative di Microsoft 365 predefinite, risolvendo in primo luogo l'impatto delle eventuali modifiche che potrebbero apportare.</span><span class="sxs-lookup"><span data-stu-id="d3740-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a><span data-ttu-id="d3740-133">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="d3740-133">Step 4.</span></span> <span data-ttu-id="d3740-134">Informazioni sulle funzionalità dei team attualmente disponibili in Microsoft 365 Government-DoD</span><span class="sxs-lookup"><span data-stu-id="d3740-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="d3740-135">Per soddisfare le esigenze dei clienti del cloud governativo, esistono alcune differenze tra teams in Microsoft 365 Government-DoD e teams in piani aziendali.</span><span class="sxs-lookup"><span data-stu-id="d3740-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="d3740-136">Fare riferimento alla tabella seguente per vedere quali funzionalità sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="d3740-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="d3740-137">Descrizione del servizio Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3740-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="d3740-138">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="d3740-138">Step 5.</span></span> <span data-ttu-id="d3740-139">Pianificare la governance</span><span class="sxs-lookup"><span data-stu-id="d3740-139">Plan for governance</span></span>

<span data-ttu-id="d3740-140">Determinare i requisiti per la governance e il modo in cui è possibile conoscerli.</span><span class="sxs-lookup"><span data-stu-id="d3740-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="d3740-141">Per altre informazioni, vedere [pianificare la governance in teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="d3740-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="d3740-142">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="d3740-142">Decision point</span></span> |<ul><li><span data-ttu-id="d3740-143">Determinare e documentare i requisiti di governance seguendo le linee guida in [piano per la governance in teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="d3740-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="d3740-144">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="d3740-144">Step 6.</span></span> <span data-ttu-id="d3740-145">Distribuire teams per la collaborazione</span><span class="sxs-lookup"><span data-stu-id="d3740-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="d3740-146">Dopo aver eseguito l'accesso a Microsoft 365 Government-DoD, seguire il percorso di distribuzione consigliato descritto in [come implementare Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d3740-146">After you've been onboarded to Microsoft 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="d3740-147">Assicurati di interagire con il team di gestione di adozioni e cambiamenti.</span><span class="sxs-lookup"><span data-stu-id="d3740-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="d3740-148">È anche possibile collaborare con [FastTrack](https://www.microsoft.com/fasttrack) o con il partner scelto per l'onboard del servizio.</span><span class="sxs-lookup"><span data-stu-id="d3740-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
