---
title: Usare i file di log per la risoluzione dei problemi di Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove è possibile trovarne i file e su come possono essere utili per la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761094"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usare i file di log per la risoluzione dei problemi di Microsoft Teams
=================================================

Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per agevolare la risoluzione dei problemi di Microsoft Teams:

-   Log di debug

-   Log multimediali

-   Log del desktop

Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug. Avere a portata di mano i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema. **I** log multimediali **o desktop** sono necessari solo se richiesti da Microsoft.

> [!NOTE]
> In questo articolo il termine **log di debug fa** riferimento ai log usati per la risoluzione dei problemi. Tuttavia, i file generati per questi log conterranno i termini **log diagnostici** nei loro nomi.  

La tabella seguente illustra i vari client e i log associati. I file di log sono archiviati in posizioni specifiche del client e del sistema operativo.


|Client |Debug|Desktop|Elementi multimediali|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Per un elenco completo dei sistemi operativi e dei browser supportati, vedere [Ottenere i client per Microsoft Teams.](get-clients.md)

<a name="debug-logs"></a>Log di debug
---------------------------

Si tratta dei log più comuni e sono necessari per tutti i casi di supporto Tecnico Microsoft. I log di debug vengono prodotti dai client desktop Windows e Mac, nonché dai client basati su browser. I log sono basati su testo e vengono letti dal basso verso l'alto. Possono essere letti con qualsiasi editor basato su testo e vengono creati nuovi log quando si accede al client.

I log di debug mostrano i flussi di dati seguenti:

-   Accesso

-   Richieste di connessione ai servizi di livello intermedio

-   Chiamata/conversazione

I log di debug vengono prodotti usando i metodi specifici del sistema operativo seguenti:

-   Windows:

      Scelta rapida da tastiera: CTRL + ALT + MAIUSC + 1

-   Mac OSX:

      Scelta rapida da tastiera: OPZIONE+COMANDO+MAIUSC+1

-   Linux:

      Scelta rapida da tastiera: CTRL + ALT + MAIUSC + 1

I log di debug vengono scaricati automaticamente nelle cartelle seguenti:

-   Windows: %userprofile% \\ Download

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita

<a name="media-logs"></a>Log multimediali
---------------------------

I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle riunioni di Teams. Sono obbligatori per i casi di supporto collegati a problemi correlati alle chiamate.

La registrazione multimediale è disattivata per impostazione predefinita. Per registrare i dati di diagnostica per le riunioni di Teams, gli utenti devono attivare l'opzione nel client di Teams. Vai a **Impostazioni** generali, seleziona la casella di controllo Attiva registrazione per la diagnostica delle riunioni (richiede il riavvio di Teams), riavvia  >  Teams e riproduci il problema.  

La tabella seguente illustra i percorsi dei log multimediali. Quando si inviano i file di log al supporto Microsoft, verificare la data e l'ora dei file di log per assicurarsi che coprono l'intervallo di tempo durante il periodo in cui è stato riprodotto il problema.

|Client |Posizione |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Ecco un elenco dei file di log generati e delle informazioni in essi contenute.

|Nome file di log  |Descrizione  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Contiene informazioni correlate allo stack multimediale. Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione schermo basata su video e fotocamera.         |
|rtmcontrol.msrtc-0-2415069487.blog      |Registra informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore di data e ora quando viene assegnato il controllo e le informazioni del puntatore del mouse.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Registra gli eventi di traccia dello stack multimediale.         |
|Debug-0-s2790420889.blog    | Contiene informazioni relative all'agente multimediale, inclusa la qualità di rendering.          |
|tscalling-0-2061129496.blog   |Registra gli eventi nell'API per la chiamata ts.       |

<a name="desktop-logs"></a>Log del desktop
---------------------

I log desktop, noti anche come log del programma di avvio automatico, contengono dati di log che si verificano tra il client desktop e il browser. Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft. I log sono basati sul testo e possono essere letti usando qualsiasi editor basato su testo in formato dall'alto verso il basso.

Windows:

 - Fare clic con il pulsante **destro del mouse sull'icona** di Microsoft Teams sulla barra delle applicazioni e scegliere Ottieni **registri.**

Mac OsX:

 - Scegliere **Ottieni registri** dal menu **a** discesa?

Linux:

 - Fare clic **sull'icona di Microsoft Teams** sulla barra delle applicazioni e selezionare Ottieni **registri.**

|Client |Posizione |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
