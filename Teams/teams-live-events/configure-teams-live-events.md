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
- enabler-strategic
description: Informazioni su come gestire le impostazioni per gli eventi live di Teams tenute nell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831196"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurare le impostazioni degli eventi live in Microsoft Teams

Usare le impostazioni degli eventi live di Teams per configurare le impostazioni per gli eventi live che si svolgono nell'organizzazione. È possibile configurare un URL di supporto e un provider di distribuzione di video di terze parti. Queste impostazioni si applicano a tutti gli eventi live creati nell'organizzazione.

Queste impostazioni possono essere facilmente gestite nell'interfaccia di amministrazione di Microsoft Teams. Nel riquadro di spostamento sinistro passare alle **impostazioni degli eventi** live di  >  **Riunioni.**

![Schermata delle impostazioni degli eventi live di Teams](../media/teams-live-events-settings.png "Schermata delle impostazioni degli eventi live di Teams che è possibile configurare nell'interfaccia di amministrazione di Microsoft Teams")

## <a name="set-up-event-support-url"></a>Configurare l'URL di supporto per gli eventi

Questo URL viene visualizzato dai partecipanti all'evento live. Aggiungere l'URL di supporto per l'organizzazione per offrire ai partecipanti un modo per contattare il supporto durante un evento live.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro, passare alle **impostazioni degli eventi live** di  >  **Riunioni.**
2. In **URL supporto** immettere l'URL di supporto dell'organizzazione.

    ![Impostazione dell'URL di supporto per gli eventi live nell'interfaccia di amministrazione](../media/teams-live-events-settings-supporturl.png "Schermata dell'impostazione dell'URL di supporto per gli eventi live di Teams")

### <a name="using-windows-powershell"></a>Uso Windows PowerShell

Esegui il seguente comando:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurare un provider di distribuzione di video di terze parti 

Se hai acquistato e configurato una soluzione di rete definita dal software (SDN) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner di distribuzione di video Microsoft, configura il provider per gli eventi live in Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](../media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro, passare alle **impostazioni degli eventi live** di  >  **Riunioni.**
2. In **Provider di distribuzione di video di terze parti,** completa le operazioni seguenti: 

    ![Impostazioni dei provider di distribuzione di video di terze parti nell'interfaccia di amministrazione](../media/teams-live-events-settings-distribution-provider.png "Screenshot delle impostazioni del provider di distribuzione di video di terze parti per gli eventi live")

    - **Usare un provider di distribuzione di terze parti** Attiva questa opzione per abilitare il provider di distribuzione di video di terze parti.
    - **Nome provider SDN** Scegliere il provider in uso.
    - **Codice di licenza del provider** Immettere l'ID di licenza ottenuto dal contatto del provider.
    - **URL modello API SDN** Immettere l'URL del modello API ricevuto dal contatto del provider.

### <a name="using-windows-powershell"></a>Uso Windows PowerShell
Ottenere il modello di ID licenza o token API e API dal contatto del provider e quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:

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

Per altre informazioni, vedere [Set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> Se si prevede di creare eventi live usando un'app o un dispositivo esterno, è necessario configurare anche il [provider eCDN con Microsoft Stream.](https://docs.microsoft.com/stream/network-caching) 

>[!Note]
> Il passaggio dall'utilizzo di Microsoft Stream a [ OneDrive for Business e SharePoint per le registrazioni delle riunioni ](../tmr-meeting-recording-change.md) sarà graduale. Al momento del lancio sarà possibile acconsentire esplicitamente all’esperienza. A novembre sarà necessario rifiutarla esplicitamente se si vuole continuare a usare Stream e all'inizio del 2021 sarà chiesto a tutti i clienti di usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
