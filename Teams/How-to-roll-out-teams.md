---
title: Come implementare Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dstrome
audience: admin
description: Sia che l'implementazione venga effettuata in un'unica soluzione o avviata per fasi, è importante tracciare un percorso per implementare correttamente Microsoft Teams nell'organizzazione.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.rolloutteams
- seo-marvel-mar2020
- seo-marvel-may2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d55f9d0ce9d3a7668abb6c02435acaa83a06324
ms.sourcegitcommit: 4dd8a326a7284872f0d14e0a61bd4fcbe2297c10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071757"
---
# <a name="how-to-roll-out-microsoft-teams"></a><span data-ttu-id="28bef-103">Come implementare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28bef-103">How to roll out Microsoft Teams</span></span>

## <a name="start-here"></a><span data-ttu-id="28bef-104">Iniziare da qui</span><span class="sxs-lookup"><span data-stu-id="28bef-104">Start here</span></span>
<span data-ttu-id="28bef-p101">Sia per le piccole imprese sia per le società multinazionali, il primo passo per l'implementazione di Teams è andare alla pagina [Introduzione](get-started-with-teams-quick-start.md). Questa è una linea guida per eseguire l'implementazione di Teams su scala ridotta, che potrebbe essere tutto ciò che serve per le piccole imprese, o se si sta implementando rapidamente Teams come primo carico di lavoro di Microsoft 365 o Office 365 per supportare i **lavoratori remoti**. In caso di un’organizzazione più grande, usare [Introduzione](get-started-with-teams-quick-start.md) per pilotare Teams con un piccolo gruppo di early adopter in modo da poter conoscere Teams e iniziare a pianificare la distribuzione a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="28bef-p101">Whether you're a small business or a multi-national, the place to start for rolling out Teams is [Get started](get-started-with-teams-quick-start.md). It walks you through a small-scale Teams rollout, which may be all you need if you're a small business, or if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers**. If you're a larger organization, use [Get started](get-started-with-teams-quick-start.md) to pilot Teams with a small group of early adopters so you can learn about Teams and start planning your org-wide deployment.</span></span> 

## <a name="recommended-path-to-teams"></a><span data-ttu-id="28bef-108">Percorso suggerito per Teams</span><span class="sxs-lookup"><span data-stu-id="28bef-108">Recommended path to Teams</span></span>


<span data-ttu-id="28bef-p102">È consigliabile implementare Teams in fasi, un carico di lavoro dopo l’altro, quando l'organizzazione è pronta. **Non è necessario attendere il completamento di un passaggio prima di passare al successivo.** Alcune organizzazioni potrebbero voler distribuire tutte le funzionalità di Teams contemporaneamente, mentre altre potrebbero preferire un procedimento a fasi. Ecco i carichi di lavoro di Teams, nell'ordine in cui è consigliabile implementarli:</span><span class="sxs-lookup"><span data-stu-id="28bef-p102">We recommend rolling out Teams in stages, workload by workload, as your organization is ready. **You don't have to wait until you've completed one step before you move to the next.** Some orgs may want to roll out all Teams features at once, while others may prefer a phased approach. Here are the Teams workloads, in the order we recommend rolling them out:</span></span>

