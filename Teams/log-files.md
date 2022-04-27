---
title: Usare i file di log nella risoluzione dei problemi di Microsoft Teams
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
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove sono disponibili e su come possono essere utili per il monitoraggio e la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d8e3ab079498ecfca11a7d2ba48736aaf457329
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059107"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Usare i file di log per monitorare e risolvere Microsoft Teams

Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere usati per assistere nel monitoraggio e nella risoluzione dei problemi Teams:

-   [Eseguire il debug dei log](#debug-logs)

-   [Registri multimediali](#media-logs)

-   [Log desktop](#desktop-logs)

Questo articolo descrive questi log e come vengono usati. Per informazioni sulla risoluzione di problemi specifici, vedere: [Teams Risoluzione dei problemi](/MicrosoftTeams/troubleshoot/teams). Per informazioni su come contattare il supporto tecnico, vedere [Ottenere supporto](/microsoft-365/business-video/get-help-support). Quando si crea una richiesta di supporto con supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug. Avere a portata di mano i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di avviare rapidamente la risoluzione del problema. **I log multimediali** o **desktop** sono necessari solo se richiesto da Microsoft.

> [!NOTE]
> In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi. Tuttavia, i file generati per questi log conterranno i **termini log diagnostici** nei loro nomi.  

## <a name="collect-and-enable-logging"></a>Raccogliere e abilitare la registrazione

È importante raccogliere i log non appena si verifica un problema. I log possono essere raccolti insieme con un paio di clic.

- Windows: fai clic con il pulsante destro del mouse sull'icona Teams sulla barra delle applicazioni e scegli **Raccogli file di supporto**. 

- Mac: selezionare il menu ? e scegliere **Raccogli file di supporto**.

I log di debug, desktop e multimediali verranno raccolti in un'unica cartella con il nome _MsTeams Diagnostics Log \<local date and time\>_. Questa cartella può essere compressa e condivisa quando apri una richiesta di supporto con supporto tecnico Microsoft. La cartella conterrà le cartelle Desktop, Riunione (elementi multimediali) e Debug (Web). È possibile raccogliere i file usando le scelte rapide da tastiera seguenti:

- Windows: <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>

- Mac: <kbd>Opzione</kbd> + <kbd>Comando</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>


La registrazione multimediale è attivata per impostazione predefinita solo per alcune CPU, descritte nei [log multimediali](#media-logs). In caso contrario, è disattivato per impostazione predefinita. Per abilitare la registrazione multimediale, gli utenti devono attivare l'opzione nel client Teams. Passare a **Impostazioni** **General** e selezionare **Abilita registrazione per la diagnostica delle riunioni (è necessario riavviare Teams).** Go to Impostazioni  >  General, and select Enable logging for meeting diagnostics (requires restarting Teams). Per avviare la registrazione, è necessario riavviare il client Teams facendo clic con il pulsante destro del mouse sull'icona nel Dock (Mac) o nella barra delle applicazioni (Windows) e selezionando **Esci**. Dopo aver chiuso, fai clic sull'icona dell'app per aprirla di nuovo).

Se si verifica un problema con una riunione o un evento live specifico, è utile avere l'URL associato alla riunione. In questo modo vengono fornite informazioni aggiuntive per identificare la riunione esatta o l'evento live nei log. Queste informazioni possono essere raccolte da qualsiasi partecipante per una riunione o dal relatore o produttore per un evento live. Questo URL può essere acquisito passando il puntatore sull'URL del join e scegliendo **Copia collegamento ipertestuale**.

> [!NOTE]
> Se la registrazione multimediale è abilitata, nella cartella Riunione saranno inclusi altri file necessari per l'analisi di problemi audio e video. Se la registrazione multimediale non è abilitata, sarà disponibile un numero limitato di log.
  
> [!NOTE]
> I log di debug venivano raccolti in precedenza usando le scelte rapide da tastiera seguenti. Questi continuano a funzionare e completeranno la stessa acquisizione del log dell'opzione **Raccogli file di supporto** .
>
> - Windows: <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Opzione</kbd> + <kbd>Comando</kbd> + <kbd>MAIUSC</kbd> + <kbd>1</kbd>


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

Per istruzioni su Windows e Mac, vedere la sezione _Raccogliere e abilitare la registrazione_. I log di debug vengono prodotti dai client desktop di Windows e Mac, nonché dai client basati su browser. I log sono basati su testo e vengono letti dal basso verso l'alto. Possono essere letti usando qualsiasi editor basato su testo e vengono creati nuovi log quando si accede al client.

I log di debug mostrano i flussi di dati seguenti:

-   Login

-   Richieste di connessione ai servizi di livello intermedio

-   Chiamata/conversazione

Per raccogliere i log per Linux:
- Scelta rapida da tastiera: <kbd>CTRLAltShift1</kbd> + <kbd></kbd> + <kbd></kbd> + <kbd></kbd>  
- I file saranno disponibili in `~/Downloads`

Per raccogliere i log per Browser e Windows:
- Scelta rapida da tastiera: <kbd>CTRLAltShift1</kbd> + <kbd></kbd> + <kbd></kbd> + <kbd></kbd>  
- I file saranno disponibili in `%userprofile%\Downloads`

## <a name="media-logs"></a>Registri multimediali

Per istruzioni su Windows e Mac, vedere la sezione _Raccogliere e abilitare la registrazione_. I log multimediali contengono dati diagnostici su audio, video e condivisione dello schermo durante Teams riunioni. Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.

La registrazione multimediale è attivata per impostazione predefinita per i computer in cui la CPU è:
- qualsiasi Apple M1
- qualsiasi Intel Xeon
- qualsiasi Intel i9, ad eccezione delle serie U, G7, M e MQ
- qualsiasi 6a generazione e successive Intel i7, ad eccezione delle serie U, G7, M e MQ

In caso contrario, è disattivato per impostazione predefinita. Per registrare i dati di diagnostica per Teams riunioni, gli utenti devono attivare l'opzione nel client Teams. Passare a **Impostazioni** >  **General**, selezionare la casella di controllo **Abilita registrazione per diagnostica riunioni (è necessario riavviare Teams**), riavviare Teams e riprodurre il problema. 

> [!NOTE]
> Quando ci si disconnette da Teams, la registrazione multimediale viene reimpostata come predefinita. 

Quando si inviano i file di log al supporto microsoft, verificare il timestamp dei file di log per assicurarsi che i log coprano l'intervallo di tempo durante la riproduzione del problema.

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

Per istruzioni su Windows e Mac, vedere la sezione _Raccogliere e abilitare la registrazione_. I log desktop, noti anche come log del bootstrapper, contengono dati di log che si verificano tra il client desktop e il browser. Analogamente ai log multimediali, questi log sono necessari solo se richiesti da Microsoft. I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato dall'alto verso il basso.

Per raccogliere i log per Linux:
- Fare clic sull'icona Microsoft Teams sulla barra delle applicazioni e selezionare **Ottieni log**.
- I file saranno disponibili in `~/.config/Microsoft/Microsoft Teams/logs.txt`.
  
Per raccogliere i log per Windows:
- Fai clic sull'icona Microsoft Teams sulla barra delle applicazioni e seleziona **Raccogli file di supporto**.
- Il `logs.txt` file verrà aperto automaticamente in Blocco note.

Durante l'analisi dei problemi di accesso a Teams, potrebbe essere necessario raccogliere manualmente i log desktop. Questi file di log si trovano in %appdata%\Microsoft\Teams in Windows.

## <a name="browser-trace"></a>Traccia browser

Per alcune categorie di errori, supporto tecnico Microsoft potrebbe richiedere la raccolta di una traccia del browser. Queste informazioni possono fornire dettagli importanti sullo stato del client Teams quando si verifica l'errore.

Prima di avviare la traccia del browser, verificare di avere eseguito l'accesso a Teams. È importante eseguire questa operazione prima di avviare la traccia in modo che non contenga informazioni di accesso riservate.

Dopo aver eseguito l'accesso, seleziona uno dei collegamenti seguenti, in base alle esigenze del browser, e segui i passaggi forniti. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Bordo](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Nei passaggi sostituire tutti i riferimenti alla portale di Azure con il client Teams.
  
## <a name="webrtc-logs-in-browsers"></a>Log di WebRTC nei browser
I log di WebRTC possono aiutare supporto tecnico Microsoft fornendo dettagli di connessione per le chiamate audio e video. Segui i passaggi per accedere ai log di WebRTC in Edge (Chromium) o Chrome: 
  
1.  Aprire una nuova scheda e passare a uno degli URL seguenti:
    -   Edge (Chromium):`edge://webrtc-internals/`
    -   Chrome: `chrome://webrtc-internals/`
  
2.  Apri l'applicazione Web Teams e riproduci il problema.
  
3.  Indietro alla scheda a cui è stato eseguito l'accesso nel passaggio 1 e verranno visualizzate almeno due schede:
    -   Richieste GetUserMedia
    -   `https://teams.microsoft.com/url`

4.  Scegliere la scheda con il nome dell'applicazione Teams e salvare il contenuto della pagina.

## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
