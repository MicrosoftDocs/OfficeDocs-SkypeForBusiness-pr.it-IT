---
title: Panoramica dell'implementazione dell'aggiornamento a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determinare il percorso di aggiornamento ottimale per Microsoft teams in base alla distribuzione corrente di Skype for business.
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
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578359"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="03e44-103">Panoramica dell'implementazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="03e44-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="03e44-104">![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="03e44-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="03e44-105">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="03e44-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="03e44-106">Attività di pianificazione prerequisito</span><span class="sxs-lookup"><span data-stu-id="03e44-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03e44-107">Prima di procedere con l'implementazione dell'aggiornamento, verificare di aver letto il contenuto di pianificazione a partire da [pianificare l'aggiornamento](upgrade-plan-journey.md) per verificare di aver completato tutte le attività di pianificazione dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="03e44-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="03e44-108">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="03e44-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="03e44-109">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="03e44-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="03e44-110">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="03e44-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="03e44-111">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="03e44-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="03e44-112">Pianificato un pilota utente</span><span class="sxs-lookup"><span data-stu-id="03e44-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="03e44-113">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="03e44-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="03e44-114">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="03e44-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="03e44-115">Scegliere il punto di partenza dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="03e44-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="03e44-116">I passaggi necessari per eseguire l'aggiornamento a teams dipendono dalla distribuzione corrente di Skype for business:</span><span class="sxs-lookup"><span data-stu-id="03e44-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="03e44-117">In base all'ambiente corrente, scegliere il punto di partenza:</span><span class="sxs-lookup"><span data-stu-id="03e44-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="03e44-118">**Se si esegue l'aggiornamento da Skype for business online a teams**, seguire i passaggi descritti in [aggiornamento da Skype for business online a teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span><span class="sxs-lookup"><span data-stu-id="03e44-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="03e44-119">**Se si esegue l'aggiornamento da un ambiente locale di Skype for business**, è necessario eseguire alcuni passaggi aggiuntivi per configurare la connettività tra gli ambienti locali e online prima di trasferire gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="03e44-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="03e44-120">Per altre informazioni, Vedi [aggiornare Skype for business locale a teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="03e44-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
