---
title: Gestire i criteri delle riunioni per audio e video
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per audio e video.
ms.openlocfilehash: 4f8de802fd2ddf90555a34ac0b8d66d2d7021f79
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726565"
---
# <a name="meeting-policy-settings-for-audio--video"></a>Impostazioni dei criteri per le riunioni per & video

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

Questo articolo descrive le impostazioni dei criteri di riunione specifiche per audio e video. Di seguito sono riportate le informazioni seguenti:

- [Consenti la trascrizione](#allow-transcription)
- [Consenti registrazione cloud](#allow-cloud-recording)
- [Modalità per audio IP](#mode-for-ip-audio)
- [Modalità per video IP](#mode-for-ip-video)
- [Consenti video IP](#allow-ip-video)
- [Velocità in bit supporto (Kbs)](#media-bit-rate-kbs)
- [Modalità filtri video](#video-filters-mode)
- [Consenti impostazioni di sfondo personalizzate](#allow-custom-background-settings)

### <a name="allow-transcription"></a>Consenti la trascrizione

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. Se si disattiva questa opzione, durante la riproduzione di una registrazione di riunione non saranno disponibili le opzioni **Cerca** e **Cc**. La persona che ha avviato la registrazione ha bisogno che questa impostazione sia attivata perché la registrazione includa anche una trascrizione.

Si noti che la trascrizione per le riunioni registrate è attualmente supportata solo per gli utenti che hanno la lingua di Teams impostata sull'inglese e quando durante la riunione si usa l'inglese.

### <a name="allow-cloud-recording"></a>Consenti registrazione cloud

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione controlla se è possibile registrare le riunioni di quest'utente. La registrazione può essere avviata dall'organizzatore della riunione o da un altro partecipante alla riunione, se l'impostazione dei criteri è attivata per il partecipante e se si tratta di un utente autenticato della stessa organizzazione.

Le persone esterne all'organizzazione, ad esempio gli utenti federati e anonimi, non possono avviare la registrazione. Gli utenti guest non possono avviare o interrompere la registrazione.

![Screenshot che mostra le opzioni di registrazione.](media/meeting-policies-recording.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti registrazione cloud |
|---------|---------|---------|
|Daniela | Globale   | Disattivato |
|Amanda | CriterioRiunionePosizione1 | Attivato|
|Luca (utente esterno) | Non applicabile | Non applicabile|

Non è possibile registrare le riunioni organizzate da Daniela e Amanda che ha l'impostazione del criterio attivata, non può registrare le riunioni organizzate da Daniela. Le riunioni organizzate da Amanda possono essere registrate, tuttavia Daniela, che ha l'impostazione del criterio disabilitata, e John, che è un utente esterno, non possono registrare le riunioni organizzate da Amanda.

Per altre informazioni sulla registrazione di una riunione cloud, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

### <a name="mode-for-ip-audio"></a>Modalità per audio IP

Questo è un criterio per utente. Questa impostazione controlla se l'audio può essere attivato nelle riunioni e nelle chiamate di gruppo. Ecco i valori per questa impostazione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Audio in uscita e in arrivo abilitato**    |Per impostazione predefinita, sia l’audio in entrata che in uscita sono consentiti nella riunione. |
|**Disattiva**     |L'audio in uscita e in arrivo è disattivato nella riunione.     |

Se l'opzione è impostata su **Disabilitato** per un utente, tale utente può comunque pianificare e organizzare riunioni ma senza poter usare l'audio. Per partecipare a una riunione, deve connettersi telefonicamente tramite la rete PSTN (Public Switched Telephone Network) o dal telefono. Per i partecipanti alla riunione che non hanno criteri assegnati (ad esempio, i partecipanti anonimi), questa opzione è impostata su **Audio in uscita e in arrivo abilitato** per impostazione predefinita. Nei client per dispositivi mobili di Teams, se questa impostazione è disabilitata, l'utente deve connettersi telefonicamente alla riunione tramite PSTN.

Questa impostazione non si applica alle chiamate tra due persone. Per limitare le chiamate tra due persone, configurare un [criterio di chiamata](teams-calling-policy.md) di Teams e disabilitare l'impostazione **Effettua chiamate private**. Questa impostazione non si applica nemmeno ai dispositivi delle sale riunioni come i dispositivi Surface Hub e Microsoft Teams Rooms.

Questa impostazione non è ancora disponibile per gli ambienti Microsoft 365 Government Community Cloud (GCC), GCC High o Department of Defense (DoD).

Per altre informazioni, vedere [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modalità per video IP

Questo è un criterio per utente. Questa impostazione controlla se il video può essere attivato nelle riunioni e nelle chiamate di gruppo. Ecco i valori per questa impostazione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Video in uscita e in arrivo abilitato**    | Il video in uscita e in arrivo è consentito nella riunione. Questa è l'impostazione predefinita. |
|**Disattiva**     | Il video in uscita e in arrivo è disattivato nella riunione. Nei client per dispositivi mobili di Teams, gli utenti non possono condividere video o foto nella riunione. <br><br>Se l'impostazione **Modalità per audio IP** è disabilitata, anche l'impostazione **Modalità per video IP** resterà disabilitata.  |

Se impostata su **Disabilitato** per un utente, tale utente non può attivare il video o visualizzare i video condivisi dagli altri partecipanti alla riunione. Per i partecipanti alla riunione che non hanno criteri assegnati (ad esempio, i partecipanti anonimi), questa opzione è impostata su **Video in uscita e in arrivo abilitato** per impostazione predefinita.

Questa impostazione non si applica ai dispositivi delle sale riunioni come i dispositivi Surface Hub e Microsoft Teams Rooms.

Questa impostazione non è ancora disponibile per gli ambienti Microsoft 365 Government Community Cloud (GCC), GCC High o Department of Defense (DoD).

> [!NOTE]
> Questa impostazione controlla il video in uscita e in arrivo, mentre l'impostazione **Consenti video IP** controlla solo il video in uscita. Per altre informazioni, vedere [Quale impostazione dei criteri per video IP ha la precedenza?](#which-ip-video-policy-setting-takes-precedence) e [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

Per altre informazioni, vedere [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

### <a name="allow-ip-video"></a>Consenti video IP

Questa è una combinazione di criterio per organizzatore e criterio per utente. Il video è un componente chiave per le riunioni. In alcune organizzazioni, gli amministratori possono volere un maggiore controllo sugli utenti che possono usare il video nelle riunioni. Questa impostazione controlla se è possibile attivare il video nelle riunioni ospitate da un utente e nelle chiamate tra due persone e di gruppo avviate da un utente. Nei Teams per dispositivi mobili, questa impostazione controlla se gli utenti possono condividere foto e video in una riunione.

Le riunioni organizzate da un utente che ha questa impostazione di criteri abilitata consentono la condivisione di video nella riunione da parte dei partecipanti, se anche questi ultimi hanno l'impostazione di criteri abilitata. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi e federati, ereditano i criteri dell'organizzatore della riunione.

> [!NOTE]
> Questa impostazione controlla solo il video in uscita, mentre l'impostazione **Modalità per video IP** controlla il video in uscita e in arrivo. Per altre informazioni, vedere [Quale impostazione dei criteri per video IP ha la precedenza?](#which-ip-video-policy-setting-takes-precedence) e [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

| Client Web e desktop di Teams |Client per dispositivi mobili di Teams  |
|:-------:|:-------:|
|![Screenshot che mostra la partecipazione alla riunione con le impostazioni audio/video sul desktop.](media/meeting-policies-audio-video-settings.png)    |![Screenshot che mostra la schermata di accesso alla riunione con le impostazioni per audio/video su dispositivo mobile](media/meeting-policies-mobile-join.png)          |

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti video IP |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda    | CriterioRiunionePosizione1        | Disattivato      |

Le riunioni ospitate da Daniela consentono di attivare il video. Daniela può partecipare alla riunione e attivare il video. Amanda non può attivare il video nella riunione di Daniela poiché il criterio di Amanda è impostato in modo da non consentire il video. Amanda può vedere i video condivisi da altri partecipanti alla riunione.

Nelle riunioni ospitate da Amanda nessuno può attivare il video, indipendentemente dai criteri video assegnati. Questo significa che Daniela non può attivare il video nelle riunioni di Amanda.  

Se Daniela chiama Amanda con il video, Amanda può rispondere alla chiamata solo con l'audio.  Una volta connessa la chiamata, Amanda potrà vedere il video di Daniela, ma non potrà attivare il video. Se Amanda chiama Daniela, Daniela può rispondere alla chiamata con il video e l'audio. Una volta connessa la chiamata, Daniela può attivare o disattivare suo video come desidera.

Per altre informazioni, vedere [Gestire audio/video per i partecipanti alle riunioni](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Quale impostazione dei criteri video IP ha la precedenza?

Per un utente, l'impostazione di criteri più restrittiva per il video ha la precedenza. Ecco alcuni esempi.

|Consenti video IP|Modalità per video IP|Esperienza di riunione|
|---------|---------|---------|
|Organizzatore: **Attivato**<br><br>Partecipante: **Attivato** |Partecipante: **Disabilitato**        |L'impostazione **Modalità per video IP** ha la precedenza. Il partecipante al quale è assegnato questo criterio non può attivare o visualizzare i video condivisi dagli altri.|
|Organizzatore: **Attivato**<br><br>Partecipante: **Attivato** |Partecipante: **Video in uscita e in arrivo abilitato**          |Il partecipante al quale è assegnato questo criterio può attivare o visualizzare i video condivisi dagli altri.         |
|Organizzatore: **Attivato**<br><br>Partecipante: **Disattivato** |Partecipante: **Video in uscita e in arrivo abilitato**         |L'impostazione **Consenti video IP** ha la precedenza. I partecipanti possono solo visualizzare video in arrivo e non inviare video in uscita.         |
|Organizzatore: **Attivato**<br><br>Partecipante: **Disattivato** |Partecipante: **Disabilitato**         |L'impostazione **Modalità per video IP** ha la precedenza. Il partecipante non può visualizzare il video in arrivo o in uscita.|
|Organizzatore: **Disattivato**    |       |L'opzione **Consenti video IP** ha la precedenza poiché è disattivata per l'organizzatore. Nessuno può attivare il video nelle riunioni organizzate dall'utente a cui è assegnato questo criterio.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Gestire audio/video per i partecipanti alle riunioni

|Per:  |Impostare le impostazioni di criteri seguenti  |
|---------|---------|
|Disabilitare audio e video per i partecipanti nelle riunioni  |Modalità per audio IP: **Disabilitata**<br> Modalità per video IP: **Disabilitato**<br>Consenti video IP: N/D       |
|Abilitare solo video e audio in arrivo per i partecipanti nelle riunioni  |Modalità per audio IP: **Audio in uscita e in arrivo abilitato**<br> Modalità per video IP: **Video in uscita e in arrivo abilitato**<br>Consenti video IP: **Disattivato**       |
|Disabilitare video per i partecipanti nelle riunioni (i partecipanti hanno solo audio)|  Modalità per audio IP: **Abilita audio in uscita e in arrivo**<br> Modalità per video IP: **Disabilitato**<br>Consenti video IP: N/D
|Abilitare audio e video per i partecipanti nelle riunioni    |Modalità per audio IP: **Audio in uscita e in arrivo abilitato** (impostazione predefinita)<br> Modalità per video IP: **Video in uscita e in arrivo abilitato** (impostazione predefinita)<br>Consenti video IP: **Attivata** (impostazione predefinita)    |

Vengono applicati i criteri più restrittivi tra i criteri dell'organizzatore della riunione e i criteri dell'utente. Ad esempio, se un organizzatore ha un criterio che limita il video e un criterio di un utente non limita il video, i partecipanti alla riunione ereditano il criterio dell'organizzatore della riunione e non hanno accesso al video nelle riunioni. Ciò significa che possono partecipare alla riunione solo con l'audio.

> [!NOTE]
> Quando un utente avvia una chiamata di gruppo per partecipare tramite telefono, la schermata **Usa il telefono per l'audio** non viene visualizzata. Si tratta di un problema noto per il quale stiamo cercando di trovare una soluzione. Per ovviare a questo problema, selezionare **Audio telefono** in **Altre opzioni di partecipazione**.  

#### <a name="teams-mobile-clients"></a>Client Teams per dispositivi mobili

Per gli utenti di client Teams per dispositivi mobili, la possibilità di condividere foto e video durante una riunione dipende anche dall'impostazione **Consenti video IP** o **Modalità video IP**. A seconda dell'impostazione di criteri che ha la precedenza, la possibilità di condividere video e foto non sarà disponibile. Questa impostazione non interessa la condivisione dello schermo, che si configura usando un'impostazione [Modalità di condivisione dello schermo](meeting-policies-content-sharing.md#screen-sharing-mode) separata. Inoltre, è possibile impostare un [criterio per dispositivi mobili di Teams](/powershell/module/skype/new-csteamsmobilitypolicy) per impedire agli utenti di dispositivi mobili di usare il video IP tramite una rete cellulare, il che significa che devono usare una connessione WiFi.

### <a name="media-bit-rate-kbs"></a>Velocità in bit supporto (KB)

Questo è un criterio per utente. Questa impostazione determina la velocità in bit per le trasmissioni audio, video e di condivisione di app basate su video nelle chiamate e riunioni dell'utente. Si applica ai flussi multimediali in uplink o downlink per gli utenti nella chiamata o riunione. Questa impostazione consente di controllare in modo granulare la gestione della larghezza di banda dell'organizzazione. In base agli scenari di riunione necessari per gli utenti, è necessario disporre di una larghezza di banda sufficiente per fornire un'esperienza di buona qualità. Il valore minimo è 30 Kbps e il valore massimo dipende dallo scenario della riunione. Per altre informazioni sulla larghezza di banda minima consigliata per una buona qualità di riunioni, chiamate ed eventi live in Teams, vedere [Requisiti di larghezza di banda](prepare-network.md#bandwidth-requirements).

Se la larghezza di banda non è sufficiente per una riunione, i partecipanti vedranno un messaggio che indica una scarsa qualità della rete.

Per le riunioni che necessitano di un'esperienza video di qualità ottimale, ad esempio le riunioni del consiglio di amministrazione e gli eventi live di Teams, è consigliabile impostare la larghezza di banda su 10 Mbps. Anche se è stata impostata la massima qualità dell'esperienza, lo stack multimediale di Teams si adatta alle condizioni di larghezza di banda ridotte quando vengono rilevate determinate condizioni di rete, a seconda dello scenario.

## <a name="video-filters-mode"></a>Modalità filtri video

<a name="bkvideofilters"> </a>

Questo è un criterio per utente. Questa impostazione controlla se gli utenti possono personalizzare lo sfondo del video in una riunione.

Attualmente, è possibile usare solo PowerShell per impostare questo criterio. È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e quindi assegnarlo agli utenti.

Per specificare se gli utenti possono personalizzare lo sfondo del video in una riunione, impostare il parametro **VideoFiltersMode** come indicato di seguito:

|Valore dell'impostazione in PowerShell |Comportamento  |
|---------|---------|
|**NoFilters**     |Un utente non può personalizzare lo sfondo del video.|
|**BlurOnly**     |Gli utenti hanno la possibilità di sfocare lo sfondo del video. |
|**BlurandDefaultBackgrounds**     |Gli utenti hanno la possibilità di sfocare lo sfondo del video o di scegliere il set predefinito di immagini da usare come sfondo. |
|**AllFilters**     |L'utente ha la possibilità di sfocare lo sfondo del video, di scegliere il set predefinito di immagini o di caricare immagini personalizzate da usare come sfondo. |

> [!NOTE]
> Le immagini caricate dagli utenti non vengono analizzate da Teams. Se si usa l'impostazione **AllFilters**, sono previsti criteri interni dell'organizzazione per impedire agli utenti di caricare immagini offensive o inappropriate o di cui l'organizzazione non dispone dei diritti di utilizzo per gli sfondi delle riunioni di Teams.

### <a name="allow-custom-background-settings"></a>Consenti impostazioni di sfondo personalizzate

È possibile aggiungere immagini di sfondo personalizzate da usare per ogni tenant. Questa caratteristica consente alle aziende di applicare il marchio aziendale Teams riunioni.

1. Passare all'interfaccia di amministrazione di Teams.

2. Selezionare **Criteri riunione Personalizza** immagini  >  **riunione**.

   ![Selezione dei criteri riunione con il pulsante Personalizza immagini riunione evidenziato.](media/custom-background-image-button.png)

3. Selezionare **Su da** immagini di sfondo a livello di **organizzazione.**

4. Selezionare **+ Aggiungi immagini**.

5. Nel riquadro Gestione sfondi selezionare **Aggiungi immagine.**

6. Verificare che le immagini soddisfino questi requisiti:
  
   - Dimensioni minime 360 px
   - Dimensioni massime 2048 px
   - Tipo di file PNG, JPG o BMP
   - È possibile caricare al massimo 50 immagini

7. Visualizzare in anteprima le immagini selezionate e quindi selezionare **Chiudi.**

8. Rivedi le immagini e aggiungi altre immagini in base alle esigenze.

9. Selezionare **Salva**.

I partecipanti alla riunione visualizzano una selezione di immagini di sfondo che possono usare quando partecipano a una riunione.

> [!NOTE]
> L'applicazione delle modifiche potrebbe richiedere fino a 24 ore.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
