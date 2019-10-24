---
title: Installare Microsoft teams con MSI tramite SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Gli amministratori possono usare il team MSI per distribuire in blocco Microsoft teams per selezionare utenti o computer.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37573372"
---
<a name="install-microsoft-teams-using-msi"></a>Installare Microsoft teams con MSI
=================================

> [!Tip]
> Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la distribuzione e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)

Per usare System Center Configuration Manager o criteri di gruppo o qualsiasi meccanismo di distribuzione di terze parti per una distribuzione ampia, Microsoft ha fornito file MSI (sia [32 bit](https://aka.ms/teams32bitmsi) che [64 bit](https://aka.ms/teams64bitmsi)) che gli amministratori possono usare per la distribuzione in blocco dei team da selezionare utenti o computer. Gli amministratori possono usare questi file per distribuire in remoto i team in modo che gli utenti non debbano scaricare manualmente l'app teams. Una volta distribuiti, i team verranno avviati automaticamente per tutti gli utenti che accedono a tale computer. Puoi disabilitare l'avvio automatico dopo l'installazione dell'app. [Vedere di seguito](#disable-auto-launch-for-the-msi-installer).) Ti consigliamo di distribuire il pacchetto nel computer, in modo che tutti i nuovi utenti della macchina beneficeranno anche di questa distribuzione. 

I team possono anche essere inclusi in una distribuzione di Office 365 ProPlus. Per altre informazioni, vedere [distribuire Microsoft teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).
 
> [!Note] 
> Per altre informazioni su SCCM, vedere [Introduzione a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedura di distribuzione (scelta consigliata)
1. Recuperare il pacchetto più recente.
2. Usare i valori predefiniti prepopolati da MSI.
3. Eseguire la distribuzione in computer quando possibile.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funzionamento del pacchetto MSI di Microsoft Teams

### <a name="pc-installation"></a>Installazione del PC

> [!Note] 
> Per informazioni su come distribuire Team in un ambiente Virtual DesktopInfrastructure (VDI), vedere [installazione VDI](#vdi-installation) .

Il programma di installazione di teams MSI verrà collocato nei file di programmazione. Ogni volta che un utente accede a un nuovo profilo utente di Windows, verrà avviato il programma di installazione e verrà installata una copia dell'app teams nella cartella AppData dell'utente. Se un utente ha già installato l'app teams nella cartella AppData, il programma di installazione MSI ignorerà il processo per l'utente.

Non usare il file MSI per distribuire gli aggiornamenti, perché il client verrà aggiornato automaticamente quando viene rilevata una nuova versione disponibile nel servizio. Per ridistribuire il programma di installazione più recente, usare il processo di ridistribuzione di MSI descritto di seguito.Se si distribuisce una versione precedente del pacchetto MSI, il client verrà aggiornato automaticamente, ad eccezione degli ambienti VDI, quando possibile per l'utente. Se viene distribuita una versione molto vecchia, il file MSI attiverà un aggiornamento dell'app prima che l'utente possa usare teams. 

> [!Important] 
> Non è consigliabile modificare le posizioni di installazione predefinite, perché questo potrebbe interrompere il flusso di aggiornamento. Una versione troppo vecchia impedirà alla fine di impedire agli utenti di accedere al servizio. 

#### <a name="target-computer-requirements"></a>Requisiti del computer di destinazione

- .NET Framework 4,5 o versione successiva
- Windows 7 o versioni successive
- 3 GB di spazio su disco per ogni profilo utente (scelta consigliata)

### <a name="vdi-installation"></a>Installazione VDI

Ecco il processo per distribuire l'app desktop teams. Per informazioni complete, vedere [team per l'infrastruttura desktop virtualizzata](teams-for-vdi.md).

1. Scaricare il pacchetto MSI teams usando uno dei collegamenti seguenti, a seconda dell'ambiente. È consigliabile usare la versione a 64 bit per una VM VDI con un sistema operativo a 64 bit.

    - [versione a 32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versione a 64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Eseguire il comando seguente per installare il file MSI nella VM VDI o per completare l'aggiornamento.

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Questo consente di installare i team nei file di programma. A questo punto, la configurazione dell'immagine dorata è completa.

    La prossima sessione di accesso interattivo avvia team e richiede le credenziali. Tieni presente che non è possibile disabilitare l'avvio automatico dei team durante l'installazione di teams in VDI tramite la proprietà ALLUSER.

3. Eseguire il comando seguente per disinstallare il file MSI dalla VM VDI o prepararsi per l'aggiornamento.

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    In questo articolo vengono disinstallati team da file di programma.

## <a name="clean-up-and-redeployment-procedure"></a>Procedura per la pulizia e la ridistribuzione

Se un utente disinstalla teams dal proprio profilo utente, il programma di installazione MSI rileva che l'utente ha disinstallato l'app teams e non ha più installato Team per il profilo utente. Per ridistribuire team per l'utente in un determinato computer in cui è stata disinstallata, eseguire le operazioni seguenti:

1. Disinstallare l'app teams installata per ogni profilo utente. 
2. Dopo la disinstallazione, eliminare la directory in modo ricorsivo in%localappdata%\Microsoft\Teams\.
3. Ridistribuire il pacchetto MSI in quel particolare computer.

> [!TIP] 
> È possibile usare lo script di [pulizia della distribuzione di Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) per completare i passaggi 1 e 2 tramite SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Disabilitare l'avvio automatico per il programma di installazione MSI

Il comportamento predefinito di MSI consiste nell'installare il client teams non appena un utente accede e quindi avvia automaticamente teams. È possibile modificare questo comportamento con i parametri seguenti:

- Quando un utente accede a Windows, i team verranno installati con MSI
- Tuttavia, il client teams non si avvia finché l'utente non ha avviato manualmente i team
- Viene aggiunto un collegamento per avviare teams sul desktop dell'utente
- Una volta avviati manualmente, i team verranno avviati automaticamente ogni volta che l'utente accede

Per la versione a 32 bit
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Per la versione a 64 bit
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Se si esegue manualmente il file MSI, assicurarsi di eseguirlo con autorizzazioni elevate. Anche se viene eseguito come amministratore, senza eseguirlo con autorizzazioni elevate, il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.
