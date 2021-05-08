---
title: Prerequisiti e dipendenze ambientali per l'aggiornamento a Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Usare queste indicazioni per informazioni sui prerequisiti e sulle dipendenze ambientali per la distribuzione di Teams nell'organizzazione
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282163"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="bc022-103">Prerequisiti e dipendenze ambientali per Teams</span><span class="sxs-lookup"><span data-stu-id="bc022-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="bc022-104">![Diagramma del percorso di aggiornamento, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")</span><span class="sxs-lookup"><span data-stu-id="bc022-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="bc022-105">Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase Di conformità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bc022-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="bc022-106">Prima di procedere, verificare di aver completato queste attività nelle fasi precedenti:</span><span class="sxs-lookup"><span data-stu-id="bc022-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="bc022-107">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="bc022-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="bc022-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="bc022-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="bc022-109">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="bc022-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="bc022-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bc022-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="bc022-111">Teams combina più Microsoft 365 e Office 365 e quindi dipende dall'implementazione e dal funzionamento corretti di questi servizi.</span><span class="sxs-lookup"><span data-stu-id="bc022-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="bc022-112">Questi servizi includono, ma non solo, SharePoint Online, Exchange Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bc022-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="bc022-113">Anche se non tutti i servizi sono necessari, è consigliabile implementarli tutti.</span><span class="sxs-lookup"><span data-stu-id="bc022-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="bc022-114">Se si sceglie di non implementare determinati servizi, questo influirà sulle funzionalità che Teams offrire all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bc022-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="bc022-115">Ad esempio, anche se non è necessario implementare SharePoint Online, Teams si basa su SharePoint Online per determinate funzionalità, ad esempio la condivisione di file nelle conversazioni di gruppo, quindi la non implementazione di questo servizio ridurrà le funzionalità offerte dal client.</span><span class="sxs-lookup"><span data-stu-id="bc022-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="bc022-116">Vedere gli articoli seguenti per informazioni sui prerequisiti e su come Teams con altre tecnologie:</span><span class="sxs-lookup"><span data-stu-id="bc022-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="bc022-117">Se l'organizzazione non ha distribuito Microsoft 365 o Office 365 di lavoro, vedere [Introduzione.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="bc022-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="bc022-118">Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere Domande [frequenti sui domini.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="bc022-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="bc022-119">Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere Modelli di identità e autenticazione [in Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="bc022-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="bc022-120">Se l’organizzazione non ha implementato Exchange Online, vedi [Informazioni su come interagiscono Exchange e Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="bc022-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="bc022-121">Se l’organizzazione non ha implementato SharePoint Online, vedi [Informazioni su come Microsoft SharePoint Online e Microsoft OneDrive for Business interagiscono con Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="bc022-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="bc022-122">Per informazioni su come [Microsoft 365 gruppi e Microsoft Teams interagire.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="bc022-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="bc022-123">Se l'organizzazione è un istituto di istruzione e si usa un sistema di informazioni degli studenti, vedere Benvenuto in [Microsoft School Data Sync](/schooldatasync) prima della distribuzione Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc022-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="bc022-124">Se l'organizzazione sta valutando le opzioni per le chiamate PSTN (Public Switched Telephone Network), vedere Connettività vocale - Sistema telefonico e [PSTN](cloud-voice-landing-page.md) [,](calling-plan-landing-page.md)Quale piano per le chiamate è giusto per te e Sistema telefonico [Routing diretto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bc022-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="bc022-125">Per assicurarsi che tutti i requisiti di rete siano stati soddisfatti prima della distribuzione Teams, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="bc022-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="bc022-126">Se attualmente si usa Skype for Business Online Connector per gestire i servizi, è necessario passare al modulo di PowerShell di Teams e aggiornare gli script di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="bc022-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="bc022-127">Per altre informazioni, vedere Passare [da Skype for Business Online Connector al Teams di PowerShell.](teams-powershell-move-from-sfbo.md)</span><span class="sxs-lookup"><span data-stu-id="bc022-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="bc022-128">Dopo aver verificato che l'ambiente soddisfi tutti i prerequisiti applicabili, valutare l'ambiente [corrente per](upgrade-plan-journey-evaluate-environment.md)Teams .</span><span class="sxs-lookup"><span data-stu-id="bc022-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>