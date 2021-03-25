---
title: Configurare le impostazioni degli eventi live in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Informazioni su come gestire le impostazioni per gli eventi live di Teams che si svolgono nell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5f19aa6cfee7d4cce19ef5a0936a5a72e954648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119345"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="fcf93-103">Configurare le impostazioni degli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcf93-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="fcf93-104">Usare le impostazioni degli eventi live di Teams per configurare le impostazioni per gli eventi live che si svolgono nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fcf93-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="fcf93-105">È possibile configurare un URL di supporto e un provider di distribuzione video di terze parti.</span><span class="sxs-lookup"><span data-stu-id="fcf93-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="fcf93-106">Queste impostazioni si applicano a tutti gli eventi live creati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fcf93-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="fcf93-107">È possibile gestire facilmente queste impostazioni nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf93-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fcf93-108">Nel riquadro di spostamento sinistro passare a **Impostazioni eventi**  >  **live riunioni.**</span><span class="sxs-lookup"><span data-stu-id="fcf93-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="fcf93-109">![Schermata delle impostazioni degli eventi live di Teams](../media/teams-live-events-settings.png "Schermata delle impostazioni degli eventi live di Teams che è possibile configurare nell'interfaccia di amministrazione di Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="fcf93-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="fcf93-110">Configurare l'URL di supporto per gli eventi</span><span class="sxs-lookup"><span data-stu-id="fcf93-110">Set up event support URL</span></span>

<span data-ttu-id="fcf93-111">Questo URL viene visualizzato per i partecipanti all'evento live.</span><span class="sxs-lookup"><span data-stu-id="fcf93-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="fcf93-112">Aggiungere l'URL di supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento live.</span><span class="sxs-lookup"><span data-stu-id="fcf93-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="fcf93-114">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf93-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fcf93-115">Nel riquadro di spostamento sinistro passare a **Impostazioni evento live**  >  **riunioni.**</span><span class="sxs-lookup"><span data-stu-id="fcf93-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="fcf93-116">In **URL supporto** immettere l'URL di supporto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fcf93-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="fcf93-117">![Impostazione dell'URL di supporto per gli eventi live nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png "Schermata dell'impostazione dell'URL di supporto per gli eventi live di Teams")</span><span class="sxs-lookup"><span data-stu-id="fcf93-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="fcf93-118">Uso di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcf93-118">Using Windows PowerShell</span></span>

<span data-ttu-id="fcf93-119">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="fcf93-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="fcf93-120">Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fcf93-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="fcf93-121">Configurare un provider di distribuzione video di terze parti</span><span class="sxs-lookup"><span data-stu-id="fcf93-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="fcf93-122">Se è stata acquistata e configurata una soluzione SDN (Software Defined Network) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner microsoft per la distribuzione di video, configurare il provider per gli eventi live in Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf93-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="fcf93-124">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf93-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fcf93-125">Nel riquadro di spostamento sinistro passare a **Impostazioni evento live**  >  **riunioni.**</span><span class="sxs-lookup"><span data-stu-id="fcf93-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="fcf93-126">In **Provider di distribuzione video di terze parti** completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fcf93-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="fcf93-127">![Impostazioni del provider di distribuzione video di terze parti nell'interfaccia di amministrazione](../media/teams-live-events-settings-distribution-provider.png "Schermata delle impostazioni del provider di distribuzione video di terze parti per gli eventi live")</span><span class="sxs-lookup"><span data-stu-id="fcf93-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="fcf93-128">**Usare un provider di distribuzione di terze parti** Attivare questa opzione per abilitare il provider di distribuzione video di terze parti.</span><span class="sxs-lookup"><span data-stu-id="fcf93-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="fcf93-129">**Nome provider SDN** Scegliere il provider in uso.</span><span class="sxs-lookup"><span data-stu-id="fcf93-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="fcf93-130">**Codice di licenza del provider** Immettere l'ID licenza ottenuto dal contatto del provider.</span><span class="sxs-lookup"><span data-stu-id="fcf93-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="fcf93-131">**URL modello API SDN** Immettere l'URL del modello API ottenuto dal contatto del provider.</span><span class="sxs-lookup"><span data-stu-id="fcf93-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="fcf93-132">Uso di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcf93-132">Using Windows PowerShell</span></span>
<span data-ttu-id="fcf93-133">Ottenere l'ID licenza o il token API e il modello API dal contatto del provider e quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:</span><span class="sxs-lookup"><span data-stu-id="fcf93-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="fcf93-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="fcf93-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="fcf93-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="fcf93-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="fcf93-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="fcf93-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="fcf93-137">Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fcf93-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="fcf93-138">Se si prevede di creare eventi live con un'app o un dispositivo esterno, sarà necessario configurare anche il [provider eCDN con Microsoft Stream.](/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="fcf93-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="fcf93-p104">Il passaggio dall'utilizzo di Microsoft Stream a [ OneDrive for Business e SharePoint per le registrazioni delle riunioni ](../tmr-meeting-recording-change.md) sarà graduale. Al momento del lancio sarà possibile acconsentire esplicitamente all’esperienza. A novembre sarà necessario rifiutarla esplicitamente se si vuole continuare a usare Stream e all'inizio del 2021 sarà chiesto a tutti i clienti di usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="fcf93-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="related-topics"></a><span data-ttu-id="fcf93-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fcf93-141">Related topics</span></span>
- [<span data-ttu-id="fcf93-142">Cosa sono gli eventi live di Teams?</span><span class="sxs-lookup"><span data-stu-id="fcf93-142">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="fcf93-143">Pianificare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="fcf93-143">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="fcf93-144">Configurare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="fcf93-144">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)