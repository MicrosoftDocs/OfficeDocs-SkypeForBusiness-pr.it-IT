---
title: Usare i file di log nella risoluzione dei problemi di Microsoft Teams
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
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove possono essere trovati e su come possono essere utili per la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112192"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usare i file di log nella risoluzione dei problemi di Microsoft Teams
=================================================

Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per facilitare la risoluzione dei problemi di Microsoft Teams:

-   Log di debug

-   Registri multimediali

-   Log del desktop

Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug. Avere a disposizione i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema. **I** log **multimediali o desktop** sono necessari solo se richiesti da Microsoft.

> [!NOTE]
> In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi. Tuttavia, i file generati per questi log conterranno il termine **log di diagnostica** nei nomi.  

La tabella seguente descrive i vari client e i log associati. I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.


|Client |Debug|Desktop|Elementi multimediali|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Per un elenco completo dei sistemi operativi e dei browser supportati, vedere [Ottenere client per Microsoft Teams.](get-clients.md)

<a name="debug-logs"></a>Log di debug
---------------------------

Questi sono i log più comuni e sono necessari per tutti i casi di supporto Tecnico Microsoft. I log di debug vengono prodotti dai client desktop Windows e Mac, oltre che dai client basati su browser. I log sono basati su testo e vengono letti dal basso verso l'alto. Possono essere letti con qualsiasi editor basato su testo e i nuovi log vengono creati quando si accede al client.

I log di debug mostrano i flussi di dati seguenti:

-   Accesso

-   Richieste di connessione a servizi di livello intermedio

-   Chiamata/conversazione

I log di debug vengono prodotti usando i metodi specifici del sistema operativo seguenti:

-   Windows:

      Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1

-   Mac OSX:

      Scelta rapida da tastiera: OPZIONE+COMANDO+MAIUSC+1

-   Linux:

      Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1

I log di debug vengono scaricati automaticamente nelle cartelle seguenti:

-   Windows: download di %userprofile% \\

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   Browser: verrà chiesto di salvare il log di debug nel percorso di salvataggio predefinito

<a name="media-logs"></a>Registri multimediali
---------------------------

I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle riunioni di Teams. Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.

La registrazione multimediale è disattivata per impostazione predefinita. Per registrare i dati di diagnostica per le riunioni di Teams, gli utenti devono attivare l'opzione nel client Teams. Passare a **Impostazioni** generali, selezionare la casella di controllo Abilita registrazione per diagnostica riunione (richiede il riavvio di  >   **Teams),** riavviare Teams e riprodurre il problema. 

La tabella seguente descrive le posizioni dei log multimediali. Quando si inviano i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log copriranno l'intervallo di tempo in cui è stato riprodotto il problema.

|Client |Posizione |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Ecco un elenco dei file di log generati e delle informazioni che contengono.

|Nome file di log  |Descrizione  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Contiene informazioni correlate allo stack multimediale. Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su video e fotocamera (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora quando viene fornito il controllo, e le informazioni sul puntatore del mouse.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Registra gli eventi di traccia dello stack multimediale.         |
|Debug-0-s2790420889.blog    | Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.          |
|tscalling-0-2061129496.blog   |Registra gli eventi nell'API ts-calling.       |

<a name="desktop-logs"></a>Log del desktop
---------------------

I log desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser. Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft. I log sono basati su testo e possono essere letti con qualsiasi editor basato su testo in un formato dall'alto verso il basso.

Windows:

 - Fare clic con il pulsante **destro del mouse sull'icona di Microsoft Teams** nella barra delle applicazioni e scegliere Ottieni **log.**

Mac OsX:

 - Scegliere **Ottieni log** dal menu **a** discesa ?

Linux:

 - Fare clic **sull'icona di Microsoft Teams** nell'area di notifica e selezionare Ottieni **log.**

|Client |Posizione |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)