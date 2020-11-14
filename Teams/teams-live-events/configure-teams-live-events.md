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
- m365initiative-meetings
description: Informazioni su come gestire le impostazioni per gli eventi di teams Live che si svolgono nell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: afbcd90db9a17f509076bae1271bf541dfb93fd4
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030892"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurare le impostazioni degli eventi dinamici in Microsoft Teams

Usa le impostazioni eventi di teams Live per configurare le impostazioni per gli eventi dinamici che si svolgono nell'organizzazione. È possibile impostare un URL di supporto e configurare un provider di distribuzione video di terze parti. Queste impostazioni si applicano a tutti gli eventi dinamici creati nell'organizzazione.

Puoi gestire facilmente queste impostazioni nell'interfaccia di amministrazione di Microsoft teams. Nella barra di spostamento sinistra, Vai **Meetings** a  >  **Impostazioni eventi live** riunioni.

![Schermata delle impostazioni di eventi live di Teams](../media/teams-live-events-settings.png "Screenshot delle impostazioni di eventi live di teams che è possibile configurare nell'interfaccia di amministrazione di Microsoft Teams")

## <a name="set-up-event-support-url"></a>URL del supporto per la configurazione dell'evento

Questo URL viene visualizzato nei partecipanti agli eventi dinamici. Aggiungere l'URL del supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento dinamico.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra, Vai **Meetings** a  >  **Impostazioni eventi live** riunioni.
2. In **URL di supporto** immettere l'URL di supporto dell'organizzazione.

    ![Impostazione dell'URL del supporto per eventi dinamici nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png "Screenshot dell'impostazione dell'URL del supporto per gli eventi live di Teams")

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell

Esegui il seguente comando:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Per altre informazioni, vedere [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurare un provider di distribuzione video di terze parti 

Se è stata acquistata e configurata una soluzione software defined Network (SDN) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner di recapito video Microsoft, configurare il provider per gli eventi dinamici in teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra, Vai **Meetings** a  >  **Impostazioni eventi live** riunioni.
2. In **provider di distribuzione video di terze parti** completare le operazioni seguenti: 

    ![Impostazioni del provider di distribuzione video di terze parti nell'interfaccia di amministrazione](../media/teams-live-events-settings-distribution-provider.png "Screenshot delle impostazioni del provider di distribuzione video di terze parti per eventi dinamici")

    - **Usare un provider di distribuzione di terze parti** Attivare questa opzione per abilitare il provider di distribuzione video di terze parti.
    - **Nome provider Sdn** Scegliere il provider che si sta usando.
    - **Codice di licenza del provider** Immettere l'ID licenza ottenuto dal contatto del provider.
    - **URL del modello dell'API Sdn** Immettere l'URL del modello di API ottenuto dal contatto del provider.

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell
Ottenere l'ID licenza o il token API e il modello di API dal contatto del provider e quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:

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

Per altre informazioni, vedere [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Se si prevede di creare eventi dinamici usando un'app o un dispositivo esterno, è necessario configurare anche [il provider di eCDN con Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

>[!Note]
> Il passaggio dall’uso di Microsoft Stream all’uso di [OneDrive for Business e SharePoint per le registrazioni delle riunioni](../tmr-meeting-recording-change.md) avverrà in modo graduale. Al momento del lancio sarà possibile acconsentire esplicitamente all’esperienza. A novembre sarà necessario rifiutarla esplicitamente se si vuole continuare a usare Stream e all'inizio del 2021 sarà chiesto a tutti i clienti di usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
