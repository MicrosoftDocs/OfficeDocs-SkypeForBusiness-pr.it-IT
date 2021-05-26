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
ms.openlocfilehash: bc1460f93259a9dd3095cf764c38b56ab703bba0
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656049"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="481b1-103">Configurare i webinar in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="481b1-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="481b1-104">Questo articolo illustra come configurare l'organizzazione per ospitare webinar.</span><span class="sxs-lookup"><span data-stu-id="481b1-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="481b1-105">Che cosa sono i webinar?</span><span class="sxs-lookup"><span data-stu-id="481b1-105">What are webinars?</span></span>

<span data-ttu-id="481b1-106">I webinar sono riunioni strutturate in cui istruttori e partecipanti hanno ruoli chiari, spesso usati per scopi di formazione o scenari di creazione di lead generation di vendite e marketing.</span><span class="sxs-lookup"><span data-stu-id="481b1-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="481b1-107">Dopo aver impostato webinar nell'organizzazione, gli utenti possono pianificare webinar e aprire la registrazione ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="481b1-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="481b1-108">A differenza delle riunioni tradizionali che includono molte discussioni e attività, i webinar sono pensati per presentazioni interattive e forniscono strumenti per l'analisi dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="481b1-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="481b1-109">Consentire agli utenti di pianificare webinar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="481b1-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="481b1-110">È possibile usare gli attributi seguenti all'interno Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** per configurare i webinar in Teams.</span><span class="sxs-lookup"><span data-stu-id="481b1-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="481b1-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="481b1-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="481b1-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="481b1-112">WhoCanRegister</span></span>
- <span data-ttu-id="481b1-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="481b1-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="481b1-114">Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="481b1-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="481b1-115">Prima di eseguire questi cmdlet, è necessario essere connessi Skype for Business PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="481b1-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="481b1-116">Per altre informazioni, vedere [Gestire Skype for Business Online con Microsoft 365 o Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="481b1-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="481b1-117">Consentire agli utenti di pianificare webinar</span><span class="sxs-lookup"><span data-stu-id="481b1-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="481b1-118">Per consentire agli utenti dell'organizzazione di pianificare webinar, eseguire:</span><span class="sxs-lookup"><span data-stu-id="481b1-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="481b1-119">Configurare gli utenti che possono registrarsi per i webinar</span><span class="sxs-lookup"><span data-stu-id="481b1-119">Configure who can register for webinars</span></span>

<span data-ttu-id="481b1-120">È possibile limitare la registrazione solo agli utenti dell'organizzazione o aprirla a tutti gli utenti interni ed esterni al tenant.</span><span class="sxs-lookup"><span data-stu-id="481b1-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="481b1-121">Per impostazione predefinita, **WhoCanRegister** è abilitato e impostato su **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="481b1-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="481b1-122">Se si vuole disattivare la registrazione della riunione, impostare **AllowMeetingRegistration** su **False**.</span><span class="sxs-lookup"><span data-stu-id="481b1-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="481b1-123">Tenere presente che **AllowPrivateMeetingScheduling** deve essere impostato su **True** per consentire il funzionamento di **AllowMeetingRegistration.**</span><span class="sxs-lookup"><span data-stu-id="481b1-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="481b1-124">Inoltre, gli elenchi Microsoft devono essere impostati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="481b1-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="481b1-125">Per altre informazioni, vedere [Impostazioni di controllo per Elenchi Microsoft.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="481b1-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="481b1-126">**Per consentire *solo agli* utenti dell'organizzazione di registrarsi per i webinar, eseguire:**</span><span class="sxs-lookup"><span data-stu-id="481b1-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

<span data-ttu-id="481b1-127">Quindi, esegui:</span><span class="sxs-lookup"><span data-stu-id="481b1-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="481b1-128">**Per consentire a chiunque, inclusi gli utenti anonimi, di registrarsi per i webinar, eseguire:**</span><span class="sxs-lookup"><span data-stu-id="481b1-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

<span data-ttu-id="481b1-129">Quindi, esegui:</span><span class="sxs-lookup"><span data-stu-id="481b1-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="481b1-130">Se l'accesso anonimo è disattivato nelle impostazioni della riunione, gli utenti anonimi non possono partecipare ai webinar.</span><span class="sxs-lookup"><span data-stu-id="481b1-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="481b1-131">Per altre informazioni e abilitare questa impostazione, vedere [Impostazioni riunione in Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="481b1-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="481b1-132">Raccogliere la partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="481b1-132">Collect meeting attendance</span></span>

<span data-ttu-id="481b1-133">Se si vuole che gli organizzatori analizzino chi ha registrato e partecipato ai webinar, è necessario attivare il criterio **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="481b1-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="481b1-134">A questo scopo, eseguire il comando seguente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="481b1-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="481b1-135">Configurare le impostazioni del webinar</span><span class="sxs-lookup"><span data-stu-id="481b1-135">Configure webinar settings</span></span>

<span data-ttu-id="481b1-136">Dopo aver abilitato l'ambiente per i webinar, non è necessaria alcuna ulteriore gestione dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="481b1-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="481b1-137">I criteri controllano le opzioni da visualizzare per gli organizzatori del webinar.</span><span class="sxs-lookup"><span data-stu-id="481b1-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="481b1-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="481b1-138">Related topics</span></span>

- [<span data-ttu-id="481b1-139">Criteri riunione in Teams - Generale</span><span class="sxs-lookup"><span data-stu-id="481b1-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="481b1-140">Documentazione di Set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="481b1-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
