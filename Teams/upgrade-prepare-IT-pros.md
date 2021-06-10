---
title: Preparare il personale IT per Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come preparare il personale IT dell'organizzazione per la distribuzione e il supporto Microsoft Teams.
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
ms.openlocfilehash: 3e79eecaaa0fbdbc00b73358f8a9fa2e147675e6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282187"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="7d44e-103">Preparare il personale IT per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d44e-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="7d44e-104">![Diagramma del percorso di aggiornamento, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="7d44e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="7d44e-105">Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase Di conformità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7d44e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="7d44e-106">Prima di procedere, verificare di aver completato queste attività nelle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="7d44e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="7d44e-107">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="7d44e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7d44e-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="7d44e-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="7d44e-109">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="7d44e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="7d44e-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="7d44e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="7d44e-111">Gli amministratori Microsoft 365 o Office 365 dell'organizzazione, i clienti potenziali tecnici e il supporto tecnico sono in base ai requisiti per guidare un'esperienza utente di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="7d44e-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="7d44e-112">Ciò include la garanzia che la rete sia pronta per supportare Teams, la configurazione di Teams per gli utenti e la possibilità di risolvere in modo efficace i problemi che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="7d44e-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="7d44e-113">Condividere le risorse seguenti con i membri del personale IT e verificare che siano pronti a supportare gli utenti prima di iniziare l'aggiornamento a Teams:</span><span class="sxs-lookup"><span data-stu-id="7d44e-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="7d44e-114">Formazione per amministratori per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d44e-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="7d44e-115">Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="7d44e-115">Contact support for business products - Admin Help</span></span>](/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="7d44e-116">Risolvere i problemi di connettività con il client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d44e-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="7d44e-117">Usare i file di log nella risoluzione dei Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d44e-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/><span data-ttu-id="7d44e-119">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="7d44e-119">Decision points</span></span>|<ul><li><span data-ttu-id="7d44e-120">Hai coinvolto tutto il personale di supporto che probabilmente sarà coinvolto nella distribuzione e nel supporto Teams?</span><span class="sxs-lookup"><span data-stu-id="7d44e-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="7d44e-121">È stato sviluppato un piano di formazione per l'onboarding di personale aggiuntivo con l'avanzamento dell'aggiornamento?</span><span class="sxs-lookup"><span data-stu-id="7d44e-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/><span data-ttu-id="7d44e-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7d44e-123">Next steps</span></span>|<ul><li><span data-ttu-id="7d44e-124">Verificare che il personale IT abbia le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="7d44e-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="7d44e-125">Rivisitare i piani di formazione e preparazione non appena vengono rilasciate nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7d44e-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="7d44e-126">Dopo aver preparato il personale IT per la Teams, verificare che l'ambiente soddisfi tutti [i prerequisiti.](upgrade-plan-journey-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="7d44e-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>