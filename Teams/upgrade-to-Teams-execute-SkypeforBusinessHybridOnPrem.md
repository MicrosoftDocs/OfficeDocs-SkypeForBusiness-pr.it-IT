---
title: Eseguire l'aggiornamento a teams da una distribuzione ibrida o locale di Skype for Business-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerazioni per l'aggiornamento a teams da una distribuzione ibrida o locale di Skype for business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 873e15e5b1f64e82889bfda6fa30c5b9394dcf3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235873"
---
<span data-ttu-id="44dc5-103">![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione] (media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="44dc5-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="44dc5-104">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="44dc5-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="44dc5-105">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="44dc5-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="44dc5-106">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="44dc5-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="44dc5-107">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="44dc5-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="44dc5-108">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="44dc5-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="44dc5-109">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="44dc5-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="44dc5-110">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="44dc5-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="44dc5-111">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="44dc5-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="44dc5-112">Condotto un pilota</span><span class="sxs-lookup"><span data-stu-id="44dc5-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="44dc5-113">Eseguire l'aggiornamento a teams da una distribuzione ibrida o locale di Skype for business</span><span class="sxs-lookup"><span data-stu-id="44dc5-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="44dc5-114">Seguire le indicazioni di questo articolo se si è distribuito Skype for business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a team in modo selettivo, usando più modalità di coesistenza o all-in.</span><span class="sxs-lookup"><span data-stu-id="44dc5-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="44dc5-115">Il primo passaggio consiste nel configurare la connettività ibrida con il tenant di Office 365 e quindi trasferire gli utenti a Skype for business online e assegnare loro la modalità di coesistenza e aggiornamento appropriata.</span><span class="sxs-lookup"><span data-stu-id="44dc5-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="44dc5-116">Skype for business online verrà ritirato il 31 luglio 2021, dopodiché non sarà più accessibile o supportato.</span><span class="sxs-lookup"><span data-stu-id="44dc5-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="44dc5-117">Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="44dc5-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="44dc5-118">Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="44dc5-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="44dc5-119">Passaggio 1: distribuire la connettività ibrida</span><span class="sxs-lookup"><span data-stu-id="44dc5-119">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="44dc5-120">Il presupposto chiave per aggiornare gli utenti ai team consiste nel distribuire la connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="44dc5-120">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="44dc5-121">Questo potrebbe comportare la distribuzione di una nuova connettività esterna per la distribuzione di Skype for business o Lync esistente oppure semplicemente la configurazione di una relazione ibrida con il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="44dc5-121">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="44dc5-122">Per altre informazioni, Vedi [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="44dc5-122">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="44dc5-123">Passaggio 2: trasferire gli utenti in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="44dc5-123">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="44dc5-124">Dopo aver completato la configurazione ibrida, sposta gli utenti in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="44dc5-124">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="44dc5-125">Per altre informazioni, vedere [trasferire utenti da locali a Skype for business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="44dc5-125">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="44dc5-126">Passaggio 3: assegnare una modalità di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="44dc5-126">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="44dc5-127">Dopo aver spostato gli utenti in Skype for business online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44dc5-127">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="44dc5-128">Per altre informazioni, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: gestione della migrazione e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)della coesistenza.</span><span class="sxs-lookup"><span data-stu-id="44dc5-128">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="44dc5-129">Con Skype for Business Server 2019 e un futuro aggiornamento cumulativo di Skype for Business Server 2015, è possibile eseguire il passaggio 2 (spostamento degli utenti in Skype for business online) e il passaggio 3 (aggiornare gli utenti ai team) in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="44dc5-129">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="44dc5-130">Altre informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="44dc5-130">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="44dc5-131">Aggiornamento di sistema telefonico e teams</span><span class="sxs-lookup"><span data-stu-id="44dc5-131">Phone System and Teams upgrade</span></span>

<span data-ttu-id="44dc5-132">Se si sta eseguendo la transizione della distribuzione ibrida di Skype for business al sistema telefonico con i piani per le chiamate e Microsoft sarà il provider PSTN (Public Switched Telephone Network) e supponendo di aver completato la portabilità del numero di telefono, aggiornare gli utenti a I team eseguiranno automaticamente la transizione delle chiamate PSTN in ingresso ai team.</span><span class="sxs-lookup"><span data-stu-id="44dc5-132">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="44dc5-133">Se i piani per le chiamate non sono disponibili, è necessario eseguire la transizione della distribuzione vocale aziendale al routing diretto di Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="44dc5-133">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="44dc5-134">Per aggiornare gli utenti a teams, vedere le [considerazioni aggiuntive per il routing diretto del sistema telefonico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="44dc5-134">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
