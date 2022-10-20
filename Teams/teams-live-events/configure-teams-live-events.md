---
title: Configurare le impostazioni degli eventi live in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: Informazioni su come gestire le impostazioni per gli eventi live di Teams tenuti nell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd870acf26300b38ceb4b1e54b6e3bbdcbf1b92d
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614559"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurare le impostazioni degli eventi live in Microsoft Teams

Usare le impostazioni degli eventi live di Teams per configurare le impostazioni per gli eventi live che si svolgono nell'organizzazione. È possibile configurare un URL di supporto e un provider di distribuzione video di terze parti. Queste impostazioni si applicano a tutti gli eventi live creati nell'organizzazione.

È possibile gestire facilmente queste impostazioni nell'interfaccia di amministrazione di Microsoft Teams. Nel riquadro di spostamento sinistro passare alle **impostazioni degli eventi** di **Riunioni** >  in tempo reale.

![Screenshot delle impostazioni degli eventi live di Teams.](../media/teams-live-events-settings-new.png "Schermata delle impostazioni degli eventi live di Teams che è possibile configurare nell'interfaccia di amministrazione di Microsoft Teams")

## <a name="set-up-event-support-url"></a>Configurare l'URL di supporto per gli eventi

Questo URL viene visualizzato per i partecipanti all'evento live. Aggiungere l'URL del supporto per l'organizzazione per consentire ai partecipanti di contattare il supporto durante un evento live.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Impostazioni evento riunioni** >  in tempo reale.
2. In **URL supporto** immetti l'URL di supporto della tua organizzazione.

    ![Impostazione DELL'URL di supporto per gli eventi live nell'interfaccia di amministrazione.](../media/teams-live-events-settings-supporturl.png "Schermata dell'impostazione dell'URL del supporto per gli eventi live di Teams")

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell

Esegui il seguente comando:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Per ulteriori informazioni, vedi [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurare un provider di distribuzione video di terze parti 

Se hai acquistato e configurato una soluzione SDN (Software Defined Network) o una soluzione eCDN (Enterprise Content Delivery Network) tramite un partner per la distribuzione di video Microsoft, configura il provider per gli eventi live in Teams. 

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Impostazioni evento riunioni** >  in tempo reale.
2. In **Provider di distribuzione video di terze parti** completa quanto segue: 

    ![Impostazioni del provider di distribuzione video di terze parti nell'interfaccia di amministrazione.](../media/teams-live-events-settings-distribution-provider-new.png "Schermata delle impostazioni del provider di distribuzione video di terze parti per gli eventi live")

    - **Provider di distribuzione di terze parti** Attiva questa opzione per abilitare il provider di distribuzione di video di terze parti.
    - **Nome provider SDN** Scegli il provider che stai usando.
    - **Configurazione SDN** Immettere i dettagli sulla configurazione SDN.
        
### <a name="using-windows-powershell"></a>Uso di Windows PowerShell
Ottenere l'ID licenza o il modello di API e token API dal contatto del provider, quindi eseguire una delle operazioni seguenti, a seconda del provider in uso:

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
**Peer5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

Per ulteriori informazioni, vedi [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

> [!NOTE]
> Se prevedi di creare eventi live usando un'app o un dispositivo esterno, dovrai anche [configurare il provider eCDN con Microsoft Stream](/stream/network-caching). 

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

>[!Note]
> La soluzione eCDN scelta è soggetta alle condizioni del servizio e all'informativa sulla privacy del provider di terze parti selezionate, che regoleranno l'uso della soluzione del provider di eCDN. L'uso della soluzione del provider di eCDN non sarà soggetto alle condizioni dei contratti multilicenza o dei servizi online Microsoft. Se non accetti le condizioni del provider di terze parti, non abilitare la soluzione eCDN in Microsoft Teams.

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Pianificare gli eventi live di Teams](plan-for-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
