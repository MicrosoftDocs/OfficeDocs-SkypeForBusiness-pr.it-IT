---
title: Aggiornare Skype for Business locale a Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione locale di Skype for business.
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
ms.openlocfilehash: 34502fe9883c98179a6b2e23cd8360ae823c1853
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666018"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="2a545-103">Eseguire l'aggiornamento da una distribuzione locale di Skype for business a teams</span><span class="sxs-lookup"><span data-stu-id="2a545-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="2a545-104">![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="2a545-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="2a545-105">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2a545-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="2a545-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a545-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="2a545-107">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="2a545-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="2a545-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="2a545-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="2a545-109">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="2a545-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="2a545-110">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a545-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="2a545-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="2a545-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="2a545-112">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2a545-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="2a545-113">Condotto un pilota</span><span class="sxs-lookup"><span data-stu-id="2a545-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="2a545-114">Seguire le indicazioni di questo articolo se si è distribuito Skype for business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft teams in modo selettivo, usando più modalità di coesistenza o all-in.</span><span class="sxs-lookup"><span data-stu-id="2a545-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="2a545-115">Passaggio 1: distribuire la connettività ibrida</span><span class="sxs-lookup"><span data-stu-id="2a545-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="2a545-116">Il presupposto chiave per aggiornare gli utenti ai team consiste nel distribuire la connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="2a545-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="2a545-117">Per altre informazioni, vedere [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="2a545-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="2a545-118">Passaggio 2: implementare il viaggio di aggiornamento scelto per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2a545-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="2a545-119">Dopo aver completato la configurazione ibrida, è possibile pianificare di trasferire gli utenti a Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a545-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="2a545-120">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="2a545-120">For more information, see:</span></span>

- <span data-ttu-id="2a545-121">[TeamsUpgradePolicy: gestione della migrazione e della coesistenza](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="2a545-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="2a545-122">[Trasferire utenti da locali a Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="2a545-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="2a545-123">Aggiornamento di sistema telefonico e teams</span><span class="sxs-lookup"><span data-stu-id="2a545-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="2a545-124">La transizione dai sistemi telefonici locali ai team consente di sfruttare il routing diretto del sistema telefonico ("Direct routing") o i piani per le chiamate fornite da Microsoft per Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a545-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="2a545-125">Se non si usano i piani di chiamata, è necessario eseguire la transizione della distribuzione di VoIP aziendale al routing diretto del sistema telefonico nell'ambito dell'aggiornamento a teams.</span><span class="sxs-lookup"><span data-stu-id="2a545-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="2a545-126">Per altre informazioni, vedere [considerazioni aggiuntive per il routing diretto del sistema telefonico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="2a545-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="2a545-127">Se si prevede di usare i piani per le chiamate, vedere le indicazioni per [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2a545-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>