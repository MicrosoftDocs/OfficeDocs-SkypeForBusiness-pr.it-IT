---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e146394b5f000ce984d7bfaff5e6674c2c091b98
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955889"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="092eb-103">Eseguire l'aggiornamento da Skype for business a teams &mdash; per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="092eb-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="092eb-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="092eb-104">Overview</span></span>

<span data-ttu-id="092eb-105">Quando si esegue l'aggiornamento da Skype for business a teams, alcune organizzazioni richiedono un'implementazione progressiva progettata e gestita dai rispettivi reparti IT.</span><span class="sxs-lookup"><span data-stu-id="092eb-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="092eb-106">Gli articoli di questa sezione si applicano principalmente agli amministratori IT delle organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="092eb-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="092eb-107">Queste organizzazioni sono in genere locali, ma potrebbero anche essere grandi organizzazioni di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="092eb-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="092eb-108">Prima di leggere questi articoli, leggere introduzione all' [aggiornamento dei team](upgrade-start-here.md) e [informazioni sul Framework di aggiornamento](upgrade-framework.md).</span><span class="sxs-lookup"><span data-stu-id="092eb-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="092eb-109">Gli articoli seguenti ti guideranno nel processo di aggiornamento per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="092eb-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="092eb-110">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="092eb-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="092eb-111">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="092eb-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="092eb-112">Considerazioni aggiuntive per le organizzazioni con Skype for business locale</span><span class="sxs-lookup"><span data-stu-id="092eb-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="092eb-113">Implementare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="092eb-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="092eb-114">Considerazioni su PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="092eb-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="092eb-115">Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="092eb-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="092eb-116">Coesistenza di teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="092eb-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="092eb-117">Modalità di coesistenza-riferimento</span><span class="sxs-lookup"><span data-stu-id="092eb-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="092eb-118">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="092eb-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="092eb-119">Questi articoli usano i termini Skype for business online, Skype for Business Server locale e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="092eb-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="092eb-120">Quest'ultimo termine si riferisce sia alle versioni online che a quelle locali.</span><span class="sxs-lookup"><span data-stu-id="092eb-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="092eb-121">Prima di iniziare, tieni presente che un utente che ha eseguito la migrazione a teams non usa più un client Skype for business tranne che per partecipare a una riunione ospitata in Skype for business.</span><span class="sxs-lookup"><span data-stu-id="092eb-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="092eb-122">Tutte le chat in arrivo e le chiamate atterrano nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi team o Skype for business.</span><span class="sxs-lookup"><span data-stu-id="092eb-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="092eb-123">Tutte le nuove riunioni organizzate dall'utente migrato saranno programmate come riunioni teams.</span><span class="sxs-lookup"><span data-stu-id="092eb-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="092eb-124">Se l'utente tenta di usare il client Skype for business, l'avvio delle chat e delle chiamate è bloccato.</span><span class="sxs-lookup"><span data-stu-id="092eb-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="092eb-125">L'utente può comunque usare il client Skype for business per partecipare a riunioni Skype for business a cui sono invitati.</span><span class="sxs-lookup"><span data-stu-id="092eb-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="092eb-126">I client Skype for business meno recenti forniti prima di 2017 non onorano TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="092eb-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="092eb-127">Verificare che si stia usando il client Skype for business più recente.</span><span class="sxs-lookup"><span data-stu-id="092eb-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="092eb-128">Puoi gestire la transizione dell'utente a teams usando il concetto di [modalità](migration-interop-guidance-for-teams-with-skype.md), che è una proprietà di [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="092eb-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="092eb-129">Un utente che ha eseguito la migrazione a teams come descritto in precedenza è in modalità "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="092eb-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="092eb-130">Per un'organizzazione che sta migrando a teams, l'obiettivo finale è quello di trasferire tutti gli utenti alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="092eb-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

<span data-ttu-id="092eb-131">Ok.</span><span class="sxs-lookup"><span data-stu-id="092eb-131">OK.</span></span> <span data-ttu-id="092eb-132">Iniziamo.</span><span class="sxs-lookup"><span data-stu-id="092eb-132">Let's get started.</span></span>  <span data-ttu-id="092eb-133">Il primo passaggio consiste nel comprendere i [metodi di aggiornamento disponibili](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="092eb-133">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="092eb-134">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="092eb-134">Related links</span></span>

[<span data-ttu-id="092eb-135">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="092eb-135">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="092eb-136">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="092eb-136">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="092eb-137">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="092eb-137">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="092eb-138">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="092eb-138">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="092eb-139">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="092eb-139">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="092eb-140">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="092eb-140">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

