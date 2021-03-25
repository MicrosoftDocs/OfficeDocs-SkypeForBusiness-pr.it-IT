---
title: Valutare l'ambiente prima di eseguire l'aggiornamento a Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni sui requisiti per valutare correttamente l'ambiente corrente per l'aggiornamento a Teams.
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
ms.openlocfilehash: 119a80f5a25b4a2d8599df3df6a573a1f5554c1a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119105"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="f56ad-103">Valutare l'ambiente prima di eseguire l'aggiornamento a Teams</span><span class="sxs-lookup"><span data-stu-id="f56ad-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="f56ad-104">![Diagramma del percorso di aggiornamento, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="f56ad-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="f56ad-105">Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase Di conformità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f56ad-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="f56ad-106">Prima di procedere, verificare di aver completato queste attività nelle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="f56ad-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="f56ad-107">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="f56ad-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f56ad-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="f56ad-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="f56ad-109">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="f56ad-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f56ad-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f56ad-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="f56ad-111">Questo articolo fornisce una panoramica dei requisiti per valutare correttamente l'ambiente corrente per il funzionamento di Teams.</span><span class="sxs-lookup"><span data-stu-id="f56ad-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="f56ad-112">Valutando l'ambiente, si identificano i rischi e i requisiti che influiranno sulla distribuzione generale.</span><span class="sxs-lookup"><span data-stu-id="f56ad-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="f56ad-113">Identificando questi elementi in anticipo, è possibile modificare la pianificazione in modo da ottenere il successo.</span><span class="sxs-lookup"><span data-stu-id="f56ad-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="f56ad-114">Introduzione al questionario di individuazione</span><span class="sxs-lookup"><span data-stu-id="f56ad-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="f56ad-115">Per ottenere i risultati chiave obiettivi (OKR), in precedenza sono state prese decisioni chiave relative ai servizi.</span><span class="sxs-lookup"><span data-stu-id="f56ad-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="f56ad-116">Il passaggio successivo consiste nell'eseguire l'individuazione dell'ambiente per valutare tutti gli aspetti relativi all'infrastruttura IT, alla rete e alle operazioni per verificare che l'organizzazione sia pronta per implementare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="f56ad-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="f56ad-117">L'individuazione è uno dei primi passaggi chiave da eseguire durante la pianificazione del viaggio in Teams.</span><span class="sxs-lookup"><span data-stu-id="f56ad-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="f56ad-118">L'individuazione dell'ambiente deve includere una valutazione della conformità della rete per garantire che la rete supporti l'aggiornamento a Teams.</span><span class="sxs-lookup"><span data-stu-id="f56ad-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="f56ad-119">È possibile eseguire un'individuazione dettagliata dell'ambiente per comprenderne meglio lo stato corrente e per rivelare eventuali difficoltà o, ancora più importante, possibili blocchi all'esecuzione dell'implementazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="f56ad-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="f56ad-120">È possibile identificare i rischi tecnici come parte di una valutazione dell'ambiente e della conformità all'adozione e sviluppare un piano di attenuazione per ogni rischio identificato.</span><span class="sxs-lookup"><span data-stu-id="f56ad-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="f56ad-121">È consigliabile incorporare queste informazioni nel registro dei rischi.</span><span class="sxs-lookup"><span data-stu-id="f56ad-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="f56ad-122">Tutte le questioni relative all'infrastruttura di collaborazione esistente e all'organizzazione di Microsoft 365 o Office 365, le reti, gli endpoint, le operazioni e l'adozione e la conformità sono incluse nel questionario sull'individuazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f56ad-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="f56ad-123">Collaborare con il team di progetto per fornire le informazioni richieste con il maggior numero di dettagli possibile per facilitare le attività di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f56ad-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="f56ad-124">[Il questionario](upgrade-plan-journey-discovery-questionnaire.md) è suddiviso nelle sezioni seguenti per confermare la conformità dell'organizzazione alla distribuzione di Teams in diverse aree principali:</span><span class="sxs-lookup"><span data-stu-id="f56ad-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="f56ad-125">Dettagli dell'organizzazione di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="f56ad-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="f56ad-126">Riepilogo della piattaforma di collaborazione esistente</span><span class="sxs-lookup"><span data-stu-id="f56ad-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="f56ad-127">Dettagli sulla distribuzione della piattaforma di collaborazione</span><span class="sxs-lookup"><span data-stu-id="f56ad-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="f56ad-128">Rete e accesso ai servizi di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="f56ad-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="f56ad-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="f56ad-129">Endpoints</span></span>
- <span data-ttu-id="f56ad-130">Operazioni</span><span class="sxs-lookup"><span data-stu-id="f56ad-130">Operations</span></span>
- <span data-ttu-id="f56ad-131">Adozione e conformità</span><span class="sxs-lookup"><span data-stu-id="f56ad-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="f56ad-132">Per iniziare, copiare il questionario in un documento di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="f56ad-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="f56ad-133">Prova a rispondere a tutte le domande e acquisisci tutti i dettagli mentre ti sposti.</span><span class="sxs-lookup"><span data-stu-id="f56ad-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="f56ad-134">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="f56ad-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="f56ad-135">Chi sarà responsabile del completamento di una valutazione dell'ambiente?</span><span class="sxs-lookup"><span data-stu-id="f56ad-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="f56ad-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f56ad-136">Next step</span></span></td><td><ul><li><span data-ttu-id="f56ad-137">Documentare i risultati della valutazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f56ad-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="f56ad-138">Team di progetto</span><span class="sxs-lookup"><span data-stu-id="f56ad-138">Project team</span></span>

<span data-ttu-id="f56ad-139">Assicurarsi di avere coinvolto le persone giuste per il team di progetto.</span><span class="sxs-lookup"><span data-stu-id="f56ad-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="f56ad-140">Verificare i passaggi completati in Integrare [gli stakeholder del progetto.](upgrade-enlist-stakeholders.md)</span><span class="sxs-lookup"><span data-stu-id="f56ad-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="f56ad-141">Dopo aver valutato l'ambiente, procedere con il passaggio successivo: [Preparare il servizio.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="f56ad-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>