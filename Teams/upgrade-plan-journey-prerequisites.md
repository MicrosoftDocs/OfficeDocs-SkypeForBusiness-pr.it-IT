---
title: Prerequisiti e dipendenze ambientali per l'aggiornamento a teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Usare queste indicazioni per informazioni sui prerequisiti e sulle dipendenze ambientali per la distribuzione di team nell'organizzazione
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578279"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="d8a52-103">Prerequisiti e dipendenze ambientali per i team</span><span class="sxs-lookup"><span data-stu-id="d8a52-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="d8a52-104">![Aggiornare il diagramma di viaggio, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="d8a52-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="d8a52-105">Questo articolo fa parte della fase di preparazione tecnica del viaggio di aggiornamento, un'attività completata in parallelo con la fase di preparazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d8a52-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="d8a52-106">Prima di procedere, verificare di aver completato queste attività dalle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="d8a52-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="d8a52-107">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="d8a52-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d8a52-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="d8a52-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d8a52-109">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="d8a52-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d8a52-110">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d8a52-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="d8a52-111">Teams combina più servizi Microsoft 365 e Office 365 e dipende quindi dall'implementazione e dal funzionamento corretti di questi servizi.</span><span class="sxs-lookup"><span data-stu-id="d8a52-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="d8a52-112">Questi servizi includono, ma non sono limitati a, SharePoint Online, Exchange Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="d8a52-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="d8a52-113">Anche se non tutti i servizi sono obbligatori, ti consigliamo di implementarli tutti.</span><span class="sxs-lookup"><span data-stu-id="d8a52-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="d8a52-114">Se si sceglie di non implementare determinati servizi, verranno influenzati dalla funzionalità che i team possono offrire alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d8a52-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="d8a52-115">Ad esempio, anche se non è necessario implementare SharePoint Online, i team si basano su SharePoint Online per alcune funzionalità, come la condivisione di file in conversazioni di gruppo, quindi non l'implementazione di questo servizio ridurrà le funzionalità offerte dal client.</span><span class="sxs-lookup"><span data-stu-id="d8a52-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="d8a52-116">Vedere gli articoli seguenti per informazioni sui prerequisiti e sul modo in cui i team interagiscono con altre tecnologie:</span><span class="sxs-lookup"><span data-stu-id="d8a52-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="d8a52-117">Se l'organizzazione non ha distribuito i carichi di lavoro di Microsoft 365 o Office 365, vedere [Introduzione](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="d8a52-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="d8a52-118">Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere [domande frequenti sui domini](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="d8a52-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="d8a52-119">Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere [modelli di identità e autenticazione in Microsoft teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="d8a52-120">Se l'organizzazione non ha Exchange Online, vedere [informazioni su come interagire con Exchange e Microsoft teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="d8a52-121">Se l'organizzazione non ha SharePoint Online, vedere [informazioni sul modo in cui SharePoint Online e OneDrive for business interagiscono con Microsoft teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="d8a52-122">Per informazioni su come interagire con Microsoft [365 Groups e Microsoft teams](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="d8a52-123">Se l'organizzazione è un Istituto di istruzione e si usa un sistema di informazioni per studenti, vedere [Introduzione a Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) prima della distribuzione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="d8a52-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="d8a52-124">Se l'organizzazione sta prendendo in considerazione le opzioni di chiamata PSTN (Public Switched Telephone Network), vedi sistema di telefonia [vocale e connettività PSTN](cloud-voice-landing-page.md), il [piano di chiamata è giusto per te](calling-plan-landing-page.md)e il [routing diretto del sistema telefonico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="d8a52-125">Per verificare che tutti i requisiti di rete siano stati soddisfatti prima di eseguire il rollforward dei team, vedere [preparare la rete dell'organizzazione per Microsoft teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

<span data-ttu-id="d8a52-126">Dopo aver verificato che l'ambiente soddisfi tutti i prerequisiti applicabili, [valutare l'ambiente corrente per i team](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d8a52-126">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
