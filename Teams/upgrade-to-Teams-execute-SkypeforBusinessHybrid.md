---
title: Aggiornare Skype for Business distribuzione ibrida a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una Skype for Business ibrida.
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104022"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="f0475-103">Eseguire l'aggiornamento da Skype for Business distribuzione ibrida a Teams</span><span class="sxs-lookup"><span data-stu-id="f0475-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="f0475-104">![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="f0475-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f0475-105">Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f0475-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="f0475-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0475-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="f0475-107">Coinvolgimento degli stakeholder del progetto</span><span class="sxs-lookup"><span data-stu-id="f0475-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f0475-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="f0475-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="f0475-109">Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="f0475-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f0475-110">Hai scelto il percorso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f0475-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="f0475-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="f0475-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="f0475-112">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f0475-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="f0475-113">Ha condotto un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="f0475-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="f0475-114">Seguire le indicazioni di questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e lo si è configurato in una distribuzione ibrida con l'organizzazione di Microsoft 365 o Office 365 e l'organizzazione vuole eseguire l'aggiornamento a Teams in modo selettivo, usando più modalità di coesistenza o all-in.</span><span class="sxs-lookup"><span data-stu-id="f0475-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="f0475-115">Per entrambi i percorsi di aggiornamento, è necessario spostare gli utenti in Skype for Business Online (se non sono già ospitati online) e quindi assegnare loro la modalità di coesistenza e aggiornamento appropriata.</span><span class="sxs-lookup"><span data-stu-id="f0475-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="f0475-116">Passaggio 1: Spostare gli utenti in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f0475-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="f0475-117">Questo passaggio si applica agli utenti attualmente ospitati in locale.</span><span class="sxs-lookup"><span data-stu-id="f0475-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="f0475-118">Per altre informazioni sullo spostamento di questi utenti in Skype for Business Online, vedere Spostare gli utenti da locale a [Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="f0475-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="f0475-119">Passaggio 2: Assegnare una modalità di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f0475-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="f0475-120">Dopo aver spostato gli utenti in Skype for Business Online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f0475-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="f0475-121">Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](./setting-your-coexistence-and-upgrade-settings.md) e aggiornamento e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="f0475-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f0475-122">Con Skype for Business Server 2019 e un aggiornamento cumulativo futuro di Skype for Business Server 2015, sarà possibile eseguire il passaggio 1 (spostare gli utenti in Skype for Business Online) e il passaggio 2 (aggiornare gli utenti a Teams) in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="f0475-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="f0475-123">Altre informazioni verranno fornite dopo il Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f0475-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="f0475-124">Sistema telefonico e Teams aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f0475-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="f0475-125">Se stai eseguendo la transizione della distribuzione ibrida di Skype for Business a Sistema telefonico con Piani per le chiamate e Microsoft sarà il tuo provider di rete PSTN (Public Switched Telephone Network) e presupponendo che sia stata completata la portabilità del numero di telefono, l'aggiornamento degli utenti a Teams esegue automaticamente la transizione delle chiamate PSTN in ingresso a Teams.</span><span class="sxs-lookup"><span data-stu-id="f0475-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="f0475-126">Se Piani per chiamate non è disponibile o si prevede di usare il provider di connettività PSTN esistente, è necessario eseguire la transizione della distribuzione voIP aziendale o della distribuzione vocale ibrida che usa la distribuzione locale esistente o Cloud Connector Edition a Telefono Microsoft System Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="f0475-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="f0475-127">Per aggiornare gli utenti a Teams, vedere le considerazioni aggiuntive per [Sistema telefonico routing diretto.](./direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="f0475-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>