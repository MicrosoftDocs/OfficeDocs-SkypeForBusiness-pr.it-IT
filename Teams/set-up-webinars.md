---
title: Configurare i webinar in Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Informazioni su come gestire i criteri webinar per Teams riunioni.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926748"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="a65e4-103">Configurare i webinar in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a65e4-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="a65e4-104">Questo articolo illustra come configurare l'organizzazione per ospitare webinar.</span><span class="sxs-lookup"><span data-stu-id="a65e4-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="a65e4-105">Che cosa sono i webinar?</span><span class="sxs-lookup"><span data-stu-id="a65e4-105">What are webinars?</span></span>

<span data-ttu-id="a65e4-106">I webinar sono riunioni strutturate in cui relatori e partecipanti hanno ruoli chiari, spesso usati per scopi di formazione o scenari di creazione di lead generation per vendite e marketing.</span><span class="sxs-lookup"><span data-stu-id="a65e4-106">Webinars are structured meetings where presenters and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="a65e4-107">Dopo aver impostato webinar nell'organizzazione, gli utenti possono pianificare webinar e aprire la registrazione ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="a65e4-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="a65e4-108">A differenza delle riunioni tradizionali che includono molte discussioni e attività, i webinar sono pensati per presentazioni interattive e forniscono strumenti per l'analisi dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="a65e4-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="a65e4-109">Consentire agli utenti di pianificare webinar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65e4-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="a65e4-110">È possibile usare gli attributi seguenti all'interno Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** per configurare i webinar in Teams.</span><span class="sxs-lookup"><span data-stu-id="a65e4-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="a65e4-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="a65e4-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="a65e4-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="a65e4-112">WhoCanRegister</span></span>
- <span data-ttu-id="a65e4-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="a65e4-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="a65e4-114">Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="a65e4-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a65e4-115">Prima di eseguire questi cmdlet, è necessario essere connessi a Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a65e4-115">Before you can run these cmdlets you must be connected to Microsoft Teams PowerShell.</span></span> <span data-ttu-id="a65e4-116">Per altre informazioni, vedere [Gestire Teams con Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)</span><span class="sxs-lookup"><span data-stu-id="a65e4-116">For more information, see [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="a65e4-117">Consentire agli utenti di pianificare webinar</span><span class="sxs-lookup"><span data-stu-id="a65e4-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="a65e4-118">È possibile limitare la registrazione solo agli utenti dell'organizzazione o aprirla a tutti gli utenti interni ed esterni al tenant.</span><span class="sxs-lookup"><span data-stu-id="a65e4-118">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="a65e4-119">Per impostazione predefinita, **WhoCanRegister** è abilitato e impostato su **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="a65e4-119">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="a65e4-120">Se si vuole disattivare la registrazione della riunione, impostare **AllowMeetingRegistration** su **False**.</span><span class="sxs-lookup"><span data-stu-id="a65e4-120">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a65e4-121">**AllowPrivateMeetingScheduling** deve essere impostato su **True** perché **AllowMeetingRegistration** funzioni.</span><span class="sxs-lookup"><span data-stu-id="a65e4-121">**AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="a65e4-122">Inoltre, gli elenchi Microsoft devono essere impostati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a65e4-122">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="a65e4-123">Per altre informazioni, vedere [Impostazioni di controllo per Elenchi Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="a65e4-123">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

1. <span data-ttu-id="a65e4-124">Attivare la registrazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="a65e4-124">Turn on meeting registration</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. <span data-ttu-id="a65e4-125">Attivare la pianificazione privata delle riunioni</span><span class="sxs-lookup"><span data-stu-id="a65e4-125">Turn on private meeting scheduling</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. <span data-ttu-id="a65e4-126">Configurare gli utenti che possono registrarsi per i webinar</span><span class="sxs-lookup"><span data-stu-id="a65e4-126">Configure who can register for webinars</span></span>

<span data-ttu-id="a65e4-127">**Consentire *solo agli* utenti dell'organizzazione di registrarsi per i webinar**</span><span class="sxs-lookup"><span data-stu-id="a65e4-127">**Allow *only* users in your organization to register for webinars**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="a65e4-128">**Per consentire a chiunque, inclusi gli utenti anonimi, di registrarsi per i webinar, eseguire:**</span><span class="sxs-lookup"><span data-stu-id="a65e4-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> <span data-ttu-id="a65e4-129">Se l'accesso anonimo è disattivato nelle impostazioni della riunione, gli utenti anonimi non possono partecipare ai webinar.</span><span class="sxs-lookup"><span data-stu-id="a65e4-129">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="a65e4-130">Per altre informazioni e abilitare questa impostazione, vedere [Impostazioni riunione in Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a65e4-130">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="a65e4-131">Raccogliere la partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="a65e4-131">Collect meeting attendance</span></span>

<span data-ttu-id="a65e4-132">Se si vuole che gli organizzatori analizzino chi ha registrato e partecipato ai webinar, è necessario attivare il criterio **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="a65e4-132">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="a65e4-133">A questo scopo, eseguire il comando seguente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a65e4-133">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="a65e4-134">Configurare le impostazioni del webinar</span><span class="sxs-lookup"><span data-stu-id="a65e4-134">Configure webinar settings</span></span>

<span data-ttu-id="a65e4-135">Dopo aver abilitato l'ambiente per i webinar, non è necessaria alcuna ulteriore gestione dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a65e4-135">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="a65e4-136">I criteri controllano le opzioni da visualizzare per gli organizzatori del webinar.</span><span class="sxs-lookup"><span data-stu-id="a65e4-136">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a65e4-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a65e4-137">Related topics</span></span>

- [<span data-ttu-id="a65e4-138">Criteri riunione in Teams - Generale</span><span class="sxs-lookup"><span data-stu-id="a65e4-138">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="a65e4-139">Documentazione di Set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a65e4-139">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
