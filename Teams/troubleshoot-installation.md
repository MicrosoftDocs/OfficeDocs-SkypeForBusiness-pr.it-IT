---
title: Risoluzione dei problemi di installazione e aggiornamento di Microsoft Teams in Windows
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come risolvere i problemi di installazione e aggiornamento per il client desktop Teams in Windows.
ms.openlocfilehash: d01c67c58a67ab0c52becdd54f0298ec0196704c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605855"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Risoluzione dei problemi di installazione e aggiornamento di Microsoft Teams in Windows

Questo articolo fornisce indicazioni su come diagnosticare e risolvere i problemi di installazione e aggiornamento per il client desktop Teams in esecuzione su Windows. Per altre informazioni sulla risoluzione dei problemi, vedere [risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams).

## <a name="check-whether-teams-is-updated-successfully"></a>Verificare che Teams sia stato aggiornato correttamente

Seguire questa procedura per verificare se l'aggiornamento di Teams è stato installato.

1. In Teams selezionare i puntini di sospensione (**...**) accanto all'immagine del profilo e poi fare clic su **Informazioni** > **sulla versione**. Verrà visualizzato un banner che mostra la versione di Teams corrente e la data dell'ultimo aggiornamento. Ad esempio, **possiedi Microsoft Teams versione 1.5.00.3806 (64 bit)-E. È stato aggiornato l'ultima volta il 16/02/2022**.
2. Aprire di nuovo il menu con i puntini di sospensione e fare clic su **Controlla aggiornamenti**.
3. Attendere che il banner nella parte superiore dell'app indichi che è necessario “aggiornare” Teams. Il collegamento dovrebbe venire mostrato dopo circa un minuto, il tempo necessario per scaricare la nuova versione di Teams. Il banner indica anche se si dispone già della versione più recente. In tal caso, non è necessario eseguire alcun aggiornamento.
4. Fare clic sul collegamento Aggiorna nel banner.
5. Attendere il riavvio di Teams, quindi ripetere il passaggio 1 per assicurarsi che l'app sia stata aggiornata.

Se si visualizza un messaggio di errore o se il numero della versione corrisponde a quello del passaggio 4, il processo di aggiornamento non è riuscito.

## <a name="troubleshoot-installation-and-update-issues"></a>Risoluzione dei problemi di installazione e aggiornamento

### <a name="troubleshoot-installation-issues"></a>Risoluzione dei problemi di installazione

Quando Teams è installato, il programma di installazione di Teams registra la sequenza di eventi in `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`. Per prima cosa, verificare la presenza di messaggi di errore o stack di chiamate verso la fine del log. Tenere presente che gli stack di chiamate all'inizio del log potrebbero non indicare l'esistenza di un problema di installazione. Potrebbe essere più semplice confrontare il proprio log con quello di un'installazione riuscita (anche di un altro computer) per vedere il risultato previsto.

