---
title: Aggiornamenti assistiti | Skype Aggiornamento di Business Online Teams business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Panoramica degli aggiornamenti assistiti da Skype for Business Online a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e445fd6c5d26a64005ff1c285d8e9d843ca0211
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656059"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="d668b-103">Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d668b-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="d668b-104">Microsoft offre aggiornamenti assistiti a Teams per aiutare le organizzazioni a eseguire una transizione corretta da Skype for Business Online man mano che il servizio si ritira il 31 luglio 2021.</span><span class="sxs-lookup"><span data-stu-id="d668b-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="d668b-105">Sia che l'organizzazione eserciti l'aggiornamento da un ambiente Skype for Business *Online* o *Skype for Business Online* con ambienti ibridi (utenti sia in Skype for Business Online che in Skype for Business Server), gli aggiornamenti assistiti riducono il numero di attività tecniche da eseguire e consentono di concentrarsi più sulla preparazione dell'organizzazione, sulla consapevolezza degli utenti e sulla formazione Teams. </span><span class="sxs-lookup"><span data-stu-id="d668b-105">Whether your organization is upgrading from a *Skype for Business Online* or *Skype for Business Online with hybrid* (users in both Skype for Business Online **and** Skype for Business Server) environment, assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="d668b-106">È consigliabile consultare le indicazioni per [l'aggiornamento prima](https://aka.ms/SkypeToTeams) dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d668b-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="d668b-107">Le indicazioni sull'aggiornamento includono attività consigliate e risorse utili per completare un aggiornamento da Skype for Business Online a Teams.</span><span class="sxs-lookup"><span data-stu-id="d668b-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="d668b-108">Queste indicazioni si applicano a qualsiasi organizzazione che pianifica un aggiornamento a Teams, indipendentemente dal fatto che gestirà tutti gli aspetti dell'aggiornamento o userà il processo assistito.</span><span class="sxs-lookup"><span data-stu-id="d668b-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="d668b-109">Se è stato pianificato un aggiornamento assistito a Teams, è possibile eseguire un aggiornamento personalizzato da Skype for Business Online prima della data di aggiornamento pianificata.</span><span class="sxs-lookup"><span data-stu-id="d668b-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="d668b-110">Per altre informazioni su come eseguire manualmente l'aggiornamento a Teams, vedere le indicazioni [per l'aggiornamento.](https://aka.ms/SkypeToTeams)</span><span class="sxs-lookup"><span data-stu-id="d668b-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="d668b-111">Gli aggiornamenti assistiti non sono disponibili per le distribuzioni locali di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d668b-111">Assisted upgrades are not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="d668b-112">Notifiche per i clienti programmati</span><span class="sxs-lookup"><span data-stu-id="d668b-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="d668b-113">Skype for Business I clienti online pianificati per gli aggiornamenti assistiti Teams riceveranno una serie di notifiche di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d668b-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="d668b-114">Queste notifiche inizieranno 90 giorni prima della data di aggiornamento pianificata.</span><span class="sxs-lookup"><span data-stu-id="d668b-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="d668b-115">Queste notifiche verranno recapitate come post Di pianificazione per la modifica nel Centro messaggi di Microsoft 365, notifiche del dashboard di aggiornamento nell'interfaccia di amministrazione di Teams e contrassegni in-app agli utenti finali. </span><span class="sxs-lookup"><span data-stu-id="d668b-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="d668b-116">Le notifiche di aggiornamento includeranno la data pianificata dell'aggiornamento assistito e un collegamento alle risorse di aggiornamento e alla formazione per facilitare l'adozione e l'uso di Teams.</span><span class="sxs-lookup"><span data-stu-id="d668b-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="d668b-117">Esperienza di aggiornamento assistito</span><span class="sxs-lookup"><span data-stu-id="d668b-117">The assisted upgrade experience</span></span>

<span data-ttu-id="d668b-118">Gli aggiornamenti assistiti inizieranno ad agosto 2021 con date specifiche del tenant condivise nelle notifiche di pianificazione menzionate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d668b-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="d668b-119">L'esperienza di aggiornamento assistito varia leggermente a seconda che si abbia un Skype for Business solo online o un Skype for Business Online con ambiente ibrido:</span><span class="sxs-lookup"><span data-stu-id="d668b-119">Your assisted upgrade experience will differ slightly depending on whether you have a Skype for Business Online-only or a Skype for Business Online with hybrid environment:</span></span>

- <span data-ttu-id="d668b-120">**Skype for Business solo online** Il processo di aggiornamento assistito applierà `TeamsUpgradeOverridePolicy` i criteri all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d668b-120">**Skype for Business Online-only** The assisted upgrade process will apply the `TeamsUpgradeOverridePolicy` policy to your organization.</span></span> <span data-ttu-id="d668b-121">Quando si applica questo criterio, tutti gli utenti Skype for Business online verranno inseriti in Teams Solo utenti.</span><span class="sxs-lookup"><span data-stu-id="d668b-121">When this policy is applied, all your Skype for Business Online users will be placed in Teams Only mode.</span></span>
- <span data-ttu-id="d668b-122">**Skype for Business Online con ibridi** Gli ambienti ibridi possono includere utenti che rientrano in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d668b-122">**Skype for Business Online with hybrid** Hybrid environments may have users that fall into one of the following categories:</span></span>

  - <span data-ttu-id="d668b-123">Utenti locali ospitati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d668b-123">On-premises users homed on Skype for Business Server</span></span>
  - <span data-ttu-id="d668b-124">Skype for Business Utenti online che si Teams modalità Solo utenti</span><span class="sxs-lookup"><span data-stu-id="d668b-124">Skype for Business Online users that are in Teams Only mode</span></span>
  - <span data-ttu-id="d668b-125">Skype for Business Utenti online che non **sono** in Teams solo utenti</span><span class="sxs-lookup"><span data-stu-id="d668b-125">Skype for Business Online users that are **not** in Teams Only mode</span></span>

  <span data-ttu-id="d668b-126">Se si ha una combinazione di utenti in ognuna delle categorie elencate sopra, il processo di aggiornamento assistito passa solo agli utenti di Skype for Business Online alla modalità Solo Teams se non sono già in quella modalità.</span><span class="sxs-lookup"><span data-stu-id="d668b-126">If you have a mixture of users in each of the categories listed above, the assisted upgrade process will only switch Skype for Business Online users to Teams Only mode if they're not already in that mode.</span></span> <span data-ttu-id="d668b-127">Gli utenti Skype for Business locali non saranno influenzati dal processo di aggiornamento assistito.</span><span class="sxs-lookup"><span data-stu-id="d668b-127">On-premises Skype for Business users won't be impacted by the assisted upgrade process.</span></span>

> [!NOTE]
> <span data-ttu-id="d668b-128">Non preoccuparti se l'aggiornamento assistito è pianificato per una data successiva al 31 luglio 2021.</span><span class="sxs-lookup"><span data-stu-id="d668b-128">Don't worry if your assisted upgrade is scheduled for a date after July 31, 2021.</span></span> <span data-ttu-id="d668b-129">L'organizzazione sarà in grado di usare Skype for Business Online fino al completamento dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d668b-129">Your organization will be able to use Skype for Business Online until your upgrade is complete.</span></span>

<span data-ttu-id="d668b-130">La durata dell'aggiornamento varia in base al volume di utenti e alle caratteristiche della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d668b-130">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="d668b-131">Nella maggior parte dei casi, gli utenti all'interno di un tenant verranno aggiornati entro 24 ore dall'inizio dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d668b-131">In most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="d668b-132">Durante questo periodo, gli utenti finali avranno ancora accesso Skype for Business funzionalità online.</span><span class="sxs-lookup"><span data-stu-id="d668b-132">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="d668b-133">Una volta completato l'aggiornamento e gli utenti si disconnennendono da Skype for Business Online, inizieranno a usare Teams messaggistica, riunioni e chiamate.</span><span class="sxs-lookup"><span data-stu-id="d668b-133">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="d668b-134">Esperienza post-aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d668b-134">The post-upgrade experience</span></span>

<span data-ttu-id="d668b-135">Al termine dell'aggiornamento assistito, la **modalità di coesistenza** per gli utenti aggiornati è impostata su Solo Teams versione.</span><span class="sxs-lookup"><span data-stu-id="d668b-135">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only.</span></span> <span data-ttu-id="d668b-136">È consigliabile rivedere le considerazioni [Teams modalità Solo prima](teams-only-mode-considerations.md) dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d668b-136">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="d668b-137">La tabella seguente fornisce una panoramica generale dell'esperienza Teams solo per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d668b-137">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="d668b-138">**Chat e chiamate**</span><span class="sxs-lookup"><span data-stu-id="d668b-138">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="d668b-139">Tutte le chiamate e le chat vengono avviate e ricevute in Teams</span><span class="sxs-lookup"><span data-stu-id="d668b-139">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="d668b-140">Gli utenti possono comunicare (chat/chiamata) con qualsiasi Skype for Business utente</span><span class="sxs-lookup"><span data-stu-id="d668b-140">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="d668b-141">Le organizzazioni possono consentire agli Teams utenti di comunicare con gli utenti del servizio Skype consumer gestendo [le autorizzazioni di accesso esterno](manage-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="d668b-141">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="d668b-142">Teams utenti che provano ad accedere a Skype for Business Online vengono reindirizzati a Teams</span><span class="sxs-lookup"><span data-stu-id="d668b-142">Teams users who attempt to sign in to Skype for Business Online are redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="d668b-143">**Riunioni**</span><span class="sxs-lookup"><span data-stu-id="d668b-143">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="d668b-144">Gli utenti pianificano tutte le nuove riunioni in Teams (plug-in sostituito)</span><span class="sxs-lookup"><span data-stu-id="d668b-144">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="d668b-145">**Dati migrati**</span><span class="sxs-lookup"><span data-stu-id="d668b-145">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="d668b-146">Contatti esistenti di Skype for Business Online, inclusi federati (ma non liste di distribuzione)</span><span class="sxs-lookup"><span data-stu-id="d668b-146">Existing contacts from Skype for Business Online including federated (but no distribution lists)</span></span>
        - <span data-ttu-id="d668b-147">La migrazione dei contatti viene eseguita quando gli utenti a Teams per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="d668b-147">Contacts are migrated when users log into Teams for the first time.</span></span>
            > [!IMPORTANT]
            ><span data-ttu-id="d668b-148">La migrazione dei contatti deve essere eseguita entro 90 giorni dal completamento dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d668b-148">Contacts must be migrated within 90 days of the completion of your upgrade.</span></span>
        - <span data-ttu-id="d668b-149">Le Skype for Business online esistenti vengono convertite in Teams riunioni</span><span class="sxs-lookup"><span data-stu-id="d668b-149">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
            > [!IMPORTANT]
            > <span data-ttu-id="d668b-150">I clienti con configurazioni Skype for Business online devono usare il servizio di migrazione delle riunioni (MMS) per eseguire la migrazione delle riunioni Skype for Business Online esistenti a Teams riunioni.</span><span class="sxs-lookup"><span data-stu-id="d668b-150">Customers with pure Skype for Business Online configurations need to use the Meeting Migration Service (MMS) to migrate existing Skype for Business Online meetings to Teams meetings.</span></span> <span data-ttu-id="d668b-151">È consigliabile usare MMS prima della data di aggiornamento assistito.</span><span class="sxs-lookup"><span data-stu-id="d668b-151">We recommend using MMS prior to the assisted upgrade date.</span></span> <span data-ttu-id="d668b-152">Per altre informazioni su MMS, vedere Uso del servizio di [migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="d668b-152">For more information about MMS, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span></span>
    :::column-end:::
:::row-end:::

<span data-ttu-id="d668b-153">Al termine dell'aggiornamento, le organizzazioni con distribuzioni ibride possono spostare gli utenti dalla versione locale a Teams o spostarsi da Teams a locale.</span><span class="sxs-lookup"><span data-stu-id="d668b-153">After your upgrade is complete, organizations with hybrid deployments may move users from on-premises to Teams or moved from Teams to on-premises.</span></span>  

## <a name="related-content"></a><span data-ttu-id="d668b-154">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="d668b-154">Related content</span></span>

- [<span data-ttu-id="d668b-155">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d668b-155">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="d668b-156">Ritiro di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d668b-156">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="d668b-157">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="d668b-157">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="d668b-158">Teams Considerazioni solo sulla modalità</span><span class="sxs-lookup"><span data-stu-id="d668b-158">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
