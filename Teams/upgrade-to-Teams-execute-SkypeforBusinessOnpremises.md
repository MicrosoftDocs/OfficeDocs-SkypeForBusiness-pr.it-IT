---
title: Aggiornare Skype for business locale a Microsoft Teams | Deploy | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerazioni per l'aggiornamento a teams da una distribuzione locale di Skype for business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f234c6fe959d35d2f92e117e28af8d15f0a02819
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235900"
---
<span data-ttu-id="a2980-103">![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione] (media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="a2980-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a2980-104">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a2980-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="a2980-105">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2980-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="a2980-106">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="a2980-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a2980-107">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="a2980-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a2980-108">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="a2980-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a2980-109">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a2980-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a2980-110">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="a2980-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a2980-111">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a2980-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="a2980-112">Condotto un pilota</span><span class="sxs-lookup"><span data-stu-id="a2980-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="a2980-113">Eseguire l'aggiornamento da una distribuzione locale di Skype for business a teams</span><span class="sxs-lookup"><span data-stu-id="a2980-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="a2980-114">Seguire le indicazioni di questo articolo se si è distribuito Skype for business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft teams in modo selettivo, usando più modalità di coesistenza o all-in.</span><span class="sxs-lookup"><span data-stu-id="a2980-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="a2980-115">Passaggio 1: distribuire la connettività ibrida</span><span class="sxs-lookup"><span data-stu-id="a2980-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="a2980-116">Il presupposto chiave per aggiornare gli utenti ai team consiste nel distribuire la connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="a2980-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="a2980-117">Per altre informazioni, vedere [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="a2980-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="a2980-118">Passaggio 2: implementare il viaggio di aggiornamento scelto per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a2980-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="a2980-119">Dopo aver completato la configurazione ibrida, è possibile pianificare la migrazione degli utenti a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a2980-119">After you’ve completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="a2980-120">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="a2980-120">For more information, see:</span></span>

- <span data-ttu-id="a2980-121">[TeamsUpgradePolicy: gestione della migrazione e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)della coesistenza.</span><span class="sxs-lookup"><span data-stu-id="a2980-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="a2980-122">[Trasferire utenti da locali a Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="a2980-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="a2980-123">Aggiornamento di sistema telefonico e teams</span><span class="sxs-lookup"><span data-stu-id="a2980-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="a2980-124">La transizione dai sistemi telefonici locali ai team consente di sfruttare il routing diretto del sistema telefonico ("Direct routing") o i piani di chiamata forniti da Microsoft per Office 365.</span><span class="sxs-lookup"><span data-stu-id="a2980-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing (“Direct Routing”) or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="a2980-125">Se non si usano i piani per le chiamate in Office 365, è necessario eseguire la transizione della distribuzione vocale aziendale al routing diretto del sistema telefonico nell'ambito dell'aggiornamento a teams.</span><span class="sxs-lookup"><span data-stu-id="a2980-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="a2980-126">Per altre informazioni, vedere [considerazioni aggiuntive per il routing diretto del sistema telefonico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="a2980-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="a2980-127">Se si prevede di usare i piani per le chiamate in Office 365, vedere le indicazioni per [trasferire i numeri di telefono in office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="a2980-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>