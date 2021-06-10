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
description: Informazioni su come gestire le impostazioni Teams eventi live che si svolgono nell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9749484344d969671e8a0195de3386a57388d275
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637878"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="9d06f-103">Configurare le impostazioni degli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d06f-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="9d06f-104">Usare Teams eventi live per configurare le impostazioni per gli eventi live che si svolgono nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d06f-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="9d06f-105">È possibile configurare un URL di supporto e un provider di distribuzione video di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9d06f-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="9d06f-106">Queste impostazioni si applicano a tutti gli eventi live creati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d06f-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="9d06f-107">È possibile gestire facilmente queste impostazioni nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="9d06f-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9d06f-108">Nel riquadro di spostamento sinistro passare a **Impostazioni eventi**  >  **live riunioni.**</span><span class="sxs-lookup"><span data-stu-id="9d06f-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="9d06f-109">![Schermata delle impostazioni Teams eventi live](../media/teams-live-events-settings.png "Schermata delle impostazioni Teams eventi live che è possibile configurare nell'interfaccia Microsoft Teams di amministrazione")</span><span class="sxs-lookup"><span data-stu-id="9d06f-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="9d06f-110">Configurare l'URL di supporto per gli eventi</span><span class="sxs-lookup"><span data-stu-id="9d06f-110">Set up event support URL</span></span>

<span data-ttu-id="9d06f-111">Questo URL viene visualizzato per i partecipanti all'evento live.</span><span class="sxs-lookup"><span data-stu-id="9d06f-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="9d06f-112">Aggiungere l'URL di supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento live.</span><span class="sxs-lookup"><span data-stu-id="9d06f-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="9d06f-114&quot;>Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9d06f-114&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;9d06f-115&quot;>Nel riquadro di spostamento sinistro passare a **Impostazioni evento live**  >  **riunioni.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9d06f-115&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;9d06f-116&quot;>In **URL supporto** immettere l'URL di supporto dell'organizzazione.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9d06f-116&quot;>Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id=&quot;9d06f-117&quot;>![Impostazione dell'URL di supporto per gli eventi live nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png &quot;Schermata dell'impostazione dell'URL di supporto per Teams eventi live")</span><span class="sxs-lookup"><span data-stu-id="9d06f-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="9d06f-118">Uso di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d06f-118">Using Windows PowerShell</span></span>

<span data-ttu-id="9d06f-119">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="9d06f-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="9d06f-120">Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9d06f-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="9d06f-121">Configurare un provider di distribuzione video di terze parti</span><span class="sxs-lookup"><span data-stu-id="9d06f-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="9d06f-122">Se è stata acquistata e configurata una soluzione SDN (Software Defined Network) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner microsoft per la distribuzione di video, configurare il provider per gli eventi live in Teams.</span><span class="sxs-lookup"><span data-stu-id="9d06f-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="9d06f-124&quot;>Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9d06f-124&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;9d06f-125&quot;>Nel riquadro di spostamento sinistro passare a **Impostazioni evento live**  >  **riunioni.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9d06f-125&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;9d06f-126&quot;>In **Provider di distribuzione video di terze parti** completare le operazioni seguenti:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9d06f-126&quot;>Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id=&quot;9d06f-127&quot;>![Impostazioni del provider di distribuzione video di terze parti nell'interfaccia di amministrazione](../media/teams-live-events-settings-distribution-provider.png &quot;Schermata delle impostazioni del provider di distribuzione video di terze parti per gli eventi live")</span><span class="sxs-lookup"><span data-stu-id="9d06f-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="9d06f-128">**Usare un provider di distribuzione di terze parti** Attivare questa opzione per abilitare il provider di distribuzione video di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9d06f-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="9d06f-129">**Nome provider SDN** Scegliere il provider in uso.</span><span class="sxs-lookup"><span data-stu-id="9d06f-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="9d06f-130">**Codice di licenza del provider** Immettere l'ID licenza ottenuto dal contatto del provider.</span><span class="sxs-lookup"><span data-stu-id="9d06f-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="9d06f-131">**URL modello API SDN** Immettere l'URL del modello API ottenuto dal contatto del provider.</span><span class="sxs-lookup"><span data-stu-id="9d06f-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="9d06f-132">Uso di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d06f-132">Using Windows PowerShell</span></span>
<span data-ttu-id="9d06f-133">Ottenere l'ID licenza o il token API e il modello API dal contatto del provider e quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:</span><span class="sxs-lookup"><span data-stu-id="9d06f-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="9d06f-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="9d06f-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="9d06f-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="9d06f-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="9d06f-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="9d06f-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
<span data-ttu-id="9d06f-137">**Ramp**</span><span class="sxs-lookup"><span data-stu-id="9d06f-137">**Ramp**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

<span data-ttu-id="9d06f-138">Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9d06f-138">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="9d06f-139">Se si prevede di creare eventi live con un'app o un dispositivo esterno, sarà necessario configurare anche il [provider eCDN con Microsoft Stream.](/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="9d06f-139">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="9d06f-p104">Il passaggio dall'utilizzo di Microsoft Stream a [ OneDrive for Business e SharePoint per le registrazioni delle riunioni ](../tmr-meeting-recording-change.md) sarà graduale. Al momento del lancio sarà possibile acconsentire esplicitamente all’esperienza. A novembre sarà necessario rifiutarla esplicitamente se si vuole continuare a usare Stream e all'inizio del 2021 sarà chiesto a tutti i clienti di usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9d06f-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

>[!Note]
> <span data-ttu-id="9d06f-142">La soluzione eCDN scelta è soggetta alle condizioni di servizio e all'informativa sulla privacy del provider di terze parti selezionato, che regolano l'uso della soluzione del provider eCDN.</span><span class="sxs-lookup"><span data-stu-id="9d06f-142">Your chosen eCDN solution is subject to the selected 3rd party provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="9d06f-143">L'uso della soluzione del provider eCDN non sarà soggetto alle condizioni per i contratti multilicenza Microsoft o ai Termini dei Servizi online.</span><span class="sxs-lookup"><span data-stu-id="9d06f-143">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="9d06f-144">Se non si accettano le condizioni del provider di terze parti, non abilitare la soluzione eCDN in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d06f-144">If you don't agree to the 3rd party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.</span></span>

### <a name="related-topics"></a><span data-ttu-id="9d06f-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9d06f-145">Related topics</span></span>
- [<span data-ttu-id="9d06f-146">Cosa sono gli eventi live di Teams?</span><span class="sxs-lookup"><span data-stu-id="9d06f-146">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="9d06f-147">Pianificare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="9d06f-147">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="9d06f-148">Configurare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="9d06f-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