- [<span data-ttu-id="28bef-113">Introduzione</span><span class="sxs-lookup"><span data-stu-id="28bef-113">Get started</span></span>](get-started-with-teams-quick-start.md)
- [<span data-ttu-id="28bef-114">Chat, team, canali e app</span><span class="sxs-lookup"><span data-stu-id="28bef-114">Chat, teams, channels, & apps</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [<span data-ttu-id="28bef-115">Riunioni e conferenze</span><span class="sxs-lookup"><span data-stu-id="28bef-115">Meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="28bef-116">Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="28bef-116">Cloud voice</span></span>](cloud-voice-landing-page.md)

<span data-ttu-id="28bef-117">[Hub di adozione](adopt-microsoft-teams-landing-page.md): durante l'implementazione di Teams è possibile usare queste risorse per agevolare l'adozione di Teams.</span><span class="sxs-lookup"><span data-stu-id="28bef-117">[Adoption hub](adopt-microsoft-teams-landing-page.md): Throughout your Teams rollout, be sure to take advantage of these resources to help drive Teams adoption.</span></span>

![Diagramma che illustra i percorsi di distribuzione di Teams](media/how-to-roll-out-teams-image1.png)


## <a name="if-youre-starting-from-skype-for-business-on-premises-or-hybrid-deployments"></a><span data-ttu-id="28bef-119">Se si inizia da Skype for Business in distribuzioni locali o ibride</span><span class="sxs-lookup"><span data-stu-id="28bef-119">If you're starting from Skype for Business, on-premises, or hybrid deployments</span></span>

<span data-ttu-id="28bef-p103">Se si arriva a Teams da Skype for Business (online o locale) oppure se è necessaria una configurazione ibrida, è comunque necessario seguire il [percorso suggerito](#recommended-path-to-teams) sopra per distribuire Teams, ma prima di tutto vanno eseguite alcune operazioni di pianificazione aggiuntive. Innanzitutto esaminare le linee guida corrispondenti al profilo dell'organizzazione riportate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="28bef-p103">If you're coming to Teams from Skype for Business (online or on premises), or if you need a hybrid configuration, you still want to follow the [recommended path](#recommended-path-to-teams) above for a Teams deployment, but first you need to do some extra planning. Start by reviewing the guidance in the table below that applies to your organization's profile.</span></span>



|  |<span data-ttu-id="28bef-122">Profilo dell’organizzazione</span><span class="sxs-lookup"><span data-stu-id="28bef-122">Your organization's profile</span></span>|<span data-ttu-id="28bef-123">Linee guida</span><span class="sxs-lookup"><span data-stu-id="28bef-123">Guidance</span></span>  |
|---------|---------|---------|
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-teams.svg" alt="Migration arrow symbol" height="50" width="50">|<span data-ttu-id="28bef-124">Attualmente uso Skype for Business Online e sono pronto per passare a Teams.</span><span class="sxs-lookup"><span data-stu-id="28bef-124">I'm currently using Skype for Business Online, and I'm ready to move to Teams.</span></span> |<span data-ttu-id="28bef-125">Passare a [Esegui l'aggiornamento a Teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="28bef-125">Go to [Upgrade to Teams](upgrade-start-here.md).</span></span>        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-teams.svg" alt="Hybrid symbol" height="50" width="50">|<span data-ttu-id="28bef-126">La mia organizzazione usa Skype for Business Server e voglio implementare Teams.</span><span class="sxs-lookup"><span data-stu-id="28bef-126">My organization is running Skype for Business Server, and I want to roll out Teams.</span></span> |<span data-ttu-id="28bef-p104">Per un’implementazione completa di Teams è prima necessario configurare la connettività ibrida tra l'ambiente locale e Microsoft 365. Per iniziare, leggere [Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="28bef-p104">For a full-scale Teams rollout, first you need to configure hybrid connectivity between your on-premises environment and Microsoft 365. Start by reading [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity). </span></span><br><br><span data-ttu-id="28bef-129">È anche consigliabile rivedere [Esegui l'aggiornamento a Teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="28bef-129">You should also review [Upgrade to Teams](upgrade-start-here.md).</span></span>   |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises-teams.svg" alt="On premises symbol" height="50" width="50">|<span data-ttu-id="28bef-p105">Non ho Skype for Business Server, ma ho una soluzione PSTN locale. Voglio distribuire Teams, mantenendo però la soluzione PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="28bef-p105">I don't have Skype for Business Server, but I do have an on-premises PSTN solution. I want to roll out Teams, but I want to keep my on-premises PSTN solution.</span></span> |<span data-ttu-id="28bef-132">Implementare Teams seguendo il [percorso suggerito](#recommended-path-to-teams) indicato sopra.</span><span class="sxs-lookup"><span data-stu-id="28bef-132">Roll out Teams following  the [recommended path](#recommended-path-to-teams) above.</span></span><br><br><span data-ttu-id="28bef-133">Quindi leggere [Pianificare il routing diretto](direct-routing-plan.md) per altre informazioni sull'uso del routing diretto del sistema telefonico per collegare la soluzione PSTN locale a Teams.</span><span class="sxs-lookup"><span data-stu-id="28bef-133">Then read [Plan Direct Routing](direct-routing-plan.md) to learn about using Phone System Direct Routing to hook up your on-premises PSTN solution with Teams.</span></span>|
|


