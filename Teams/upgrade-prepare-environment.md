---
title: Preparare l'ambiente per l'aggiornamento a Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Convalidare la conformità dell'ambiente e della rete prima di iniziare l'aggiornamento da Skype for Business a Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f75d899f2b14915e265ce8d36c57daeaf0ce72d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119055"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="783de-103">Preparare l'ambiente per l'aggiornamento a Teams</span><span class="sxs-lookup"><span data-stu-id="783de-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="783de-104">![Diagramma del percorso di aggiornamento, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="783de-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="783de-105">Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase Di conformità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="783de-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="783de-106">Prima di procedere, verificare di aver completato queste attività nelle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="783de-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="783de-107">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="783de-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="783de-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="783de-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="783de-109">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="783de-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="783de-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="783de-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="783de-111">Per eseguire correttamente l'aggiornamento di Teams nell'organizzazione, è importante convalidare l'attuale ambiente Skype for Business e la conformità alla rete.</span><span class="sxs-lookup"><span data-stu-id="783de-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="783de-112">La preparazione dell'ambiente corrente consente di garantire un'esperienza utente di alta qualità, oltre a migliorare la qualità dell'esperienza utente in Teams.</span><span class="sxs-lookup"><span data-stu-id="783de-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="783de-113">La pianificazione di singoli passaggi può essere utile per accelerare la distribuzione e assicurarsi di non aver ignorato le azioni importanti.</span><span class="sxs-lookup"><span data-stu-id="783de-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="783de-114">Completare queste attività in parallelo con la preparazione dell'utente:</span><span class="sxs-lookup"><span data-stu-id="783de-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="783de-115">[Preparare il personale IT per](upgrade-prepare-IT-pros.md) assicurarsi di avere tutto il necessario per un percorso di aggiornamento efficace.</span><span class="sxs-lookup"><span data-stu-id="783de-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="783de-116">Verificare che l'ambiente soddisfi tutti [i prerequisiti](upgrade-plan-journey-prerequisites.md)e comprendere le dipendenze tra i servizi e Teams di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="783de-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="783de-117">[Valutare l'ambiente](upgrade-plan-journey-evaluate-environment.md) eseguendo l'individuazione dell'ambiente usando un questionario di esempio per confermare la disponibilità dell'organizzazione a intraprendere un percorso di aggiornamento a Teams.</span><span class="sxs-lookup"><span data-stu-id="783de-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="783de-118">[Preparare la rete con](prepare-network.md) la pianificazione, la preparazione e l'esecuzione dei passaggi di correzione necessari per la rete per supportare i carichi di lavoro di Teams.</span><span class="sxs-lookup"><span data-stu-id="783de-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="783de-119">[Preparare il servizio per](upgrade-prepare-environment-prepare-service.md) l'implementazione usando elenchi di controllo di onboarding per assicurarsi che la configurazione di Teams sia pronta per supportare la migrazione degli utenti da Skype for Business a Teams.</span><span class="sxs-lookup"><span data-stu-id="783de-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>