---
title: Aggiornare Skype for Business locale a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione Skype for Business locale.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115554"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="0fb48-103">Eseguire l'aggiornamento da Skype for Business distribuzione locale a Teams</span><span class="sxs-lookup"><span data-stu-id="0fb48-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="0fb48-104">![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="0fb48-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="0fb48-105">Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0fb48-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="0fb48-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fb48-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="0fb48-107">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="0fb48-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="0fb48-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="0fb48-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="0fb48-109">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="0fb48-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="0fb48-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0fb48-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="0fb48-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="0fb48-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="0fb48-112">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0fb48-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="0fb48-113">Ha condotto un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="0fb48-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="0fb48-114">Seguire le indicazioni di questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft Teams in modo selettivo, usando più modalità di coesistenza o all-in.</span><span class="sxs-lookup"><span data-stu-id="0fb48-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="0fb48-115">Passaggio 1: Distribuire la connettività ibrida</span><span class="sxs-lookup"><span data-stu-id="0fb48-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="0fb48-116">Il prerequisito fondamentale per l'aggiornamento degli utenti a Teams è la distribuzione della connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="0fb48-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="0fb48-117">Per altre informazioni, vedere [Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="0fb48-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="0fb48-118">Passaggio 2: Implementare il percorso di aggiornamento scelto per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0fb48-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="0fb48-119">Dopo aver completato la configurazione ibrida, è possibile pianificare lo spostamento degli utenti in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="0fb48-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="0fb48-120">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0fb48-120">For more information, see:</span></span>

- <span data-ttu-id="0fb48-121">[TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="0fb48-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="0fb48-122">[Spostare gli utenti da locale a Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="0fb48-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="0fb48-123">Sistema telefonico e Teams aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0fb48-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="0fb48-124">La transizione dai sistemi telefonici locali a Teams consente di sfruttare Sistema telefonico Direct Routing ("Direct Routing") o i Piani per le chiamate forniti da Microsoft per Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="0fb48-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="0fb48-125">Se non si usa Piani per chiamate, è necessario eseguire la transizione della distribuzione voIP aziendale a Sistema telefonico Routing diretto nell'ambito dell'aggiornamento a Teams.</span><span class="sxs-lookup"><span data-stu-id="0fb48-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="0fb48-126">Per altre informazioni, vedere [considerazioni aggiuntive per Sistema telefonico routing diretto](./direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="0fb48-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="0fb48-127">Se stai pianificando di usare Piani per chiamate, consulta le nostre indicazioni per trasferire i tuoi numeri di telefono a [Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0fb48-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>