---
title: Configurare le impostazioni degli eventi dinamici in Microsoft Teams
author: chuckedmonson
ms.author: chucked
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
f1.keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: f12432bb7932d7ab974f229344b5b5be51a1cb74
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708352"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurare le impostazioni degli eventi dinamici in Microsoft Teams

Usa le impostazioni eventi di teams Live per configurare le impostazioni per gli eventi dinamici che si svolgono nell'organizzazione. È possibile impostare un URL di supporto e configurare un provider di distribuzione video di terze parti. Queste impostazioni si applicano a tutti gli eventi dinamici creati nell'organizzazione. 

Puoi gestire facilmente queste impostazioni nell'interfaccia di amministrazione di Microsoft teams. Nella barra di spostamento sinistra, vai a**Impostazioni eventi live** **riunioni** > . 

![Schermata delle impostazioni di eventi live di Teams](../media/teams-live-events-settings.png "Screenshot delle impostazioni di eventi live di teams che è possibile configurare nell'interfaccia di amministrazione di Microsoft Teams") 

## <a name="set-up-event-support-url"></a>URL del supporto per la configurazione dell'evento

Questo URL viene visualizzato nei partecipanti agli eventi dinamici. Aggiungere l'URL del supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento dinamico.

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft Teams

1. Nella barra di spostamento sinistra, vai a**Impostazioni eventi live** **riunioni** > .
2. In **URL di supporto**immettere l'URL di supporto dell'organizzazione. 

    ![Impostazione dell'URL del supporto per eventi dinamici nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png "Screenshot dell'impostazione dell'URL del supporto per gli eventi live di Teams")

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell
Esegui il seguente comando:
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Per altre informazioni, vedere [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurare un provider di distribuzione video di terze parti 

Se è stata acquistata e configurata una soluzione software defined Network (SDN) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner di recapito video Microsoft, configurare il provider per gli eventi dinamici in teams. 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft Teams

1. Nella barra di spostamento sinistra, vai a**Impostazioni eventi live** **riunioni** > .
2. In **provider di distribuzione video di terze parti**completare le operazioni seguenti: 

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
Per altre informazioni, vedere [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Se si prevede di creare eventi dinamici usando un'app o un dispositivo esterno, è necessario configurare anche [il provider di eCDN con Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)