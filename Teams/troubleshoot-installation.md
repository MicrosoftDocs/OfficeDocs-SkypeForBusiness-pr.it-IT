---
title: Risolvere i problemi di installazione e aggiornamento di Microsoft teams in Windows
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come risolvere i problemi di installazione e aggiornamento per l'app client desktop teams in Windows.
ms.openlocfilehash: 812beb3471a1d4ee2cbc1e8e7f7b36b2a42e0e2d
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39920152"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Risolvere i problemi di installazione e aggiornamento di Microsoft teams in Windows

Questo articolo fornisce indicazioni su come diagnosticare e risolvere i problemi di installazione e aggiornamento per l'app client desktop teams in uso in Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Verificare se i team vengono aggiornati correttamente

Seguire questa procedura per verificare se un aggiornamento di teams è stato installato correttamente.

1. In teams selezionare l'immagine del profilo e quindi fare clic **su informazioni sulla** > **versione**.
2. Nello stesso menu fare clic su **Controlla aggiornamenti**.
3. Aspetta che il banner nella parte superiore dell'app indichi che è necessario un "aggiornamento" dei team. Il collegamento dovrebbe essere visualizzato circa un minuto dopo che questo processo Scarica la nuova versione di teams. Lo striscione consente anche di sapere se si sta già usando la versione più recente, in questo caso, non è necessario alcun aggiornamento.
4. Fare clic sul collegamento Aggiorna nell'intestazione.
5. Attendere che i team vengano riavviati e quindi ripetere il passaggio 1 per verificare se l'app viene aggiornata.

Se viene visualizzato un messaggio di errore o se il numero di versione è uguale a quello del passaggio 4, il processo di aggiornamento non è riuscito.

## <a name="troubleshoot-installation-and-update-issues"></a>Risolvere i problemi di installazione e aggiornamento

### <a name="troubleshoot-installation-issues"></a>Risolvere i problemi di installazione

Quando si installa teams, il programma di installazione di teams registra la sequenza di eventi in%LocalAppData%\SquirrelTemp\SquirrelSetup.log. La prima cosa da cercare è un messaggio di errore o uno stack di chiamate vicino alla fine del log. Tieni presente che gli stack di chiamate all'inizio del log potrebbero non significare che esiste un problema di installazione. Può essere più semplice confrontare il log con il log da un'installazione corretta (anche in un altro computer) per vedere cosa ci si aspetta.

