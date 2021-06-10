---
title: Panoramica dell'implementazione dell'aggiornamento a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determinare il percorso di aggiornamento ottimale Microsoft Teams in base alla distribuzione Skype for Business corrente.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1774b8bebc1330e69a611e64d4f0a8e01f05febb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282373"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="0fd12-103">Panoramica dell'implementazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0fd12-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="0fd12-104">![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="0fd12-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="0fd12-105">Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0fd12-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="0fd12-106">Attività di pianificazione prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0fd12-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fd12-107">Prima di procedere con l'implementazione dell'aggiornamento, [](upgrade-plan-journey.md) verificare di aver letto il contenuto della pianificazione a partire da Pianificare l'aggiornamento per assicurarsi di aver completato tutte le attività di pianificazione prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="0fd12-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="0fd12-108">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="0fd12-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="0fd12-109">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="0fd12-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="0fd12-110">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="0fd12-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="0fd12-111">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0fd12-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="0fd12-112">Pianificazione pilota di un utente</span><span class="sxs-lookup"><span data-stu-id="0fd12-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="0fd12-113">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="0fd12-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="0fd12-114">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0fd12-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="0fd12-115">Scegliere il punto di partenza dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0fd12-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="0fd12-116">La procedura da eseguire per eseguire l'aggiornamento a Teams dipende dalla distribuzione corrente di Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="0fd12-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="0fd12-117">In base all'ambiente corrente, scegliere il punto di partenza:</span><span class="sxs-lookup"><span data-stu-id="0fd12-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="0fd12-118">**Se si esegue l'aggiornamento da Skype for Business Online** a Teams , seguire la procedura descritta in Eseguire l'aggiornamento da [Skype for Business Online](./upgrade-to-teams-execute-skypeforbusinessonline.md)a Teams .</span><span class="sxs-lookup"><span data-stu-id="0fd12-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="0fd12-119">Se si esegue l'aggiornamento da un ambiente locale di **Skype for Business**, è necessario eseguire alcuni passaggi aggiuntivi per configurare la connettività tra gli ambienti locali e online prima di spostare gli utenti in Teams.</span><span class="sxs-lookup"><span data-stu-id="0fd12-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="0fd12-120">Per altre informazioni, vedere [Aggiornare Skype for Business locale](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)a Teams .</span><span class="sxs-lookup"><span data-stu-id="0fd12-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]