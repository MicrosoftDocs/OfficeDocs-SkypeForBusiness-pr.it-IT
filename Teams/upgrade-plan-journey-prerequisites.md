---
title: Prerequisiti di Microsoft Teams | Aggiornamento delle dipendenze di adozione
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 241c1f2ab0287b6beb2a99386b2f04b1f7cbfb28
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666068"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="55c9c-103">Prerequisiti e dipendenze ambientali per i team</span><span class="sxs-lookup"><span data-stu-id="55c9c-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="55c9c-104">![Aggiornare il diagramma di viaggio, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="55c9c-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="55c9c-105">Questo articolo fa parte della fase di preparazione tecnica del viaggio di aggiornamento, un'attività completata in parallelo con la fase di preparazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="55c9c-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="55c9c-106">Prima di procedere, verificare di aver completato queste attività dalle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="55c9c-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="55c9c-107">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="55c9c-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="55c9c-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="55c9c-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="55c9c-109">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="55c9c-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="55c9c-110">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="55c9c-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="55c9c-111">Teams combina più servizi Microsoft 365 e Office 365 e dipende quindi dall'implementazione e dal funzionamento corretti di questi servizi.</span><span class="sxs-lookup"><span data-stu-id="55c9c-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="55c9c-112">Questi servizi includono, ma non sono limitati a, SharePoint Online, Exchange Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="55c9c-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="55c9c-113">Anche se non tutti i servizi sono obbligatori, ti consigliamo di implementarli tutti.</span><span class="sxs-lookup"><span data-stu-id="55c9c-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="55c9c-114">Se si sceglie di non implementare determinati servizi, verranno influenzati dalla funzionalità che i team possono offrire alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55c9c-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="55c9c-115">Ad esempio, anche se non è necessario implementare SharePoint Online, i team si basano su SharePoint Online per alcune funzionalità, come la condivisione di file in conversazioni di gruppo, quindi non l'implementazione di questo servizio ridurrà le funzionalità offerte dal client.</span><span class="sxs-lookup"><span data-stu-id="55c9c-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="55c9c-116">Vedere gli articoli seguenti per informazioni sui prerequisiti e sul modo in cui i team interagiscono con altre tecnologie:</span><span class="sxs-lookup"><span data-stu-id="55c9c-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="55c9c-117">Se l'organizzazione non ha distribuito i carichi di lavoro di Microsoft 365 o Office 365, vedere [Introduzione](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="55c9c-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="55c9c-118">Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere [domande frequenti sui domini](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="55c9c-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="55c9c-119">Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere [modelli di identità e autenticazione in Microsoft teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="55c9c-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="55c9c-120">Se l'organizzazione non ha<sup>una</sup>t di Exchange Online, vedere [informazioni su come interagire con Exchange e Microsoft teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="55c9c-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="55c9c-121">Se l'organizzazione non ha SharePoint Online, vedere [informazioni sul modo in cui SharePoint Online e OneDrive for business interagiscono con Microsoft teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="55c9c-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="55c9c-122">Informazioni su come [interagire con microsoft 365 Groups e Microsoft teams](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="55c9c-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="55c9c-123">Se l'organizzazione è un Istituto di istruzione e si usa un sistema di informazioni per studenti, [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync) prima di distribuire Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="55c9c-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="55c9c-124">Dopo aver verificato che l'ambiente soddisfi tutti i prerequisiti applicabili, [valutare l'ambiente corrente per i team](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="55c9c-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
