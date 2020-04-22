---
title: Aggiornare Skype for Business locale a Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Distribuire e implementare l'aggiornamento a teams da una distribuzione locale di Skype for Business Server o Microsoft Lync.
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
ms.openlocfilehash: ac5045df6462be28d7f13e093695376ea612e6cd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780155"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="772c3-103">Eseguire l'aggiornamento da Skype for business locale a teams</span><span class="sxs-lookup"><span data-stu-id="772c3-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="772c3-104">![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="772c3-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="772c3-105">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="772c3-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="772c3-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="772c3-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="772c3-107">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="772c3-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="772c3-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="772c3-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="772c3-109">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="772c3-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="772c3-110">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="772c3-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="772c3-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="772c3-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="772c3-112">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="772c3-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="772c3-113">Condotto un pilota</span><span class="sxs-lookup"><span data-stu-id="772c3-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="772c3-114">Se si è implementato Skype for Business Server o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a teams, seguire le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="772c3-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="772c3-115">È necessario configurare la connettività ibrida con l'organizzazione di Office 365 e determinare i requisiti di coesistenza se si stanno spostando gli utenti in teams in fasi.</span><span class="sxs-lookup"><span data-stu-id="772c3-115">You need to set up hybrid connectivity with your Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="772c3-116">Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato.</span><span class="sxs-lookup"><span data-stu-id="772c3-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="772c3-117">Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="772c3-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="772c3-118">Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="772c3-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="772c3-119">Passaggio 1: configurare la connettività ibrida</span><span class="sxs-lookup"><span data-stu-id="772c3-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="772c3-120">Il presupposto chiave per l'aggiornamento degli utenti locali ai team è la configurazione della connettività ibrida per la distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="772c3-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="772c3-121">Iniziare leggendo il [piano di connettività ibrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e quindi seguire le attività descritte in [configurare la connettività ibrida](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="772c3-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="772c3-122">Passaggio 2: impostare la modalità di coesistenza transitoria (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="772c3-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="772c3-123">La coesistenza e l'interoperabilità tra i client e gli utenti di Skype for business e teams sono definiti dalle modalità di aggiornamento dei team.</span><span class="sxs-lookup"><span data-stu-id="772c3-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="772c3-124">Per impostazione predefinita, le organizzazioni sono in modalità isole, che consente agli utenti di usare entrambi i team e i client Skype for business affiancati.</span><span class="sxs-lookup"><span data-stu-id="772c3-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="772c3-125">Per un'organizzazione che si sposta in teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati TeamsOnly (o qualsiasi altra modalità) allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="772c3-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="772c3-126">Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono facoltativamente usare una qualsiasi delle modalità di coesistenza di Skype for business per garantire una comunicazione prevedibile tra gli utenti che si trovano in modalità TeamsOnly e gli utenti che non sono ancora stati.</span><span class="sxs-lookup"><span data-stu-id="772c3-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="772c3-127">Lo scopo delle modalità di coesistenza di Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è quello di creare un'esperienza semplice e prevedibile per gli utenti finali come organizzazioni di transizione da Skype for business a teams.</span><span class="sxs-lookup"><span data-stu-id="772c3-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="772c3-128">Quando un utente si trova in una delle modalità Skype for business, tutte le chat in arrivo e le chiamate vengono instradate al client Skype for business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="772c3-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="772c3-129">Per evitare confusione per gli utenti finali e garantire un corretto routing, le funzionalità di chiamata e chat nel client teams vengono disabilitate quando un utente si trova in una delle modalità Skype for business.</span><span class="sxs-lookup"><span data-stu-id="772c3-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="772c3-130">Analogamente, la pianificazione delle riunioni in teams viene disabilitata esplicitamente quando gli utenti si trovano nelle modalità SfBOnly o SfBWithTeamsCollab e abilitata esplicitamente quando un utente si trova in modalità SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="772c3-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="772c3-131">A seconda dei requisiti, è possibile assegnare la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="772c3-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="772c3-132">Per altre informazioni, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) e per [impostare le impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="772c3-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="772c3-133">Passaggio 3: trasferire gli utenti da Skype for business locale a teams only</span><span class="sxs-lookup"><span data-stu-id="772c3-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="772c3-134">In definitiva, vorrai trasferire gli utenti in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="772c3-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="772c3-135">Questo potrebbe includere uno o due passaggi a seconda dell'ambiente locale corrente.</span><span class="sxs-lookup"><span data-stu-id="772c3-135">This might involve one or two steps depending on your current on-premises environment.</span></span>  

<span data-ttu-id="772c3-136">Per altre informazioni, vedere [trasferire gli utenti tra locale e il cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e [trasferire gli utenti da locale a teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span><span class="sxs-lookup"><span data-stu-id="772c3-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 



## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="772c3-137">Aggiornamento di sistema telefonico e teams</span><span class="sxs-lookup"><span data-stu-id="772c3-137">Phone System and Teams upgrade</span></span>

<span data-ttu-id="772c3-138">Se si sta passando la distribuzione di Skype for business al sistema telefonico con i piani di chiamata, Microsoft sarà il provider PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="772c3-138">If you are transitioning your Skype for Business deployment to Phone System with Calling Plans, Microsoft will be your public switched telephone network (PSTN) provider.</span></span> <span data-ttu-id="772c3-139">Supponendo che tu abbia completato la portabilità del numero di telefono, l'aggiornamento degli utenti a teams eseguirà automaticamente la transizione delle chiamate PSTN in ingresso ai team.</span><span class="sxs-lookup"><span data-stu-id="772c3-139">Assuming that you've completed the phone number porting--upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="772c3-140">Se si sta eseguendo la transizione alla distribuzione di Skype for business al sistema telefonico, ma non si usano i piani di chiamata, è necessario eseguire la transizione della distribuzione vocale aziendale al routing diretto di Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="772c3-140">If you are transitioning your Skype for Business deployment to Phone System but are not using Calling Plans, you  need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="772c3-141">Per altre informazioni, Vedi [routing diretto del sistema telefonico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="772c3-141">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>
