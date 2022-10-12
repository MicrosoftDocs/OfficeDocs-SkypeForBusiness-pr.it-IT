---
title: Gestire i criteri delle riunioni per audio e video
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri riunione in Teams per audio e video.
ms.openlocfilehash: 1f03f81c52c089a922040e0065621f5bf95fe20e
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551480"
---
# <a name="meeting-policy-settings-for-audio--video"></a>Impostazioni dei criteri riunione per audio & video

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

Questo articolo descrive le impostazioni dei criteri di riunione specifiche per audio e video. Ecco alcuni esempi:

- [Modalità per audio IP](#mode-for-ip-audio)
- [Modalità per video IP](#mode-for-ip-video)
- [Video IP](#ip-video)
- [Velocità in bit supporto (Kbs)](#media-bit-rate-kbs)
- [Modalità filtri video](#video-filters-mode)
- [Consenti impostazioni di sfondo personalizzate](#allow-custom-background-settings)
- [Controllo della fotocamera estremi (FECC) per le fotocamere con zoom di inclinazione del punto (PTZ)](#far-end-camera-control-fecc-for-point-tilt-zoom-ptz-cameras)

## <a name="mode-for-ip-audio"></a>Modalità per audio IP

Questo è un criterio per utente. Questa impostazione controlla se l'audio può essere attivato nelle riunioni e nelle chiamate di gruppo. Ecco i valori per questa impostazione.

|Valore dell'impostazione|Comportamento|
|---|---|
|**Audio in uscita e in arrivo abilitato**|L'audio in uscita e in arrivo è consentito nella riunione. Questa è l'impostazione predefinita.|
|**Non abilitato**|L'audio in uscita e in arrivo è disattivato nella riunione.|

Se è impostato su **Non abilitato** per un utente, l'utente può comunque pianificare e organizzare riunioni, ma non può usare l'audio. Per partecipare a una riunione, deve connettersi telefonicamente tramite la rete PSTN (Public Switched Telephone Network) o dal telefono. Per i partecipanti alla riunione che non hanno criteri assegnati (ad esempio, i partecipanti anonimi), questa opzione è impostata su **Audio in uscita e in arrivo abilitato** per impostazione predefinita. Nei client mobili di Teams, se questa impostazione non è abilitata, l'utente deve accedere alla riunione tramite PSTN.

Questa impostazione non si applica alle chiamate tra due persone. Per limitare le chiamate tra due persone, configurare un [criterio di chiamata](teams-calling-policy.md) di Teams e disabilitare l'impostazione **Effettua chiamate private**. Questa impostazione non si applica nemmeno ai dispositivi delle sale riunioni come i dispositivi Surface Hub e Microsoft Teams Rooms.

Questa impostazione non è ancora disponibile per gli ambienti Microsoft 365 Government Community Cloud (GCC), GCC High o Department of Defense (DoD).

Per altre informazioni, vedere [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

## <a name="mode-for-ip-video"></a>Modalità per video IP

Questo è un criterio per utente. Questa impostazione controlla se il video può essere attivato nelle riunioni e nelle chiamate di gruppo. Ecco i valori per questa impostazione.

|Valore dell'impostazione|Comportamento|
|---|---|
|**Video in uscita e in arrivo abilitato**|Il video in uscita e in arrivo è consentito nella riunione. Questa è l'impostazione predefinita.|
|**Non abilitato**|Il video in uscita e in arrivo è disattivato nella riunione. Nei client per dispositivi mobili di Teams, gli utenti non possono condividere video o foto nella riunione. <br><br>Si noti che se la **modalità per l'audio IP** non è abilitata, anche **la modalità per il video IP** rimarrà non abilitata.|

Se è impostato su **Non abilitato** per un utente, l'utente non può attivare o visualizzare video condivisi da altri partecipanti alla riunione. Per i partecipanti alla riunione che non hanno criteri assegnati (ad esempio, i partecipanti anonimi), questa opzione è impostata su **Video in uscita e in arrivo abilitato** per impostazione predefinita.

Questa impostazione non si applica ai dispositivi delle sale riunioni come i dispositivi Surface Hub e Microsoft Teams Rooms.

Questa impostazione non è ancora disponibile per gli ambienti Microsoft 365 Government Community Cloud (GCC), GCC High o Department of Defense (DoD).

> [!NOTE]
> Tenere presente che questa impostazione controlla sia il video in uscita che quello in arrivo, mentre l'impostazione **Video IP** controlla il video in uscita. Per altre informazioni, vedere [Quale impostazione dei criteri per video IP ha la precedenza?](#which-ip-video-policy-setting-takes-precedence) e [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

Per altre informazioni, vedere [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

## <a name="ip-video"></a>Video IP

Questa è una combinazione di criterio per organizzatore e criterio per utente. Il video è un componente chiave per le riunioni. In alcune organizzazioni, gli amministratori possono volere un maggiore controllo sugli utenti che possono usare il video nelle riunioni. Questa impostazione controlla se è possibile attivare il video nelle riunioni ospitate da un utente e nelle chiamate tra due persone e di gruppo avviate da un utente. Nei client mobili di Teams, questa impostazione controlla se gli utenti possono condividere foto e video in una riunione.

Le riunioni organizzate da un utente che ha questa impostazione di criteri abilitata consentono la condivisione di video nella riunione da parte dei partecipanti, se anche questi ultimi hanno l'impostazione di criteri abilitata. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi e federati, ereditano i criteri dell'organizzatore della riunione.

> [!NOTE]
> Questa impostazione controlla solo il video in uscita, mentre l'impostazione **Modalità per video IP** controlla il video in uscita e in arrivo. Per altre informazioni, vedere [Quale impostazione dei criteri per video IP ha la precedenza?](#which-ip-video-policy-setting-takes-precedence) e [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

|Client Web e desktop di Teams|Client per dispositivi mobili di Teams|
|:---:|:---:|
|![Screenshot che mostra la schermata di accesso alla riunione con le impostazioni per audio/video su desktop.](media/meeting-policies-audio-video-settings.png)|![Screenshot che mostra la schermata di accesso alla riunione con le impostazioni per audio/video su dispositivo mobile](media/meeting-policies-mobile-join.png)|

Osserviamo l'esempio seguente.

|Utente|Criterio di riunione|Video IP|
|---|---|---|
|Daniela|Globale|Attivato|
|Amanda|CriterioRiunionePosizione1|Disattivato|

Le riunioni ospitate da Daniela consentono di attivare il video. Daniela può partecipare alla riunione e attivare il video. Amanda non può attivare il video nella riunione di Daniela poiché il criterio di Amanda è impostato in modo da non consentire il video. Amanda può vedere i video condivisi da altri partecipanti alla riunione.

Nelle riunioni ospitate da Amanda nessuno può attivare il video, indipendentemente dai criteri video assegnati. Questo significa che Daniela non può attivare il video nelle riunioni di Amanda.  

Se Daniela chiama Amanda con il video, Amanda può rispondere alla chiamata solo con l'audio.  Una volta connessa la chiamata, Amanda potrà vedere il video di Daniela, ma non potrà attivare il video. Se Amanda chiama Daniela, Daniela può rispondere alla chiamata con il video e l'audio. Una volta connessa la chiamata, Daniela può attivare o disattivare suo video come desidera.

Per altre informazioni, vedere [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

### <a name="which-ip-video-policy-setting-takes-precedence"></a>Quale impostazione dei criteri video IP ha la precedenza?

Per un utente, l'impostazione di criteri più restrittiva per il video ha la precedenza. Ecco alcuni esempi.

|Video IP|Modalità per video IP|Esperienza di riunione|
|---|---|---|
|Organizzatore: **Attivato**<br><br>Partecipante: **Attivato**|Partecipante: **Disabilitato**|L'impostazione **Modalità per video IP** ha la precedenza. Il partecipante al quale è assegnato questo criterio non può attivare o visualizzare i video condivisi dagli altri.|
|Organizzatore: **Attivato**<br><br>Partecipante: **Attivato**|Partecipante: **Video in uscita e in arrivo abilitato**|Il partecipante al quale è assegnato questo criterio può attivare o visualizzare i video condivisi dagli altri.|
|Organizzatore: **Attivato**<br><br>Partecipante: **Disattivato**|Partecipante: **Video in uscita e in arrivo abilitato**|L'impostazione **video IP** ha la precedenza. I partecipanti possono solo visualizzare video in arrivo e non inviare video in uscita.|
|Organizzatore: **Attivato**<br><br>Partecipante: **Disattivato**|Partecipante: **Disabilitato**|L'impostazione **Modalità per video IP** ha la precedenza. Il partecipante non può visualizzare il video in arrivo o in uscita.|
|Organizzatore: **Disattivato**||L'impostazione **video IP** ha la precedenza perché è disattivata per l'organizzatore. Nessuno può attivare il video nelle riunioni organizzate dall'utente a cui è assegnato questo criterio.|

### <a name="manage-audiovideo-for-meeting-participants"></a>Gestire audio/video per i partecipanti alle riunioni

|Per:|Impostare le impostazioni di criteri seguenti|
|---|---|
|Disabilitare audio e video per i partecipanti nelle riunioni|Modalità per audio IP: **Disabilitata**<br> Modalità per video IP: **Disabilitato**<br>Video IP: N/D|
|Abilitare solo video e audio in arrivo per i partecipanti nelle riunioni|Modalità per audio IP: **Audio in uscita e in arrivo abilitato**<br> Modalità per video IP: **Video in uscita e in arrivo abilitato**<br>Video IP: **Disattivato**|
|Disabilitare video per i partecipanti nelle riunioni (i partecipanti hanno solo audio)|Modalità per audio IP: **Abilita audio in uscita e in arrivo**<br> Modalità per video IP: **Disabilitato**<br>Video IP: N/D
|Abilitare audio e video per i partecipanti nelle riunioni|Modalità per audio IP: **Audio in uscita e in arrivo abilitato** (impostazione predefinita)<br> Modalità per video IP: **Video in uscita e in arrivo abilitato** (impostazione predefinita)<br>Video IP: **Attivato** (impostazione predefinita)|

Vengono applicati i criteri più restrittivi tra i criteri dell'organizzatore della riunione e i criteri dell'utente. Ad esempio, se un organizzatore ha un criterio che limita il video e un criterio di un utente non limita il video, i partecipanti alla riunione ereditano il criterio dell'organizzatore della riunione e non hanno accesso al video nelle riunioni. Ciò significa che possono partecipare alla riunione solo con l'audio.

> [!NOTE]
> Quando un utente avvia una chiamata di gruppo per partecipare tramite telefono, la schermata **Usa il telefono per l'audio** non viene visualizzata. Si tratta di un problema noto per il quale stiamo cercando di trovare una soluzione. Per ovviare a questo problema, selezionare **Audio telefono** in **Altre opzioni di partecipazione**.

### <a name="teams-mobile-clients"></a>Client Teams per dispositivi mobili

Per gli utenti dei client mobili di Teams, la possibilità di condividere foto e video durante una riunione è determinata anche  dall'impostazione della **modalità video IP o video IP**. A seconda dell'impostazione di criteri che ha la precedenza, la possibilità di condividere video e foto non sarà disponibile. Questa impostazione non interessa la condivisione dello schermo, che si configura usando un'impostazione [Modalità di condivisione dello schermo](meeting-policies-content-sharing.md#screen-sharing-mode) separata. Inoltre, è possibile impostare un [criterio per dispositivi mobili di Teams](/powershell/module/skype/new-csteamsmobilitypolicy) per impedire agli utenti di dispositivi mobili di usare il video IP tramite una rete cellulare, il che significa che devono usare una connessione WiFi.

## <a name="media-bit-rate-kbs"></a>Velocità in bit supporto (KB)

Questo è un criterio per utente. Questa impostazione determina la velocità in bit per le trasmissioni audio, video e di condivisione di app basate su video nelle chiamate e riunioni dell'utente. Si applica ai flussi multimediali in uplink o downlink per gli utenti nella chiamata o riunione. Questa impostazione consente di controllare in modo granulare la gestione della larghezza di banda dell'organizzazione. In base agli scenari di riunione necessari per gli utenti, è necessario disporre di una larghezza di banda sufficiente per fornire un'esperienza di buona qualità. Il valore minimo è 30 Kbps e il valore massimo dipende dallo scenario della riunione. Per altre informazioni sulla larghezza di banda minima consigliata per una buona qualità di riunioni, chiamate ed eventi live in Teams, vedere [Requisiti di larghezza di banda](prepare-network.md#bandwidth-requirements).

Se la larghezza di banda non è sufficiente per una riunione, i partecipanti vedranno un messaggio che indica una scarsa qualità della rete.

Per le riunioni che necessitano di un'esperienza video di qualità ottimale, ad esempio le riunioni del consiglio di amministrazione e gli eventi live di Teams, è consigliabile impostare la larghezza di banda su 10 Mbps. Anche se è stata impostata la massima qualità dell'esperienza, lo stack multimediale di Teams si adatta alle condizioni di larghezza di banda ridotte quando vengono rilevate determinate condizioni di rete, a seconda dello scenario.

## <a name="video-filters-mode"></a>Modalità filtri video

<a name="bkvideofilters"> </a>

Questo è un criterio per utente. Questa impostazione controlla se gli utenti possono personalizzare lo sfondo del video in una riunione.

È possibile usare sia l'interfaccia di amministrazione di Teams che PowerShell per impostare questo criterio. È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e quindi assegnarlo agli utenti.

Per specificare se gli utenti possono personalizzare lo sfondo video in una riunione, impostare il parametro **VideoFiltersMode** (**impostazione Seleziona filtri video** nell'interfaccia di amministrazione di Teams) come segue:

|Valore dell'impostazione in PowerShell|Impostazione del valore nell'interfaccia di amministrazione di Teams|Comportamento|
|---|---|---|
|**NoFilters**|**Nessun filtro**|Un utente non può personalizzare lo sfondo del video.|
|**BlurOnly**|**Solo sfocatura dello sfondo**|Gli utenti hanno la possibilità di sfocare lo sfondo del video.|
|**BlurandDefaultBackgrounds**|**Sfocatura dello sfondo e immagini predefinite**|Gli utenti hanno la possibilità di sfocare lo sfondo del video o di scegliere il set predefinito di immagini da usare come sfondo.|
|**AllFilters**|**Tutti i filtri**|L'utente ha la possibilità di sfocare lo sfondo del video, di scegliere il set predefinito di immagini o di caricare immagini personalizzate da usare come sfondo.|

> [!NOTE]
> Le immagini caricate dagli utenti non vengono analizzate da Teams. Se si usa l'impostazione **AllFilters**, sono previsti criteri interni dell'organizzazione per impedire agli utenti di caricare immagini offensive o inappropriate o di cui l'organizzazione non dispone dei diritti di utilizzo per gli sfondi delle riunioni di Teams.

## <a name="allow-custom-background-settings"></a>Consenti impostazioni di sfondo personalizzate

È possibile aggiungere immagini di sfondo personalizzate da usare per ogni tenant. Questa funzionalità consente alle aziende di applicare il branding aziendale alle riunioni di Teams.

> [!NOTE]
> Per caricare immagini di sfondo, l'account amministratore usato per eseguire questa procedura deve avere una licenza di Teams.

1. Passare all'interfaccia di amministrazione di Teams.

2. Selezionare **Criteri** \> **riunione** **Personalizza immagini riunione**\>.

   ![Selezione dei criteri riunione con il pulsante Personalizza immagini riunione evidenziato.](media/custom-background-image-button.png)

3. Selezionare **Attivato** da **Immagini di sfondo a livello di organizzazione**.

4. Selezionare **+ Aggiungi immagini**.

5. Nel pannello Gestione sfondi seleziona **Aggiungi immagine**.

6. Assicurarsi che le immagini soddisfino questi requisiti:
  
   - Dimensione minima 360 px
   - Dimensione massima 2048 px
   - Tipo di file PNG, JPG o BMP
   - È possibile caricare al massimo 50 immagini

7. Visualizzare in anteprima le immagini selezionate e quindi selezionare **Chiudi**.

8. Rivedere le immagini e aggiungerne altre in base alle esigenze.

9. Selezionare **Salva**.

I partecipanti alla riunione vedranno una selezione di immagini di sfondo che possono usare quando partecipano a una riunione.

> [!NOTE]
> L'applicazione delle modifiche può richiedere fino a 24 ore.
>
> Questa funzionalità è temporaneamente disponibile in anteprima pubblica per tutti i clienti di Microsoft Teams. Per ottenere questa funzionalità dopo l'anteprima, ogni utente avrà bisogno della licenza per il componente aggiuntivo Advanced Communications. Per ulteriori informazioni, vedere [Componente aggiuntivo per comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="far-end-camera-control-fecc-for-point-tilt-zoom-ptz-cameras"></a>Controllo della fotocamera estremi (FECC) per le fotocamere con zoom di inclinazione del punto (PTZ)

Il controllo della fotocamera estremo è un criterio che può essere assegnato a Teams Rooms sugli account delle risorse di Windows. Consente alle videocamere PTZ connesse a una sala riunioni di Teams di essere controllate dai partecipanti alla riunione nell'app client di Teams durante le riunioni.

Per usare il controllo della fotocamera lontano, i partecipanti alla riunione dovranno ottenere l'app **Controlli fotocamera PTZ** .  Vedere [Consentire e bloccare app](manage-apps.md#allow-and-block-apps) per informazioni su come rendere l'app disponibile nell'app store dell'organizzazione.

Per specificare chi può utilizzare il controllo della fotocamera di estremi in una riunione, creare e assegnare un nuovo criterio a un account di risorse Teams Rooms utilizzando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy?view=skype-ps) o utilizzare [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) per modificarne uno esistente. Impostare il `TeamsCameraFarEndPTZMode` parametro su uno dei valori seguenti:

|Valore dell'impostazione|Comportamento|
|---|---|
|Disattiva|Questa è l'impostazione predefinita. Quando è impostata su "disabilitata", nessuno può utilizzare i controlli della fotocamera PTZ.|
|AutoAcceptAll|I controlli della fotocamera PTZ sono automaticamente disponibili per qualsiasi partecipante alla riunione.|
|AutoAcceptInTenant|I controlli della fotocamera PTZ sono disponibili automaticamente solo per i partecipanti nella stessa organizzazione della sala riunioni di Teams.|

Quando `TeamsCameraFarEndPTZMode` è impostato su `AutoAcceptAll` o `AutoAcceptInTenant`, il controllo della fotocamera può comunque essere disattivato manualmente dalla sala di Teams in qualsiasi momento durante una riunione. Il controllo della fotocamera non è disponibile anche quando la fotocamera è disattivata.

È supportata qualsiasi fotocamera con controlli meccanici PTZ e UVC. Per un elenco delle fotocamere certificate per Teams, incluse le fotocamere PTZ e non PTZ, vedi [Versioni certificate del firmware per periferiche audio e video USB](rooms/requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals). Questa funzionalità non è ancora supportata nelle fotocamere con controlli PTZ digitali o su Teams Rooms su Android.  

> [!NOTE]
> Aggiorna il firmware della fotocamera prima di testare i controlli PTZ. Vedi la documentazione dell'OEM (Original Equipment Manufacturer) per aggiornare il firmware.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