Se `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` non indica la causa o se sono necessarie altre informazioni per risolvere il problema, vedere [Raccogliere e analizzare i log delle applicazioni e di sistema](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Risoluzione dei problemi di aggiornamento

Quando Teams viene installato correttamente, il percorso del log passa da `%LocalAppData%\SquirrelTemp` a `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`. Un altro file di log di interesse è `%AppData%\Microsoft\Teams\logs.txt`.

- Il file `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` è scritto da `Update.exe`, ovvero eseguibile che serve l'app Teams.
- Il file `%AppData%\Microsoft\Teams\logs.txt` viene usato dall'app Teams (in particolare `Teams.exe`) per registrare eventi significativi dell'applicazione. È probabile che questo contenga informazioni sugli errori.

Questi file di log contengono informazioni personali (PII), quindi non vengono inviati a Microsoft.

Il processo di aggiornamento può essere avviato automaticamente da Teams (a seconda dei criteri) oppure gli utenti possono verificare manualmente la disponibilità di aggiornamenti passando al menu con i puntini di sospensione (**...**) accanto all'immagine del profilo e selezionando **Verifica disponibilità aggiornamenti**. Entrambi i metodi usano la sequenza di eventi seguente.

1. **Controllo aggiornamenti**. Teams effettua una richiesta Web e include le informazioni sulla versione corrente dell'app e sull'anello di distribuzione. L'obiettivo di questo passaggio è ottenere il collegamento per il download. Un errore in questo passaggio viene registrato in `%AppData%\Microsoft\Teams\logs.txt`.
2. **Download dell'aggiornamento**. Teams scarica l'aggiornamento tramite il collegamento per il download ottenuto al passaggio 1. Una volta completato il download, Teams invia una chiamata a `Update.exe` per eseguire il download. Viene inoltre registrato un errore di download in `%AppData%\Microsoft\Teams\logs.txt`.
3. **Eseguire un’installazione di appoggio dell'aggiornamento**. Il contenuto scaricato viene verificato e decompresso in una cartella intermedia, `%LocalAppData%\Microsoft\Teams\stage`), che viene eseguita da `Update.exe`. Gli errori in questo passaggio vengono registrati in `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`.
4. **Installazione dell'aggiornamento**. Esistono diversi modi per avviare Teams. Il sistema avvia automaticamente Teams quando un utente accede o è possibile avviarlo manualmente tramite un collegamento. Durante questo passaggio, `Update.exe` verifica la presenza della cartella di gestione temporanea, controlla nuovamente il contenuto ed esegue le operazioni sui file per annullare l’installazione di appoggio dell'app. Della vecchia cartella dell'applicazione in `%LocalAppData%\Microsoft\Teams\current` viene eseguito il backup a `%LocalAppData%\Microsoft\Teams\previous`e la cartella di gestione temporanea viene rinominata in `current`. Gli errori in questo passaggio vengono registrati in `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`.

Se `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` o `%AppData%\Microsoft\Teams\logs.txt` non contengono informazioni sufficienti per determinare la causa sottostante e sono necessarie altre informazioni per risolvere il problema, passare a [Raccogliere e analizzare i log dell'applicazione e di sistema](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Raccogliere e analizzare i log di sistema e dell'applicazione

Questa sezione descrive come raccogliere e analizzare i log di sistema e dell'applicazione per ottenere informazioni più complete per la risoluzione del problema. Sarà necessario utilizzare gli strumenti di Sysinternals per completare questi passaggi. Per altre informazioni, vedere [Windows Sysinternals](/sysinternals/).

### <a name="collect-logs"></a>Raccolta dei log

1. Scaricare gli [strumenti di Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Estrarre il file ZIP nella cartella `%Temp%` nell'unità locale.
3. Aprire un prompt dei comandi con privilegi elevati ed eseguire le operazioni seguenti:

    1. Per passare alla cartella `%Temp%`, eseguire il comando seguente:

        ```console
        cd /d %Temp%
        ```

    2. Copiare i log della configurazione e dell’applicazione. A seconda del punto di errore, alcuni di questi log potrebbero non essere presenti.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```

    3. Eseguire il comando seguente per acquisire gli handle aperti.

        ```console
        handle > handles.txt
        ```

    4. Eseguire il comando seguente per acquisire le DLL aperte

        ```console
        listdlls -v Teams > dlls.txt
        ```

    5. Eseguire il comando seguente per acquisire i driver in esecuzione.

        ```console
        driverquery /v > driverquery.txt
        ```

    6. Eseguire il comando seguente per acquisire gli elenchi di controllo di accesso (ACL) della cartella di Teams.

        ```console
        icacls %LocalAppData%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analisi dei log (per utenti esperti)

Un aggiornamento non riuscito può causare un comportamento imprevedibile dell'app. Ad esempio, gli utenti potrebbero non poter uscire da Teams, avere una versione non aggiornata o non riuscire ad avviare Teams. Se si verifica un problema durante un aggiornamento, il primo posto in cui cercare la causa è `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`. Di seguito sono indicati i diversi tipi di errore di aggiornamento (elencati dal più comune al più raro) e i metodi per analizzarli e risolverli tramite i log.

#### <a name="unable-to-exit-teams"></a>Chiusura di Teams non consentita

Quando Teams deve essere aggiornato a una versione più recente, viene scaricata ed eseguita un’installazione di appoggio della nuova app. Il riavvio viene eseguito non appena il computer è inattivo. Un problema comune durante questo processo è quando un altro processo o un driver file system blocca il processo di `Teams.exe`, impedendo così la chiusura di `Teams.exe`. Di conseguenza, l'app Teams non può essere sostituita dall'app appena scaricata e per la quale è stata eseguita un’installazione di appoggio.

Suggerimenti per la risoluzione del problema:

- Per confermare che si tratti del problema riscontrato, chiudere Teams (fare clic con il pulsante destro del mouse su Teams nella barra delle applicazioni e quindi selezionare **Esci**). Aprire Gestione attività in Windows per controllare se sono presenti istanze di Teams ancora in esecuzione.  
- Se non si sta utilizzando il computer in cui si è riscontrato il problema, esaminare il file `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` raccolto dal computer in cui si è verificato e cercare la voce **Programma: non è possibile terminare il processo nel log**.
- Per determinare cosa impedisce l'uscita di `Teams.exe`, esaminare i log `Dlls.txt` e `Handles.txt` creati nella sezione [Raccogli log](#collect-logs). Questi indicheranno i processi che impediscono la chiusura di Teams.
- Un'altra causa che potrebbe impedire la chiusura di Teams potrebbe essere il driver del filtro del file system in modalità kernel. Usare [ProcDump](/sysinternals/downloads/procdump), uno strumento di SysInternals, per raccogliere i dettagli del processo in modalità kernel eseguendo `procdump -mk <pid>`, dove \<pid> è l'ID processo ottenuto tramite Gestione attività. Puoi anche esaminare il file di log `Driverquery.txt` per vedere i driver attivi del filtro che potrebbero interferire con Teams.
- Per risolvere il problema, riavviare il computer.

#### <a name="file-permissions"></a>Autorizzazioni per i file

Teams crea diverse sottocartelle e file nel profilo dell'utente durante il processo di installazione e aggiornamento. Poiché l'app e lo strumento di aggiornamento vengono eseguiti come utente senza privilegi elevati, le autorizzazioni di lettura e scrittura devono venire concesse nelle cartelle seguenti:

|Cartella  |In uso da  |
|---------|---------|
|`%LocalAppData%\SquirrelTemp`    | Programma di installazione di Teams (ad esempio `Teams_Windows_x64.exe`), durante la fase di installazione        |
|`%LocalAppData%\Microsoft\Teams`  | Strumento di aggiornamento di Teams (`Update.exe`), per estrarre ed eseguire un’installazione di appoggio dell’app durante il processo di aggiornamento        |
|`%AppData%\Microsoft\Teams`   |  Teams app (`Teams.exe`) per salvare le impostazioni, gli stati dell'app e il pacchetto di aggiornamento (preconfigurato) scaricato       |

Se a Teams viene negato l'accesso perché non autorizzato a scrivere in un file, è possibile che sia un'altra applicazione software ad interferire oppure che la voce di un descrittore di sicurezza stia limitando l'accesso in scrittura a una cartella.

Suggerimenti per la risoluzione del problema:

- Cerca prova `access denied` in `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` o `%AppData%\Microsoft\Teams\logs.txt`. Controllare questi file per verificare la presenza di un tentativo di scrittura non riuscito in un file.
- Aprire `Icacls.txt` e cercare la voce di controllo di accesso (ACE) in funzione che blocca le operazioni di scrittura di un utente non amministratore. In genere, si tratta di una delle voci del DACL. Per altre informazioni, vedere la [documentazione di icacls](/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>File danneggiato

In alcuni casi, il software di crittografia può cambiare i file della cartella `%LocalAppData%\Microsoft\Teams`, impedendo l'avvio di Teams. Ciò può verificarsi in qualsiasi momento, anche quando l'app non è in corso di aggiornamento. Quando un file viene danneggiato, l'unico modo per risolvere il problema è disinstallare e reinstallare Teams.

> [!NOTE]
> Se non è possibile determinare la causa del problema tramite uno di questi passaggi, potrebbe essere necessaria una sessione di [Process Monitor](/sysinternals/downloads/procmon). Process Monitor è uno strumento di Sysinternals che registra l'accesso al file system e al Registro di sistema.

## <a name="related-topics"></a>Argomenti correlati

- [Ottenere i client per Microsoft Teams](get-clients.md)
- [Aggiornamenti del client di Teams](teams-client-update.md)
- [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
