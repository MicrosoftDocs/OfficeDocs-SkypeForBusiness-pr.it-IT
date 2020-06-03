---
title: Aggiornare la distribuzione ibrida di Skype for business ai team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione ibrida di Skype for business.
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
ms.openlocfilehash: a9cc76313bb65a79241e26ab70a38d8698f27e7c
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523439"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="62e6a-103">Eseguire l'aggiornamento da una distribuzione ibrida di Skype for business a teams</span><span class="sxs-lookup"><span data-stu-id="62e6a-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="62e6a-104">![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")</span><span class="sxs-lookup"><span data-stu-id="62e6a-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="62e6a-105">Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="62e6a-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="62e6a-106">Prima di procedere, verificare di aver completato le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="62e6a-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="62e6a-107">Elenco delle parti interessate del progetto</span><span class="sxs-lookup"><span data-stu-id="62e6a-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="62e6a-108">Definizione dell'ambito del progetto</span><span class="sxs-lookup"><span data-stu-id="62e6a-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="62e6a-109">Coesistenza e interoperabilità intesa di Skype for business e teams</span><span class="sxs-lookup"><span data-stu-id="62e6a-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="62e6a-110">Scelto il viaggio di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="62e6a-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="62e6a-111">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="62e6a-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="62e6a-112">Preparare l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="62e6a-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="62e6a-113">Condotto un pilota</span><span class="sxs-lookup"><span data-stu-id="62e6a-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="62e6a-114">Seguire le indicazioni di questo articolo se è stata distribuita in locale Skype for business o Microsoft Lync e la si è configurata in una distribuzione ibrida con l'organizzazione di Office 365 e l'organizzazione vuole eseguire l'aggiornamento ai team in modo selettivo, usando più modalità di coesistenza o all-in.</span><span class="sxs-lookup"><span data-stu-id="62e6a-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="62e6a-115">Per entrambi i percorsi di aggiornamento, è necessario trasferire gli utenti a Skype for business online (se non sono già stati ospitati online) e quindi assegnare loro la modalità di coesistenza e di aggiornamento appropriata.</span><span class="sxs-lookup"><span data-stu-id="62e6a-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="62e6a-116">Passaggio 1: trasferire gli utenti in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="62e6a-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="62e6a-117">Questo passaggio si applica agli utenti attualmente residenti in locale.</span><span class="sxs-lookup"><span data-stu-id="62e6a-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="62e6a-118">Per altre informazioni sullo spostamento di questi utenti in Skype for business online, vedere [spostare gli utenti da locale a Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="62e6a-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="62e6a-119">Passaggio 2: assegnare una modalità di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="62e6a-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="62e6a-120">Dopo aver spostato gli utenti in Skype for business online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="62e6a-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="62e6a-121">Per altre informazioni, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="62e6a-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="62e6a-122">Con Skype for Business Server 2019 e un futuro aggiornamento cumulativo di Skype for Business Server 2015, sarà possibile eseguire il passaggio 1 (spostando gli utenti in Skype for business online) e il passaggio 2 (aggiornare gli utenti ai team) in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="62e6a-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="62e6a-123">Altre informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="62e6a-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="62e6a-124">Aggiornamento di sistema telefonico e teams</span><span class="sxs-lookup"><span data-stu-id="62e6a-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="62e6a-125">Se si sta eseguendo la transizione della distribuzione ibrida di Skype for business al sistema telefonico con i piani per le chiamate e Microsoft sarà il provider PSTN (Public Switched Telephone Network) e supponendo che sia stata completata la portabilità del numero di telefono, l'aggiornamento degli utenti a teams eseguirà automaticamente la transizione delle chiamate PSTN in ingresso ai team.</span><span class="sxs-lookup"><span data-stu-id="62e6a-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="62e6a-126">Se i piani per le chiamate non sono disponibili o si intende usare il provider di connettività PSTN esistente, è necessario eseguire la transizione della distribuzione vocale aziendale oppure una distribuzione vocale ibrida che usa la distribuzione locale esistente o il Cloud Connector Edition, al routing diretto di Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="62e6a-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="62e6a-127">Per aggiornare gli utenti a teams, vedere le [considerazioni aggiuntive per il routing diretto del sistema telefonico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="62e6a-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
