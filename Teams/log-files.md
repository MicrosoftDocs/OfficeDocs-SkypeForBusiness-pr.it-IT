---
title: Usare i file di log in risoluzione dei problemi di Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
description: Informazioni sui registri di debug, multimediali e desktop prodotti da Microsoft teams, dove possono essere trovati e come possono essere utili per la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2303082c4f1c16a28a9116047d904a5d491a535a
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085752"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usare i file di log in risoluzione dei problemi di Microsoft Teams
=================================================

Ci sono tre tipi di file di log prodotti automaticamente dal client che possono essere sfruttati per facilitare la risoluzione dei problemi di Microsoft teams.

-   Log di debug

-   Registri multimediali

-   Registri desktop

Quando si crea una richiesta di supporto con il supporto Microsoft, il tecnico del supporto richiederà i registri di debug. La presenza di questi log a mano prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente la risoluzione del problema. Gli elementi multimediali o i registri desktop sono necessari solo se richiesti da Microsoft.

La tabella seguente descrive i diversi client e i registri associati. I file di log sono archiviati in posizioni specifiche per il client e il sistema operativo.


|Client |Debug|Desktop|Elementi multimediali|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Per un elenco completo di sistemi operativi e browser supportati, vedere [ottenere client per Microsoft teams](get-clients.md).

<a name="debug-logs"></a>Log di debug
---------------------------

Questi sono i registri più comuni e sono necessari per tutti i casi di supporto Microsoft. I log di debug vengono prodotti dai client desktop Windows e Mac, oltre ai client basati su browser. I log sono basati su testo e vengono letti dal basso verso l'alto. Possono essere lette usando qualsiasi editor basato su testo e vengono creati nuovi log durante l'accesso al client.

I registri di debug mostrano i flussi di dati seguenti:

-   Accesso

-   Richieste di connessione ai servizi di livello intermedio

-   Chiamata/conversazione

I log di debug vengono prodotti usando i seguenti metodi specifici per il sistema operativo:

-   Windows

      Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1

-   Mac OSX:

      Tasto di scelta rapida: opzione + comando + MAIUSC + 1

-   Linux

      Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1

I log di debug vengono scaricati automaticamente nelle cartelle seguenti.

-   Windows:% UserProfile% \\ download

-   Mac OSX: download

-   Linux: ~/Downloads

-   Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita

<a name="media-logs"></a>Registri multimediali
---------------------------

I registri multimediali contengono dati di diagnostica relativi alla condivisione audio, video e dello schermo. Sono necessari per i casi di supporto solo su richiesta e possono essere controllati solo da Microsoft. La tabella seguente illustra la posizione del log.


|Client |Posizione |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. Blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. Blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *. etl         |
|Mac OSX     |~/Libreria/Application Support/Microsoft/teams/media-stack/*. Blog         |
|            |~/Libreria/Application Support/Microsoft/teams/skylib/*. Blog         |
|Linux       |~/.config/Microsoft/Microsoft teams/media-stack/*. Blog         |
|            |~/.config/Microsoft/Microsoft teams/skylib/*. Blog         |



<a name="desktop-logs"></a>Registri desktop
---------------------

I registri desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser. Come i registri multimediali, questi registri sono necessari solo se richiesti da Microsoft. I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato top-down.

Windows

1.  Fare clic con il pulsante destro del mouse sull'icona di **Microsoft teams** nella barra delle applicazioni, selezionare **Ottieni log**

Mac OsX:

1.  Scegliere **Get logs** dal menu a discesa della **Guida**

Linux

1.  Fare clic sull'icona **Microsoft teams** nella barra delle applicazioni, selezionare **Get logs**

|Client |Posizione |
|---------|---------|
|Windows     |% AppData% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Libreria/Application Support/Microsoft/teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft teams/logs.txt         |


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

