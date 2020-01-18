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
ms.openlocfilehash: dd934c601b45258dd7a2e2c15ef49f19ffee9201
ms.sourcegitcommit: 416a2d404a2ea15b484cd7579035e7f2282ac2cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233275"
---
# <a name="install-microsoft-teams-using-msi"></a>Installare Microsoft teams con MSI

> [!Tip]
> Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la distribuzione e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)

Per usare System Center Configuration Manager o criteri di gruppo o qualsiasi meccanismo di distribuzione di terze parti per una distribuzione ampia, Microsoft ha fornito file MSI (sia 32 bit che 64 bit) che gli amministratori possono usare per la distribuzione in blocco dei team per selezionare utenti o computer. Gli amministratori possono usare questi file per distribuire in remoto i team in modo che gli utenti non debbano scaricare manualmente l'app teams. Una volta distribuiti, i team verranno avviati automaticamente per tutti gli utenti che accedono a tale computer. Puoi disabilitare l'avvio automatico dopo l'installazione dell'app. [Vedere di seguito](#disable-auto-launch-for-the-msi-installer).) Ti consigliamo di distribuire il pacchetto nel computer, in modo che tutti i nuovi utenti della macchina beneficeranno anche di questa distribuzione.

Questi sono i collegamenti ai file MSI:


|Entità  |32 bit      |64 bit      |
|---------|---------|---------|
|Commerciale     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Governo federale-GCC     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Governo federale-GCC High    | [32 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Governo federale-DoD     | [32 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

I team possono anche essere inclusi in una distribuzione di Office 365 ProPlus. Per altre informazioni, vedere [distribuire Microsoft teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Per altre informazioni su SCCM, vedere [Introduzione a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedura di distribuzione (scelta consigliata)

1. Recuperare il pacchetto più recente.
2. Usare i valori predefiniti prepopolati da MSI.
3. Eseguire la distribuzione in computer quando possibile.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funzionamento del pacchetto MSI di Microsoft Teams

### <a name="pc-installation"></a>Installazione del PC

Il programma di installazione di teams MSI verrà collocato nei file di programmazione. Ogni volta che un utente accede a un nuovo profilo utente di Windows, verrà avviato il programma di installazione e verrà installata una copia dell'app teams nella cartella AppData dell'utente. Se un utente ha già installato l'app teams nella cartella AppData, il programma di installazione MSI ignorerà il processo per l'utente.

Non usare il file MSI per distribuire gli aggiornamenti, perché il client verrà aggiornato automaticamente quando viene rilevata una nuova versione disponibile nel servizio. Per ridistribuire il programma di installazione più recente, usare il processo di ridistribuzione di MSI descritto di seguito.Se si distribuisce una versione precedente del pacchetto MSI, il client verrà aggiornato automaticamente, ad eccezione degli ambienti VDI, quando possibile per l'utente. Se viene distribuita una versione molto vecchia, il file MSI attiverà un aggiornamento dell'app prima che l'utente possa usare teams.

> [!Important]
> Non è consigliabile modificare le posizioni di installazione predefinite, perché questo potrebbe interrompere il flusso di aggiornamento. Una versione troppo vecchia impedirà alla fine di impedire agli utenti di accedere al servizio.

#### <a name="target-computer-requirements"></a>Requisiti del computer di destinazione

- .NET Framework 4,5 o versione successiva
- Windows 7 o versioni successive
- Windows Server 2012 R2 o versioni successive
- 3 GB di spazio su disco per ogni profilo utente (scelta consigliata)

### <a name="vdi-installation"></a>Installazione VDI

Per istruzioni complete su come distribuire l'app desktop teams su VDI, vedere [team per l'infrastruttura desktop virtualizzata](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedura per la pulizia e la ridistribuzione

Se un utente disinstalla teams dal proprio profilo utente, il programma di installazione MSI rileva che l'utente ha disinstallato l'app teams e non ha più installato Team per il profilo utente. Per ridistribuire team per l'utente in un determinato computer in cui è stata disinstallata, eseguire le operazioni seguenti:

1. Disinstallare l'app teams installata per ogni profilo utente.
2. Dopo la disinstallazione, eliminare la directory in modo ricorsivo in%localappdata%\Microsoft\Teams\.
3. Ridistribuire il pacchetto MSI in quel particolare computer.

> [!TIP]
> È possibile usare lo script di [pulizia della distribuzione di Microsoft teams](scripts/powershell-script-teams-deployment-clean-up.md) per completare i passaggi 1 e 2 tramite SCCM.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impedire l'avvio automatico dei team dopo l'installazione

Il comportamento predefinito di MSI consiste nell'installare l'app teams non appena un utente accede e quindi avvia automaticamente teams. Se non si vuole che i team vengano avviati automaticamente per gli utenti dopo l'installazione, è possibile usare criteri di gruppo per impostare un'impostazione di criteri o disabilitare l'avvio automatico per il programma di installazione MSI.

#### <a name="use-group-policy-recommended"></a>Usare criteri di gruppo (scelta consigliata)

Consentire l' **avvio automatico di Microsoft teams dopo** l'impostazione di criteri di gruppo installazione. Questa impostazione dei criteri può essere trovata in team Configurazione utente\Modelli Amministrativi\microsoft. Questo è il metodo consigliato perché puoi disattivare o attivare l'impostazione dei criteri in base alle esigenze dell'organizzazione.

Quando si abilita questa impostazione per i criteri prima dell'installazione di teams, teams non si avvia automaticamente quando gli utenti accedono a Windows. Dopo che un utente ha eseguito l'accesso a teams per la prima volta, teams avvia automaticamente la volta successiva che l'utente accede.

Per altre informazioni, vedere [usare criteri di gruppo per evitare che i team vengano avviati automaticamente dopo l'installazione](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se i team sono già stati distribuiti e si vuole impostare questo criterio per disabilitare l'autostart di teams, impostare prima di tutto l'impostazione di criteri di gruppo sul valore desiderato e quindi eseguire lo [script di reset autostart di teams](scripts/powershell-script-teams-reset-autostart.md) per ogni singolo utente.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Disabilitare l'avvio automatico per il programma di installazione MSI

È possibile disabilitare l'avvio automatico per il programma di installazione MSI usando il parametro **Options = "noAutoStart = true"** come indicato di seguito.  

Per la versione a 32 bit
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Per la versione a 64 bit
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Quando un utente accede a Windows, teams viene installato con MSI e viene aggiunto un collegamento per avviare teams al desktop dell'utente. I team non si avviano finché l'utente non avvia manualmente teams. Dopo che l'utente ha avviato manualmente teams, teams avvia automaticamente ogni volta che l'utente effettua l'accesso.

> [!Note]
> Se si esegue manualmente il file MSI, assicurarsi di eseguirlo con autorizzazioni elevate. Anche se viene eseguito come amministratore, senza eseguirlo con autorizzazioni elevate, il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.
