---
title: Configurare i file di log per il monitoraggio e la risoluzione dei problemi in Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui log debug, multimediali e desktop prodotti da Microsoft Teams, dove sono disponibili e su come possono essere utili per il monitoraggio e la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7883fe7f3d8f9938e66151bb784fa5fc45a91c74
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005366"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Configurare i file di log per il monitoraggio e la risoluzione dei problemi in Teams

Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere usati per assistere nel monitoraggio e nella risoluzione dei problemi di Teams:

-   [Eseguire il debug dei log](#debug-logs)

-   [Registri multimediali](#media-logs)

-   [Log desktop](#desktop-logs)

Questo articolo descrive questi log e come vengono usati. Per informazioni sulla risoluzione di problemi specifici, vedere: [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams). 

Per informazioni su come contattare il supporto tecnico, vedere [Ottenere supporto](/microsoft-365/business-video/get-help-support).

> [!NOTE]
> In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi. Tuttavia, i file generati per questi log conterranno i **termini log diagnostici** nei loro nomi.  

## <a name="logs-overview"></a>Panoramica dei log

È importante raccogliere i log non appena si verifica un problema.

Quando si crea una richiesta di supporto con supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug. Avere a portata di mano i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di avviare rapidamente la risoluzione del problema. **I log multimediali** o **desktop** sono necessari solo se richiesto da Microsoft.

I log di debug, desktop e multimediali verranno raccolti in un'unica cartella con il nome _MsTeams Diagnostics Log \<local date and time\>_. Questa cartella può essere compressa e condivisa quando apri una richiesta di supporto con supporto tecnico Microsoft. La cartella conterrà le cartelle Desktop, Riunione (elementi multimediali) e Debug (Web). È possibile raccogliere i file usando le scelte rapide da tastiera seguenti:

- Windows: <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>

- Mac: <kbd>Opzione</kbd> + <kbd>Comando</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>


Se si verifica un problema con una riunione o un evento live specifico, è utile avere l'URL associato alla riunione. L'URL fornisce informazioni aggiuntive per identificare la riunione esatta o l'evento live nei log. Queste informazioni possono essere raccolte da qualsiasi partecipante per una riunione o dal relatore o produttore per un evento live. Questo URL può essere acquisito passando il puntatore sull'URL del join e scegliendo **Copia collegamento ipertestuale**.

> [!NOTE]
> Se la registrazione multimediale è abilitata, nella cartella Riunione saranno inclusi altri file necessari per l'analisi di problemi audio e video. Se la registrazione multimediale non è abilitata, sarà disponibile un numero limitato di log.
  
La tabella seguente illustra i vari client e i relativi log associati. I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.

|Client |Eseguire il debug|Desktop|Elementi multimediali|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Per un elenco completo dei browser e dei sistemi operativi supportati, vedere [Ottenere client per Microsoft Teams](get-clients.md).

## <a name="debug-logs"></a>Eseguire il debug dei log

I log di debug vengono prodotti dai client desktop di Windows e Mac, nonché dai client basati su browser. I log sono basati su testo e vengono letti dal basso verso l'alto. Possono essere letti usando qualsiasi editor basato su testo e vengono creati nuovi log quando si accede al client.

I log di debug mostrano i flussi di dati seguenti:

-   Login

-   Richieste di connessione ai servizi di livello intermedio

-   Chiamata/conversazione

Per raccogliere i log per Linux:
- Scelta rapida da tastiera: <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>  
- I file saranno disponibili in `~/Downloads`

Per raccogliere i log per Browser e Windows:
- Scelta rapida da tastiera: <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>  
- I file saranno disponibili in `%userprofile%\Downloads`

Per raccogliere i log per Mac:
- Scelta rapida da tastiera:<kbd>COMANDO</kbd> +  <kbd>OPZIONE</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>  
- I file saranno disponibili in `~/Downloads`

## <a name="media-logs"></a>Registri multimediali

I log multimediali contengono dati diagnostici su audio, video e condivisione dello schermo nelle riunioni di Teams. Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.

La registrazione multimediale è attivata per impostazione predefinita per i computer in cui la CPU è:
- qualsiasi Apple M1
- qualsiasi Intel Xeon
- qualsiasi Intel i9, ad eccezione delle serie U, G7, M e MQ
- qualsiasi 6a generazione e successive Intel i7, ad eccezione delle serie U, G7, M e MQ

In caso contrario, è disattivato per impostazione predefinita. Esistono due modi per registrare i dati di diagnostica per le riunioni di Teams:

- Amministrazione configurazione: è possibile gestire i log multimediali per gli utenti finali
- Configurazione degli utenti finali: gli utenti finali possono attivare i log multimediali

### <a name="admin-configuration"></a>configurazione Amministrazione

La gestione dei log multimediali per gli utenti finali offre un'esperienza di risoluzione dei problemi senza problemi, soprattutto quando i problemi sono intermittenti. Gli amministratori possono usare il cmdlet TeamsMediaLoggingPolicy per abilitare e gestire la registrazione dei file multimediali per gli utenti.

Leggi [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) per i cmdlet di PowerShell e altre informazioni.

### <a name="end-user-configuration"></a>Configurazione dell'utente finale

Per consentire agli utenti finali di registrare i dati di diagnostica per le riunioni di Teams, devono attivare l'opzione nel client Teams. Verranno visualizzate **impostazioni** > **generali**, selezionare la casella di controllo **Abilita registrazione per diagnostica riunione** (richiede il riavvio di Teams), riavviare Teams e riprodurre il problema. Per iniziare la registrazione, il client teams deve essere riavviato. Gli utenti possono riavviarlo facendo clic con il pulsante destro del mouse sull'icona nel dock (Mac) o nella barra delle applicazioni (Windows) e selezionando Esci. Dopo la chiusura, possono fare clic sull'icona dell'app per aprire di nuovo Teams.

> [!NOTE]
> Quando gli utenti si disconnetteno da Teams, la registrazione multimediale viene reimpostata come predefinita.

### <a name="collecting-and-sending-media-logs"></a>Raccolta e invio di log multimediali

Prima di inviare i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log coprano l'intervallo di tempo durante la riproduzione del problema.

Per raccogliere i log per Linux:  
- I file saranno disponibili nei percorsi seguenti:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Per raccogliere i log per Windows:  
- I file saranno disponibili nei percorsi seguenti:
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

Per raccogliere i log per Mac:
- I file saranno disponibili nei percorsi seguenti:
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

Ecco un elenco dei file di log generati e delle informazioni che contengono.

<br/>

|Nome file di log  |Descrizione  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Contiene informazioni relative allo stack di supporti. Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su fotocamera e video (VBSS).         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora in cui è assegnato il controllo, e le informazioni del puntatore del mouse.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Registra eventi di traccia dello stack multimediale.         |
|`Debug-0-s2790420889.blog`    | Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.          |
|`tscalling-0-2061129496.blog`   |Registra gli eventi nell'API che chiama ts.       |

## <a name="desktop-logs"></a>Log desktop

I log desktop, noti anche come log del bootstrapper, contengono dati di log che si verificano tra il client desktop e il browser. Analogamente ai log multimediali, questi log sono necessari solo se richiesti da Microsoft. I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato dall'alto verso il basso.

Per raccogliere i log per Linux:
- Fare clic sull'icona Di Microsoft Teams sulla barra delle applicazioni e selezionare **Ottieni log**.
- I file saranno disponibili in `~/.config/Microsoft/Microsoft Teams/logs.txt`.

Per raccogliere i log per Mac:
- Fare clic sul menu ? in Microsoft Teams e selezionare **Raccogli file di supporto**.
- Il `logs.txt` file si troverà nella cartella Desktop all'interno della cartella _del log \<local date and time>di diagnostica di MSTeams_.

Per raccogliere i log per Windows:
- Fare clic sull'icona Di Microsoft Teams sulla barra delle applicazioni e selezionare **Raccogli file di supporto**.
- Il `logs.txt` file verrà aperto automaticamente nel Blocco note.

Durante l'analisi dei problemi di accesso a Teams, potrebbe essere necessario raccogliere manualmente i log desktop. Questi file di log si trovano in %appdata%\Microsoft\Teams in Windows.

## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)

[Log del browser e traccia per Teams](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
