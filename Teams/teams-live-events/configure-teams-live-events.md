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
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurare le impostazioni degli eventi live in Microsoft Teams

Usare Teams eventi live per configurare le impostazioni per gli eventi live che si svolgono nell'organizzazione. È possibile configurare un URL di supporto e un provider di distribuzione video di terze parti. Queste impostazioni si applicano a tutti gli eventi live creati nell'organizzazione.

È possibile gestire facilmente queste impostazioni nell'Microsoft Teams di amministrazione. Nel riquadro di spostamento sinistro passare a **Impostazioni eventi**  >  **live riunioni.**

![Schermata delle impostazioni Teams eventi live](../media/teams-live-events-settings.png "Schermata delle impostazioni Teams eventi live che è possibile configurare nell'interfaccia Microsoft Teams di amministrazione")

## <a name="set-up-event-support-url"></a>Configurare l'URL di supporto per gli eventi

Questo URL viene visualizzato per i partecipanti all'evento live. Aggiungere l'URL di supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento live.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Impostazioni evento live**  >  **riunioni.**
2. In **URL supporto** immettere l'URL di supporto dell'organizzazione.

    ![Impostazione dell'URL di supporto per gli eventi live nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png "Schermata dell'impostazione dell'URL di supporto per Teams eventi live")

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell

Esegui il seguente comando:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurare un provider di distribuzione video di terze parti 

Se è stata acquistata e configurata una soluzione SDN (Software Defined Network) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner microsoft per la distribuzione di video, configurare il provider per gli eventi live in Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Impostazioni evento live**  >  **riunioni.**
2. In **Provider di distribuzione video di terze parti** completare le operazioni seguenti: 

    ![Impostazioni del provider di distribuzione video di terze parti nell'interfaccia di amministrazione](../media/teams-live-events-settings-distribution-provider.png "Schermata delle impostazioni del provider di distribuzione video di terze parti per gli eventi live")

    - **Usare un provider di distribuzione di terze parti** Attivare questa opzione per abilitare il provider di distribuzione video di terze parti.
    - **Nome provider SDN** Scegliere il provider in uso.
    - **Codice di licenza del provider** Immettere l'ID licenza ottenuto dal contatto del provider.
    - **URL modello API SDN** Immettere l'URL del modello API ottenuto dal contatto del provider.

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell
Ottenere l'ID licenza o il token API e il modello API dal contatto del provider e quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Se si prevede di creare eventi live con un'app o un dispositivo esterno, sarà necessario configurare anche il [provider eCDN con Microsoft Stream.](/stream/network-caching) 

>[!Note]
> Il passaggio dall'utilizzo di Microsoft Stream a [ OneDrive for Business e SharePoint per le registrazioni delle riunioni ](../tmr-meeting-recording-change.md) sarà graduale. Al momento del lancio sarà possibile acconsentire esplicitamente all’esperienza. A novembre sarà necessario rifiutarla esplicitamente se si vuole continuare a usare Stream e all'inizio del 2021 sarà chiesto a tutti i clienti di usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.

>[!Note]
> La soluzione eCDN scelta è soggetta alle condizioni di servizio e all'informativa sulla privacy del provider di terze parti selezionato, che regolano l'uso della soluzione del provider eCDN. L'uso della soluzione del provider eCDN non sarà soggetto alle condizioni per i contratti multilicenza Microsoft o ai Termini dei Servizi online. Se non si accettano le condizioni del provider di terze parti, non abilitare la soluzione eCDN in Microsoft Teams.

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
