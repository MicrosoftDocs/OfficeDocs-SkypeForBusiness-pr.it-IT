---
title: Configurare le impostazioni degli eventi dinamici in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come gestire le impostazioni per gli eventi di teams Live che si svolgono nell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b87c891d29bcfafa0275f3a500eb8c5db85311a0
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962857"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="14559-103">Configurare le impostazioni degli eventi dinamici in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14559-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="14559-104">Usa le impostazioni eventi di teams Live per configurare le impostazioni per gli eventi dinamici che si svolgono nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14559-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="14559-105">È possibile impostare un URL di supporto e configurare un provider di distribuzione video di terze parti.</span><span class="sxs-lookup"><span data-stu-id="14559-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="14559-106">Queste impostazioni si applicano a tutti gli eventi dinamici creati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14559-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="14559-107">Puoi gestire facilmente queste impostazioni nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="14559-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="14559-108">Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Impostazioni eventi live**riunioni.</span><span class="sxs-lookup"><span data-stu-id="14559-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="14559-109">![Schermata delle impostazioni di eventi live di Teams](../media/teams-live-events-settings.png "Screenshot delle impostazioni di eventi live di teams che è possibile configurare nell'interfaccia di amministrazione di Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="14559-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="14559-110">URL del supporto per la configurazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="14559-110">Set up event support URL</span></span>

<span data-ttu-id="14559-111">Questo URL viene visualizzato nei partecipanti agli eventi dinamici.</span><span class="sxs-lookup"><span data-stu-id="14559-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="14559-112">Aggiungere l'URL del supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento dinamico.</span><span class="sxs-lookup"><span data-stu-id="14559-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="14559-114">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14559-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="14559-115">Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Impostazioni eventi live**riunioni.</span><span class="sxs-lookup"><span data-stu-id="14559-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="14559-116">In **URL di supporto**immettere l'URL di supporto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14559-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="14559-117">![Impostazione dell'URL del supporto per eventi dinamici nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png "Screenshot dell'impostazione dell'URL del supporto per gli eventi live di Teams")</span><span class="sxs-lookup"><span data-stu-id="14559-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="14559-118">Uso di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14559-118">Using Windows PowerShell</span></span>

<span data-ttu-id="14559-119">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="14559-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="14559-120">Per altre informazioni, vedere [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14559-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="14559-121">Configurare un provider di distribuzione video di terze parti</span><span class="sxs-lookup"><span data-stu-id="14559-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="14559-122">Se è stata acquistata e configurata una soluzione software defined Network (SDN) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner di recapito video Microsoft, configurare il provider per gli eventi dinamici in teams.</span><span class="sxs-lookup"><span data-stu-id="14559-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="14559-124">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14559-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="14559-125">Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Impostazioni eventi live**riunioni.</span><span class="sxs-lookup"><span data-stu-id="14559-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="14559-126">In **provider di distribuzione video di terze parti**completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="14559-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="14559-127">![Impostazioni del provider di distribuzione video di terze parti nell'interfaccia di amministrazione](../media/teams-live-events-settings-distribution-provider.png "Screenshot delle impostazioni del provider di distribuzione video di terze parti per eventi dinamici")</span><span class="sxs-lookup"><span data-stu-id="14559-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="14559-128">**Usare un provider di distribuzione di terze parti** Attivare questa opzione per abilitare il provider di distribuzione video di terze parti.</span><span class="sxs-lookup"><span data-stu-id="14559-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="14559-129">**Nome provider Sdn** Scegliere il provider che si sta usando.</span><span class="sxs-lookup"><span data-stu-id="14559-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="14559-130">**Codice di licenza del provider** Immettere l'ID licenza ottenuto dal contatto del provider.</span><span class="sxs-lookup"><span data-stu-id="14559-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="14559-131">**URL del modello dell'API Sdn** Immettere l'URL del modello di API ottenuto dal contatto del provider.</span><span class="sxs-lookup"><span data-stu-id="14559-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="14559-132">Uso di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14559-132">Using Windows PowerShell</span></span>
<span data-ttu-id="14559-133">Ottenere l'ID licenza o il token API e il modello di API dal contatto del provider e quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:</span><span class="sxs-lookup"><span data-stu-id="14559-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="14559-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="14559-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="14559-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="14559-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="14559-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="14559-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="14559-137">Per altre informazioni, vedere [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14559-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="14559-138">Se si prevede di creare eventi dinamici usando un'app o un dispositivo esterno, è necessario configurare anche [il provider di eCDN con Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="14559-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="14559-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="14559-139">Related topics</span></span>
- [<span data-ttu-id="14559-140">Cosa sono gli eventi live di Teams?</span><span class="sxs-lookup"><span data-stu-id="14559-140">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="14559-141">Pianificare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="14559-141">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="14559-142">Configurare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="14559-142">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)