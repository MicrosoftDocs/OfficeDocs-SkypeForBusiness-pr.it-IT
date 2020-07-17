---
title: Aggiornamento di Microsoft Teams | Valutazione dell'ambiente, domande sull'individuazione
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Usare queste indicazioni per informazioni sui requisiti per valutare correttamente l'ambiente corrente per l'aggiornamento ai team.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158744"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="84878-103">Valutare l'ambiente prima di eseguire l'aggiornamento a teams</span><span class="sxs-lookup"><span data-stu-id="84878-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="84878-104">![Aggiornare il diagramma di viaggio, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="84878-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="84878-105">Questo articolo fa parte della fase di preparazione tecnica del viaggio di aggiornamento, un'attività completata in parallelo con la fase di preparazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="84878-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="84878-106">Prima di procedere, verificare di aver completato queste attività dalle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="84878-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="84878-107">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="84878-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="84878-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="84878-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="84878-109">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="84878-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="84878-110">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="84878-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="84878-111">Questo articolo offre una panoramica dei requisiti per valutare correttamente l'ambiente corrente per i team operativi.</span><span class="sxs-lookup"><span data-stu-id="84878-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="84878-112">La valutazione dell'ambiente consente di identificare i rischi e i requisiti che influenzano la distribuzione complessiva.</span><span class="sxs-lookup"><span data-stu-id="84878-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="84878-113">Identificando preventivamente questi elementi, è possibile modificare la pianificazione per guidare il successo.</span><span class="sxs-lookup"><span data-stu-id="84878-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="84878-114">Introduzione al questionario di individuazione</span><span class="sxs-lookup"><span data-stu-id="84878-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="84878-115">Per ottenere i risultati delle chiavi oggettive (OKRs), in precedenza sono state effettuate le decisioni sui servizi chiave.</span><span class="sxs-lookup"><span data-stu-id="84878-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="84878-116">Il passaggio successivo consiste nell'eseguire l'individuazione ambientale per valutare tutti gli aspetti relativi all'infrastruttura IT, alla rete e alle operazioni per verificare che l'organizzazione sia pronta per l'implementazione della soluzione.</span><span class="sxs-lookup"><span data-stu-id="84878-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="84878-117">L'individuazione è uno dei primi passaggi principali da eseguire durante la pianificazione del viaggio in teams.</span><span class="sxs-lookup"><span data-stu-id="84878-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="84878-118">L'individuazione ambientale deve includere una valutazione della conformità della rete per garantire che la rete possa supportare l'aggiornamento ai team.</span><span class="sxs-lookup"><span data-stu-id="84878-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="84878-119">Si esegue una scoperta dettagliata dell'ambiente per comprendere meglio lo stato corrente e per rivelare eventuali difficoltà o, ancora più importanti, possibili bloccanti per l'esecuzione dell'implementazione del team.</span><span class="sxs-lookup"><span data-stu-id="84878-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="84878-120">Si identificano i rischi tecnici nell'ambito di una valutazione ambientale e di conformità all'adozione e si sviluppa un piano di attenuazione per ogni rischio identificato.</span><span class="sxs-lookup"><span data-stu-id="84878-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="84878-121">Dovresti includere queste informazioni nel registro dei rischi.</span><span class="sxs-lookup"><span data-stu-id="84878-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="84878-122">Tutte le questioni relative all'infrastruttura di collaborazione esistente e all'organizzazione di Microsoft 365 o Office 365, le reti, gli endpoint, le operazioni e l'adozione e la disponibilità sono incluse nell'ambito del questionario sull'individuazione ambientale.</span><span class="sxs-lookup"><span data-stu-id="84878-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="84878-123">Collaborare con il team di progetto per specificare le informazioni richieste con il maggior dettaglio possibile per facilitare le attività di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="84878-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="84878-124">[Il questionario](upgrade-plan-journey-discovery-questionnaire.md) è suddiviso nelle sezioni seguenti per confermare la disponibilità dell'organizzazione per la distribuzione di team in diversi settori principali:</span><span class="sxs-lookup"><span data-stu-id="84878-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="84878-125">Dettagli dell'organizzazione di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="84878-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="84878-126">Riepilogo della piattaforma di collaborazione esistente</span><span class="sxs-lookup"><span data-stu-id="84878-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="84878-127">Dettagli sulla distribuzione della piattaforma di collaborazione</span><span class="sxs-lookup"><span data-stu-id="84878-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="84878-128">Networking e accesso a Microsoft 365 o ai servizi di Office 365</span><span class="sxs-lookup"><span data-stu-id="84878-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="84878-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="84878-129">Endpoints</span></span>
- <span data-ttu-id="84878-130">Operazioni</span><span class="sxs-lookup"><span data-stu-id="84878-130">Operations</span></span>
- <span data-ttu-id="84878-131">Adozione e disponibilità</span><span class="sxs-lookup"><span data-stu-id="84878-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="84878-132">È possibile iniziare copiando il questionario in un documento di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="84878-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="84878-133">Provare a rispondere a tutte le domande e acquisire tutti i dettagli man mano che ci si sposta.</span><span class="sxs-lookup"><span data-stu-id="84878-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="84878-134">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="84878-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="84878-135">Chi sarà responsabile per il completamento di una valutazione ambientale?</span><span class="sxs-lookup"><span data-stu-id="84878-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="84878-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="84878-136">Next step</span></span></td><td><ul><li><span data-ttu-id="84878-137">Documentare i risultati della valutazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="84878-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="84878-138">Team di progetto</span><span class="sxs-lookup"><span data-stu-id="84878-138">Project team</span></span>

<span data-ttu-id="84878-139">Verificare di aver inserito le persone giuste per il team di progetto.</span><span class="sxs-lookup"><span data-stu-id="84878-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="84878-140">Verificare i passaggi completati in [integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md).</span><span class="sxs-lookup"><span data-stu-id="84878-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="84878-141">Dopo aver valutato l'ambiente, procedere con il passaggio successivo: [preparare il servizio](upgrade-prepare-environment-prepare-service.md).</span><span class="sxs-lookup"><span data-stu-id="84878-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