Se SquirrelSetup. log non indica la causa o se sono necessarie altre informazioni per risolvere il problema, vedere [raccogliere e analizzare i registri delle applicazioni e di sistema](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Risolvere i problemi di aggiornamento

Quando i team vengono installati correttamente, la posizione del log passa da%LocalAppData%\SquirrelTemp a%AppData%\Microsoft\Teams. In questa posizione sono presenti due file di log di interesse, SquirrelSetup. log e logs. txt.

- Il file SquirrelSetup. log in questa posizione è scritto da Update. exe, che è un eseguibile che assiste l'app teams.
- Il file logs. txt viene usato dall'app Teams (in particolare teams. exe) per registrare eventi applicativi significativi. Probabilmente includerà informazioni di errore.

Questi file di log contengono informazioni personali e quindi non vengono inviate a Microsoft.

I team possono avviare automaticamente il processo di aggiornamento (a seconda dei criteri) oppure gli utenti possono verificare manualmente la disponibilità degli aggiornamenti accedendo alla propria immagine del profilo > **verificare la disponibilità di aggiornamenti**. Entrambi i metodi usano la sequenza di eventi seguente.

1. **Verificare la disponibilità di aggiornamenti**. Teams effettua una richiesta Web e include le informazioni correnti sulla versione dell'app e sul ring di distribuzione. L'obiettivo di questo passaggio è ottenere il collegamento per il download. Un errore in questo passaggio viene registrato in logs. txt.
2. **Scarica aggiornamento**. Teams Scarica l'aggiornamento usando il collegamento per il download ottenuto dal passaggio 1. Al termine del download, teams chiama Update. exe per organizzare il download. Un errore di download viene registrato anche in logs. txt.
3. **Organizzare l'aggiornamento**. Il contenuto scaricato viene verificato e scompattato in una cartella intermedia,%LocalAppData%\Microsoft\Teams\stage), che viene eseguita da Update. exe. Gli errori di questo passaggio vengono registrati in SquirrelTemp. log.
4. **Installare l'aggiornamento**. Sono disponibili diversi modi per avviare teams. Il sistema avvia automaticamente i team quando un utente accede o si può avviare teams tramite un collegamento. In questo passaggio, Update. exe controlla la presenza della cartella di gestione temporanea, verifica di nuovo il contenuto e esegue le operazioni sui file per annullare la fase dell'app. La cartella dell'applicazione precedente in%LocalAppData%\Microsoft\Teams\current viene eseguito il backup in%LocalAppData%\Microsoft\Teams\previous e la cartella stage viene rinominata in "Current". Gli errori di questo passaggio vengono registrati in SquirrelTemp. log.

Se SquirrelTemp. log o logs. txt non contengono informazioni sufficienti per determinare la causa sottostante e occorrono ulteriori informazioni per risolvere il problema, vedere [raccogliere e analizzare i registri delle applicazioni e di sistema](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Raccogliere e analizzare i registri delle applicazioni e di sistema

Questa sezione descrive come raccogliere e analizzare i registri delle applicazioni e di sistema per ottenere informazioni più complete per risolvere il problema. Potrai usare gli strumenti di Sysinternals per completare questi passaggi. Per altre informazioni, vedere [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).

### <a name="collect-logs"></a>Raccolta di registri

1. Scaricare gli [strumenti di Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Estrarre il file zip nella cartella% TEMP% nell'unità locale.
3. Aprire un prompt dei comandi con privilegi elevati e quindi eseguire le operazioni seguenti:

    1. Eseguire la procedura seguente per passare alla cartella TEMP:

        ```
        cd /d %TEMP%
        ```
    2. Copiare i registri di configurazione e applicazione. Tieni presente che, a seconda del punto di errore, alcuni di questi registri potrebbero non essere presenti.

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Eseguire la procedura seguente per acquisire i quadratini aperti.

        ```
        handle > handles.txt
        ```

    4. Eseguire la procedura seguente per acquisire le dll aperte.

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. Eseguire le operazioni seguenti per acquisire i driver in esecuzione.

        ```
        driverquery /v > driverquery.txt
        ```

    6. Eseguire le operazioni seguenti per acquisire gli elenchi di controllo di accesso (ACL) della cartella teams.

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analizza log (per utenti avanzati)

Un aggiornamento non riuscito può causare un comportamento imprevedibile dell'app. Ad esempio, gli utenti potrebbero non essere in grado di uscire da teams, avere una versione non aggiornata di teams o non possono avviare teams. Se si verifica un problema durante un aggiornamento, la prima posizione in cui cercare la causa è SquirrelTemp. log. Ecco i diversi tipi di errori di aggiornamento, elencati tra i più comuni ai meno comuni, e come analizzarli e risolverli in modo anomalo usando i log.

#### <a name="unable-to-exit-teams"></a>Non è possibile uscire da teams

Poiché teams determina che deve essere aggiornato a una versione più recente, Scarica e mette in scena la nuova app e quindi attende che venga avviata l'occasione per il riavvio del computer alla successiva inattività. Un problema comune durante questo processo è quando un altro processo o un driver del file System blocca il processo teams. exe, che impedisce l'uscita di teams. exe. Di conseguenza, l'app teams non può essere sostituita dall'app appena scaricata e messa in scena.

Suggerimenti per la risoluzione dei problemi:

- Per confermare il problema che si sta verificando, chiudere Teams (fare clic con il pulsante destro del mouse su teams sulla barra delle applicazioni e quindi scegliere **Esci**). Aprire quindi Task Manager in Windows per verificare se un'istanza di teams è ancora in corso.  
- Se non ci si trova nel computer in cui si verifica questo problema, esaminare il SquirrelTemp. log raccolto dal computer in cui si verifica questo problema e cercare un "programma: non è possibile terminare il processo nella voce del log".
- Per determinare cosa impedisce l'uscita di teams. exe, vedere i registri dll. txt e Handles. txt. Questi spiegano i processi che hanno impedito l'uscita dei team.
- Un altro colpevole che può impedire l'uscita dei team è il driver del filtro del file System in modalità kernel. USA lo strumento SysInternals, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), per raccogliere il dump del processo in modalità kernel eseguendo ```procdump -mk <pid>```, dove <pid> si trova l'ID processo ottenuto da Gestione attività. È anche possibile esaminare il file di log di driverquery. txt per visualizzare i driver di filtro attivi che potrebbero interferire con i team.
- Per eseguire il ripristino da questo stato, riavviare il computer.

#### <a name="file-permissions"></a>Autorizzazioni file

Teams crea una serie di sottocartelle e file nel profilo dell'utente durante il processo di installazione e aggiornamento. Poiché l'app e l'Updater vengono eseguiti come utenti non elevati, le autorizzazioni di lettura e scrittura devono essere concesse per le cartelle seguenti:

|Cartella  |Usato da  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Installer Teams (ad esempio Teams_Windows_x64. exe) durante la fase di installazione        |
|%LocalAppData%\Microsoft\Teams  | Updater di Teams (Update. exe) per estrarre e organizzare il pacchetto dell'app durante il processo di aggiornamento        |
|%AppData%\Microsoft\Teams   |  App Teams (teams. exe) per salvare le impostazioni, gli Stati delle app e il pacchetto di aggiornamento (pre-organizzato) Scaricato       |

Se a teams viene negato l'accesso perché non può scrivere in un file, un'altra applicazione software potrebbe interferire o una voce del descrittore di sicurezza potrebbe limitare l'accesso in scrittura a una cartella.

Suggerimenti per la risoluzione dei problemi:

- Cercare l'evidenza "accesso negato" in SquirrelTemp. log o logs. txt. Selezionare questi file per verificare se è stato tentato di scrivere in un file non riuscito.
- Aprire icacls. txt e cercare l'effettiva voce di controllo di accesso (ACE) che blocca le operazioni di scrittura da un utente che non è un amministratore. In genere, si tratta di una delle voci dell'elenco DACL. Per altre informazioni, vedi la [documentazione di icacls](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>File danneggiato

In alcuni casi, il software di crittografia può modificare i file nella cartella%LocalAppData%\Microsoft\Teams, che può impedire l'avvio di teams. Questo problema può verificarsi in qualsiasi momento, anche quando l'app non viene aggiornata. Purtroppo, quando un file è danneggiato, l'unico modo per recuperarlo da questo stato consiste nel disinstallare e reinstallare Team.

> [!NOTE]
> Se non si riesce a determinare la causa sottostante del problema utilizzando uno di questi passaggi, è consigliabile provare una sessione di [monitoraggio processo](https://docs.microsoft.com/sysinternals/downloads/procmon) . Process Monitor è uno strumento di Sysinternals che registra l'accesso al registro di sistema e al file System.

## <a name="related-topics"></a>Argomenti correlati

- [Ottenere client per Teams](get-clients.md)
- [Aggiornamenti del client di Teams](teams-client-update.md)