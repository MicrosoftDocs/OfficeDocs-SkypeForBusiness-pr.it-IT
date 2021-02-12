---
title: Eseguire l'aggiornamento a Teams da una distribuzione locale di Skype for Business - Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
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
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578399"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="162bf-103">Eseguire l'aggiornamento da Skype for Business a Teams &mdash; per amministratori IT</span><span class="sxs-lookup"><span data-stu-id="162bf-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="162bf-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="162bf-104">Overview</span></span>

<span data-ttu-id="162bf-105">Durante l'aggiornamento da Skype for Business a Teams, alcune organizzazioni richiedono un'implementazione progressiva pianificata e gestita dai reparti IT.</span><span class="sxs-lookup"><span data-stu-id="162bf-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="162bf-106">Gli articoli di questa sezione sono applicabili principalmente agli amministratori IT di organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="162bf-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="162bf-107">Queste organizzazioni sono in genere locali, ma potrebbero anche essere grandi organizzazioni Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="162bf-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="162bf-108">Prima di leggere questi articoli, assicurarsi di leggere Guida introduttiva all'aggiornamento di [Teams](upgrade-start-here.md) [e Informazioni sul framework di aggiornamento.](upgrade-framework.md)</span><span class="sxs-lookup"><span data-stu-id="162bf-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="162bf-109">Gli articoli seguenti guidano il processo di aggiornamento per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="162bf-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="162bf-110">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="162bf-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="162bf-111">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="162bf-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="162bf-112">Considerazioni aggiuntive per le organizzazioni con Skype for Business locale</span><span class="sxs-lookup"><span data-stu-id="162bf-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="162bf-113">Implementare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="162bf-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="162bf-114">Considerazioni sulla rete PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="162bf-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="162bf-115">Gli articoli seguenti descrivono inoltre concetti importanti sull'aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="162bf-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="162bf-116">Coesistenza di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="162bf-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="162bf-117">Modalità di coesistenza - Riferimento</span><span class="sxs-lookup"><span data-stu-id="162bf-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="162bf-118">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="162bf-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="162bf-119">In questi articoli vengono utilizzati i termini Skype for Business online, Skype for Business Server locale e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="162bf-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="162bf-120">Quest'ultimo termine fa riferimento sia alle versioni online che a versioni locali.</span><span class="sxs-lookup"><span data-stu-id="162bf-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="162bf-121">Prima di iniziare, tenere presente che un utente migrato a Teams non usa più un client Skype for Business se non per partecipare a una riunione ospitata in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="162bf-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="162bf-122">Tutte le chat e le chiamate in arrivo vengono effettuate nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi Teams o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="162bf-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="162bf-123">Tutte le nuove riunioni organizzate dall'utente di cui è stata eseguita la migrazione verranno pianificate come riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="162bf-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="162bf-124">Se l'utente prova a usare il client Skype for Business, l'avvio delle chat e delle chiamate viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="162bf-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="162bf-125">Tuttavia, l'utente può (e deve) continuare a usare il client Skype for Business per partecipare alle riunioni Skype for Business a cui è stato invitato.</span><span class="sxs-lookup"><span data-stu-id="162bf-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="162bf-126">I client Skype for Business precedenti al 2017 non rispettano il TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="162bf-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="162bf-127">Accertati di utilizzare l'ultima versione del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="162bf-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="162bf-128">Puoi gestire la transizione dell'utente a Teams utilizzando il concetto di [modalità,](migration-interop-guidance-for-teams-with-skype.md)che è una proprietà di [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="162bf-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="162bf-129">Un utente migrato a Teams come descritto in precedenza è in modalità "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="162bf-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="162bf-130">Per un'organizzazione che sta eseguendo la migrazione a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="162bf-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="162bf-131">Gli utenti che dispongono di un account Skype for Business locale non possono essere TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="162bf-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="162bf-132">Anche se questi utenti [possono usare Teams in](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)modalità Isole, questo non fornisce il set completo di funzionalità di Teams disponibile in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="162bf-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="162bf-133">Per rendere questi utenti TeamsOnly, devono essere spostati nel cloud usando gli strumenti locali di `Move-CsUser` Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="162bf-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="162bf-134">Ok.</span><span class="sxs-lookup"><span data-stu-id="162bf-134">OK.</span></span> <span data-ttu-id="162bf-135">Iniziamo.</span><span class="sxs-lookup"><span data-stu-id="162bf-135">Let's get started.</span></span>  <span data-ttu-id="162bf-136">Il primo passaggio consiste nel comprendere i [metodi di aggiornamento disponibili.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="162bf-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="162bf-137">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="162bf-137">Related links</span></span>

[<span data-ttu-id="162bf-138">Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="162bf-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="162bf-139">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="162bf-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="162bf-140">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="162bf-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="162bf-141">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="162bf-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="162bf-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="162bf-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="162bf-143">Uso del servizio MMS (Meeting Migration Service)</span><span class="sxs-lookup"><span data-stu-id="162bf-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

