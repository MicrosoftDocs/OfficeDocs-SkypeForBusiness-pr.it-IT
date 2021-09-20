---
title: Usare i file di log nella risoluzione dei Microsoft Teams
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
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove possono essere trovati e su come possono essere utili per il monitoraggio e la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a82b2e9fe2db41e0609b7483bded813eae29cf92
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456526"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Usare i file di log per monitorare e risolvere i Microsoft Teams

Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per facilitare il monitoraggio e la risoluzione dei Teams:

-   [Log di debug](#debug-logs)

-   [Registri multimediali](#media-logs)

-   [Log del desktop](#desktop-logs)

Questo articolo descrive questi log e come vengono usati. Per informazioni sulla risoluzione di problemi specifici, vedere: Teams [risoluzione dei problemi](/MicrosoftTeams/troubleshoot/teams). Per informazioni su come contattare il supporto, vedere [Ottenere supporto.](/microsoft-365/business-video/get-help-support) Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug. Avere a disposizione i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema. **I** registri multimediali **o desktop** sono necessari solo se richiesti da Microsoft.

> [!NOTE]
> In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi. Tuttavia, i file generati per questi log conterranno il termine **log di diagnostica** nei nomi.  

## <a name="collect-and-enable-logging"></a>Raccogliere e abilitare la registrazione

È importante raccogliere i log non appena si verifica un problema. I log possono essere raccolti insieme con un paio di clic.

Windows: fare clic con il pulsante destro del mouse sull'icona Teams sulla barra delle applicazioni e scegliere **Raccolta file di supporto.** 

Mac: selezionare il menu ? e scegliere **Raccogli file di supporto.**


I log di debug, desktop e multimediali verranno raccolti in un'unica cartella con il nome MSTeams Diagnostics <local data and time> Log. Questa cartella può essere compressa e condivisa quando si apre una richiesta di supporto con il supporto tecnico Microsoft. La cartella conterrà cartelle per Desktop, Riunione (elementi multimediali) e Debug (Web). È possibile raccogliere i file usando le scelte rapide da tastiera seguenti:

Windows: CTRL + ALT + MAIUSC + 1

Mac: OPZIONE+ COMANDO + MAIUSC + 1


La registrazione multimediale è disattivata per impostazione predefinita. Per abilitare la registrazione multimediale, gli utenti devono attivare l'opzione nel client Teams dati. Passare a **Impostazioni** Generale e selezionare Abilita registrazione per diagnostica riunione  >   **(è necessario riavviare Teams).** Il Teams client deve essere riavviato per avviare la registrazione.

Se si verifica un problema con una riunione o un evento live specifico, è utile avere l'URL associato alla riunione. In questo modo vengono fornite informazioni aggiuntive che consentono di individuare l'esatta riunione o l'evento live nei log. Queste informazioni possono essere raccolte da qualsiasi partecipante per una riunione o da un relatore o un produttore per un evento live. Questo URL può essere acquisito passando il puntatore del mouse sull'URL di join e scegliendo **Copia collegamento ipertestuale.**

> [!NOTE]
> Se la registrazione multimediale è abilitata, nella cartella Riunione saranno inclusi altri file necessari per analizzare i problemi audio e video. Se la registrazione multimediale non è abilitata, sarà disponibile un numero limitato di log.
  
> [!NOTE]
> I log di debug venivano raccolti in precedenza usando le scelte rapide da tastiera seguenti. Queste funzioni funzionano ancora e completeranno la stessa acquisizione del log **dell'opzione Raccogli file di** supporto.

> Windows: Crtl + ALT + MAIUSC + 1

> Mac: OPZIONE+ COMANDO + MAIUSC + 1


La tabella seguente descrive i vari client e i log associati. I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.


|Client |Debug|Desktop|Elementi multimediali|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Per un elenco completo dei sistemi operativi e dei browser supportati, vedere [Ottenere i client per Microsoft Teams](get-clients.md).

## <a name="debug-logs"></a>Log di debug

Vedere la _sezione Raccogliere e abilitare la registrazione_ per Windows istruzioni per Mac. I log di debug vengono prodotti dai client desktop Windows e Mac, oltre che dai client basati su browser. I log sono basati su testo e vengono letti dal basso verso l'alto. Possono essere letti con qualsiasi editor basato su testo e i nuovi log vengono creati quando si accede al client.

I log di debug mostrano i flussi di dati seguenti:

-   Accesso

-   Richieste di connessione a servizi di livello intermedio

-   Chiamata/conversazione

Per raccogliere log per Linux: Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1 I file saranno disponibili in ~/Downloads

Per raccogliere i log per il browser: Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1 I file saranno disponibili in %userprofile%\Downloads

## <a name="media-logs"></a>Registri multimediali

Vedere la _sezione Raccogliere e abilitare la registrazione_ per Windows istruzioni per Mac. I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle Teams riunioni. Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.

La registrazione multimediale è disattivata per impostazione predefinita. Per registrare i dati di diagnostica Teams riunioni, gli utenti devono attivare l'opzione nel client Teams. Passare a **Impostazioni** Generale , selezionare la casella di controllo Abilita registrazione per diagnostica riunione (è necessario riavviare Teams ), riavviare Teams e riprodurre  >  il problema.  

Quando si inviano i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log copriranno l'intervallo di tempo in cui è stato riprodotto il problema.

Per raccogliere log per Linux: i file saranno disponibili in ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog e *~/.config/Microsoft/Microsoft Teams/skylib/*.blog.

Ecco un elenco dei file di log generati e delle informazioni che contengono.

|Nome file di log  |Descrizione  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Contiene informazioni correlate allo stack multimediale. Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su video e fotocamera (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora quando viene fornito il controllo, e le informazioni sul puntatore del mouse.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Registra gli eventi di traccia dello stack multimediale.         |
|Debug-0-s2790420889.blog    | Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.          |
|tscalling-0-2061129496.blog   |Registra gli eventi nell'API ts-calling.       |

## <a name="desktop-logs"></a>Log del desktop

Vedere la _sezione Raccogliere e abilitare la registrazione_ per Windows istruzioni per Mac. I log desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser. Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft. I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato dall'alto verso il basso.

Per raccogliere i log per Linux: fare clic sull'icona Microsoft Teams sulla barra delle applicazioni e selezionare **Recupera registri**.
I file saranno disponibili in ~/.config/Microsoft/Microsoft Teams/logs.txt.  

## <a name="browser-trace"></a>Traccia del browser

Per alcune categorie di errori, il supporto Tecnico Microsoft potrebbe richiedere la raccolta di una traccia del browser. Queste informazioni possono fornire dettagli importanti sullo stato del client Teams client quando si verifica l'errore.

Prima di avviare la traccia del browser, assicurarsi di aver eseguito l'accesso a Teams. È importante eseguire questa operazione prima di avviare la traccia in modo che la traccia non contenga informazioni di accesso riservate.

Dopo aver eseguito l'accesso, selezionare uno dei collegamenti seguenti, in base alle esigenze del browser, e seguire la procedura fornita. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Nei passaggi sostituire tutti i riferimenti al portale di Azure con il Teams client.
  
## <a name="webrtc-logs-in-browsers"></a>Log WebRTC nei browser
I log WebRTC possono aiutare il supporto Microsoft fornendo i dettagli della connessione per le chiamate audio e video. Seguire la procedura per accedere ai log di WebRTC in Edge (Chromium) o Chrome: 
  
1.  Aprire una nuova scheda e passare a uno degli URL seguenti:
    -   Edge (Chromium): "edge://webrtc-internals/"
    -   Chrome: "chrome://webrtc-internals/"
  
2.  Aprire l'Teams Web e riprodurre il problema.
  
3.  Tornare alla scheda a cui è stato eseguito l'accesso nel passaggio 1 e verranno visualizzate almeno due schede:
    -   Richieste GetUserMedia
    -   https://teams.microsoft.com/url

4.  Scegliere la scheda con il nome dell'applicazione Teams e salvare il contenuto della pagina.

## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
