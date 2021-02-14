---
title: Preparare il personale IT per Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come preparare il personale IT dell'organizzazione per la distribuzione e il supporto di Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 680106618d610d0adc3f93658e3a522d63850e24
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578459"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="43b6e-103">Preparare il personale IT per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43b6e-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="43b6e-104">![Diagramma percorso di aggiornamento, enfatizzando la fase Technical Readiness](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con enfasi sulla fase Technical Readiness")</span><span class="sxs-lookup"><span data-stu-id="43b6e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="43b6e-105">Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase di conformità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="43b6e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="43b6e-106">Prima di procedere, verificare di aver completato queste attività dalle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="43b6e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="43b6e-107">Integrare gli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="43b6e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="43b6e-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="43b6e-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="43b6e-109">Coesistenza e interoperabilità comprensibili di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="43b6e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="43b6e-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="43b6e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="43b6e-111">Gli amministratori dell'organizzazione di Microsoft 365 o Office 365, i lead tecnici e il supporto tecnico sono in responsabilità per supportare un'esperienza utente di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="43b6e-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="43b6e-112">Ciò include la garanzia che la rete sia pronta per supportare Teams, la configurazione di Teams per gli utenti e la possibilità di risolvere in modo efficace i problemi che possono verificarsi.</span><span class="sxs-lookup"><span data-stu-id="43b6e-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="43b6e-113">Condividere le risorse seguenti con i membri del personale IT e verificare che siano pronti a supportare gli utenti prima di iniziare l'aggiornamento a Teams:</span><span class="sxs-lookup"><span data-stu-id="43b6e-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="43b6e-114">Formazione per gli amministratori per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43b6e-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="43b6e-115">Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="43b6e-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="43b6e-116">Risolvere i problemi di connettività con il client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43b6e-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="43b6e-117">Usare i file di log per la risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43b6e-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="43b6e-119">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="43b6e-119">Decision points</span></span>|<ul><li><span data-ttu-id="43b6e-120">Hai coinvolto tutto il personale di supporto che probabilmente sarà coinvolto nella distribuzione e nel supporto di Teams?</span><span class="sxs-lookup"><span data-stu-id="43b6e-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="43b6e-121">È stato sviluppato un piano di formazione per l'onboarding di personale aggiuntivo durante l'aggiornamento?</span><span class="sxs-lookup"><span data-stu-id="43b6e-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/><span data-ttu-id="43b6e-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="43b6e-123">Next steps</span></span>|<ul><li><span data-ttu-id="43b6e-124">Verificare che il personale IT abbia le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="43b6e-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="43b6e-125">Rivisita i piani di formazione e preparazione non appena vengono rilasciate nuove caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="43b6e-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="43b6e-126">Dopo aver preparato il personale IT per Teams, verificare che l'ambiente soddisfi tutti [i prerequisiti.](upgrade-plan-journey-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="43b6e-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
