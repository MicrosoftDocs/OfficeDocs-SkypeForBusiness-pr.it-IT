---
title: Installare Microsoft Teams usando MSI tramite Microsoft Endpoint Configuration Manager
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Gli amministratori possono utilizzare MSI di Teams per distribuire in blocco Microsoft Teams a utenti o computer selezionati.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327828"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager

> [!Tip]
> Guardare la sessione seguente per informazioni sui vantaggi offerti dal client desktop per Windows e su come pianificare ed eseguire la distribuzione: [Teams Windows Desktop Client](https://aka.ms/teams-clients) (client desktop di Teams per Windows).

Per usare Microsoft Endpoint Configuration Manager o Criteri di gruppo o qualsiasi meccanismo di terze parti per la distribuzione estesa, Microsoft ha fornito dei file MSI (sia a 32 bit che a 64 bit) utilizzabili dagli amministratori per distribuire in blocco Teams a utenti o computer selezionati. Gli amministratori possono usare questi file per la distribuzione di Teams da remoto, in modo che gli utenti non debbano scaricare manualmente l'app di Teams. A distribuzione avvenuta, Teams si avvierà automaticamente per tutti gli utenti che effettuano l'accesso su tale computer (è possibile disabilitare l'avvio automatico dopo l'installazione dell'app. [Vedere sotto](#disable-auto-launch-for-the-msi-installer)). Si consiglia di distribuire il pacchetto sul computer, in modo che tutti i nuovi utenti di tale computer trarranno vantaggio da questa distribuzione.

Ecco i collegamenti ai file MSI:


|Entità  |32 bit      |64 bit      |
|---------|---------|---------|
|Commerciale:     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Governo federale - GCC     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Governo federale - GCC High    | [32 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Governo federale - DoD     | [32 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Teams può anche essere incluso in una distribuzione di Office 365 ProPlus. Per altre informazioni, vedere [Distribuire Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Per scoprire di più su Microsoft Endpoint Configuration Manager, vedere [Che cos'è Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>Procedura di distribuzione (consigliata)

1. Recuperare il pacchetto più recente.
2. Usare le impostazioni predefinite prepopolate da MSI.
3. Distribuire ai computer, se possibile.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Come funziona il pacchetto MSI di Microsoft Teams

### <a name="pc-installation"></a>Installazione su PC

MSI di Teams inserirà un programma di installazione nella cartella Programmi. Ogni volta che un utente accede con un nuovo profilo utente di Windows, questo programma di installazione verrà avviato e installerà una copia dell'app di Teams nella cartella `AppData` di quell'utente. Se un utente ha già installato l'app di Teams nella cartella `AppData`, il programma di installazione di MSI salterà il processo per tale utente.

Non utilizzare il pacchetto MSI per distribuire gli aggiornamenti, poiché il client si aggiorna automaticamente se rileva che è disponibile una nuova versione del servizio. Per distribuire nuovamente il programma di installazione più recente, usare il processo di redistribuzione di MSI descritto di seguito. Se si distribuisce una versione meno recente del pacchetto MSI, il client verrà aggiornato automaticamente (ad eccezione degli ambienti VDI) quando è possibile per l'utente. Se viene distribuita una versione precedente obsoleta, MSI provvederà all'aggiornamento dell'app prima che l'utente possa far uso di Teams.

> [!Important]
> Non è consigliabile modificare i percorsi di installazione predefiniti, poiché potrebbe interrompersi il flusso degli aggiornamenti. Una versione troppo obsoleta potrebbe impedire agli utenti l'accesso al servizio.

#### <a name="target-computer-requirements"></a>Requisiti del computer di destinazione

- .NET Framework 4.5 o versioni successive
- Windows 8.1 o versioni successive
- Windows Server 2012 R2 o versioni successive
- 3 GB di spazio su disco per ogni profilo utente (consigliato)

### <a name="vdi-installation"></a>Installazione su VDI

Per una guida completa su come distribuire l'app desktop di Teams su VDI, vedere [Teams per Virtualized Desktop Infrastructure (VDI)](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedura di pulizia e redistribuzione

Se un utente disinstalla Teams dal proprio profilo utente, il programma di installazione di MSI rileverà che l'utente ha disinstallato Teams per quel profilo utente, senza reinstallarlo. Per redistribuire Teams per tale utente su un determinato computer da cui era stato disinstallato, eseguire le operazioni seguenti:

1. Disinstallare l'app di Teams installata per ciascun profilo utente.
2. Dopo la disinstallazione, eliminare in modo ricorsivo la directory in `%localappdata%\Microsoft\Teams\`.
3. Redistribuire il pacchetto MSI su quel particolare computer.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impedire l'avvio automatico di Teams dopo l'installazione

Per impostazione predefinita, MSI installa l'app di Teams non appena un utente vi effettua l'accesso, avviando poi Teams automaticamente. Se non si desidera che Teams si avvii automaticamente per gli utenti dopo l'installazione, è possibile usare i Criteri di gruppo per definire un'impostazione dei criteri oppure disabilitare l'avvio automatico dal programma di installazione di MSI.

#### <a name="use-group-policy-recommended"></a>Utilizzo dei Criteri di gruppo (consigliato)

Abilitare l'impostazione dei Criteri di gruppo **Impedire l'avvio automatico di Microsoft Teams dopo l'installazione**. Questa impostazione di criteri è disponibile in Configurazione utente\Criteri\Modelli amministrativi\Microsoft Teams. Si tratta del metodo consigliato perché è possibile disattivare o attivare l'impostazione dei criteri in base alle esigenze dell'organizzazione.

Se si abilita questa impostazione di criteri prima dell'installazione di Teams, si impedisce l'avvio automatico di Teams quando gli utenti eseguono l'accesso a Windows. Dopo il primo accesso, Teams viene configurato per avviarsi automaticamente al seguente accesso di tale utente al dispositivo.

Per saperne di più, vedere [Uso dei Criteri di gruppo per impedire l'avvio automatico di Teams dopo l'installazione](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se Teams è già stato distribuito e si vuole impostare questo criterio per disabilitarne l'avvio automatico, prima di tutto regolare l'impostazione dei Criteri di gruppo sul valore desiderato, quindi eseguire lo [script per il reset dell'avvio automatico di Teams](scripts/powershell-script-teams-reset-autostart.md) per ogni singolo utente.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Disabilitare l'avvio automatico per il programma di installazione di MSI

È possibile disabilitare l'avvio automatico per il programma di installazione di MSI usando il parametro **OPTIONS="noAutoStart=true"** come indicato di seguito.  

Per la versione a 32 bit

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

Per la versione a 64 bit

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Quando un utente effettua l'accesso a Windows, Teams viene installato tramite MSI e sul desktop dell'utente viene aggiunto un collegamento per l'avvio di Teams. Teams non si avvierà finché l'utente non lo lancerà manualmente. Dopo l'avvio manuale, Teams si lancerà automaticamente ogni volta che l'utente effettua l'accesso.

> [!Note]
> Se si esegue MSI manualmente, assicurarsi di farlo con autorizzazioni elevate. Anche se eseguito come amministratore, senza un'esecuzione con autorizzazioni elevate il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.
