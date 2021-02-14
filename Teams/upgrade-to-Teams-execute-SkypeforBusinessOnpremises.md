---
title: Aggiornare Skype for Business locale a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione locale di Skype for Business.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820946"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="8467d-103">Eseguire l'aggiornamento da una distribuzione locale di Skype for Business a Teams</span><span class="sxs-lookup"><span data-stu-id="8467d-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="8467d-104">![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="8467d-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="8467d-105">Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8467d-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="8467d-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8467d-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="8467d-107">Integrare gli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="8467d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8467d-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="8467d-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8467d-109">Coesistenza e interoperabilità comprensibili di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="8467d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8467d-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="8467d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="8467d-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="8467d-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="8467d-112">Organizzazione preparata</span><span class="sxs-lookup"><span data-stu-id="8467d-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="8467d-113">Ha diretto un pilota</span><span class="sxs-lookup"><span data-stu-id="8467d-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="8467d-114">Seguire le indicazioni in questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft Teams in modo selettivo, utilizzando più modalità di coesistenza, o all-in.</span><span class="sxs-lookup"><span data-stu-id="8467d-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="8467d-115">Passaggio 1: Distribuire la connettività ibrida</span><span class="sxs-lookup"><span data-stu-id="8467d-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="8467d-116">Il prerequisito fondamentale per l'aggiornamento degli utenti a Teams è la distribuzione della connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="8467d-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="8467d-117">Per ulteriori informazioni, consulta [Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="8467d-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="8467d-118">Passaggio 2: Implementare il percorso di aggiornamento scelto per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8467d-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="8467d-119">Dopo aver completato la configurazione ibrida, è possibile pianificare lo spostamento degli utenti in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="8467d-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="8467d-120">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="8467d-120">For more information, see:</span></span>

- <span data-ttu-id="8467d-121">[TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="8467d-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="8467d-122">[Spostare gli utenti dalla distribuzione locale a Skype for Business online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="8467d-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="8467d-123">Aggiornamento di Sistema telefonico e Teams</span><span class="sxs-lookup"><span data-stu-id="8467d-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="8467d-124">La transizione dai sistemi telefonici locali a Teams ti consentirà di sfruttare l'instradamento diretto del sistema telefonico ("Routing diretto") o dei Piani per chiamate forniti da Microsoft per Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="8467d-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="8467d-125">Se non si usano i Piani per chiamate, è necessario eseguire la transizione della distribuzione voIP aziendale all'instradamento diretto del sistema telefonico nell'ambito dell'aggiornamento a Teams.</span><span class="sxs-lookup"><span data-stu-id="8467d-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="8467d-126">Per ulteriori informazioni, consulta [ulteriori considerazioni sull'instradamento diretto del sistema telefonico.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="8467d-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="8467d-127">Se stai pianificando di utilizzare i Piani per chiamate, consulta le nostre indicazioni per il trasferimento dei numeri [di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8467d-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>