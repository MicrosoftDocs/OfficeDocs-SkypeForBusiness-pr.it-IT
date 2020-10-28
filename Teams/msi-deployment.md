---
title: Installare teams con Microsoft endpoint Configuration Manager
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: Usare Microsoft endpoint Configuration Manager per distribuire in blocco Microsoft teams per selezionare utenti o computer.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3eb845321a13e7701f7a8d49b975fe077fa2e14
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778789"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager

> [!Tip]
> Guarda la sessione seguente per conoscere i vantaggi del client desktop di Windows, come pianificare e come distribuirlo: [Team client desktop di Windows](https://aka.ms/teams-clients).

Per usare Microsoft Endpoint Configuration Manager o Criteri di gruppo o qualsiasi meccanismo di terze parti per la distribuzione estesa, Microsoft ha fornito dei file MSI (sia a 32 bit che a 64 bit) utilizzabili dagli amministratori per distribuire in blocco Teams a utenti o computer selezionati. Gli amministratori possono usare questi file per la distribuzione di Teams da remoto, in modo che gli utenti non debbano scaricare manualmente l'app di Teams. A distribuzione avvenuta, Teams si avvierà automaticamente per tutti gli utenti che effettuano l'accesso su tale computer (è possibile disabilitare l'avvio automatico dopo l'installazione dell'app. [Vedere sotto](#disable-auto-launch-for-the-msi-installer)). Si consiglia di distribuire il pacchetto sul computer, in modo che tutti i nuovi utenti di tale computer trarranno vantaggio da questa distribuzione.

Ecco i collegamenti ai file MSI:

|Entità  |32 bit      |64 bit      | ARM64 |
|---------|---------|---------|-----------|
|Commerciale:     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Governo federale - GCC     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo federale - GCC High    | [32 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo federale - DoD     | [32 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**Per garantire una distribuzione corretta, tenere presente quanto segue:**

- Installare la versione a 64 bit di Teams nei sistemi operativi a 64 bit. Se si prova a installare la versione a 64 bit di teams in un sistema operativo a 32 bit, l'installazione non avrà esito positivo e attualmente non verrà visualizzato un messaggio di errore.

- Se il tenant del cliente si trova sulle nubi di GCCH o DoD, il cliente deve impostare l'endpoint iniziale nel registro di sistema aggiungendo il valore **CloudType** alla chiave **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** nel registro di sistema. Il tipo per **CloudType** è **DWORD** e i valori sono (0 = non impostato, 1 = commerciale, 2 = GCC, 3 = GCCH, 4 = DOD). L'impostazione dell'endpoint con la chiave del registro di sistema limita i team alla connessione all'endpoint cloud corretto per la connettività di pre-accesso con teams.

- I team possono anche essere inclusi in una distribuzione delle app Microsoft 365 per le aziende. Per altre informazioni, vedere [distribuire Microsoft teams con le app microsoft 365 per le aziende](https://docs.microsoft.com/deployoffice/teams-install).

- Per altre informazioni su Microsoft endpoint Configuration Manager, vedere [che cos'è Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>Procedura di distribuzione (consigliata)

1. Recuperare il pacchetto più recente.
2. Usare le impostazioni predefinite prepopolate da MSI.
3. Distribuire ai computer, se possibile.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Come funziona il pacchetto MSI di Microsoft Teams

### <a name="pc-installation"></a>Installazione su PC

MSI di Teams inserirà un programma di installazione nella cartella Programmi. Ogni volta che un utente accede con un nuovo profilo utente di Windows, questo programma di installazione verrà avviato e installerà una copia dell'app di Teams nella cartella `AppData` di quell'utente. Se un utente ha già installato l'app di Teams nella cartella `AppData`, il programma di installazione di MSI salterà il processo per tale utente.

Non utilizzare il pacchetto MSI per distribuire gli aggiornamenti, poiché il client si aggiorna automaticamente se rileva che è disponibile una nuova versione del servizio. Per distribuire nuovamente il programma di installazione più recente, usare il processo di redistribuzione di MSI descritto di seguito. Se si distribuisce una versione meno recente del pacchetto MSI, il client verrà aggiornato automaticamente (ad eccezione degli ambienti VDI) quando è possibile per l'utente. Se viene distribuita una versione precedente obsoleta, MSI provvederà all'aggiornamento dell'app prima che l'utente possa far uso di Teams.

> [!IMPORTANT]
> Il percorso predefinito è C:\Programmi (x86) \Teams Installer in sistemi operativi a 64 bit e C:\Program Files\Teams Installer nei sistemi operativi a 32 bit.
> Non è consigliabile modificare i percorsi di installazione predefiniti, poiché potrebbe interrompersi il flusso degli aggiornamenti. Una versione troppo obsoleta potrebbe impedire agli utenti l'accesso al servizio.

#### <a name="target-computer-requirements"></a>Requisiti del computer di destinazione

- .NET Framework 4.5 o versioni successive
- Windows 8.1 o versioni successive
- Windows Server 2012 R2 o versioni successive
- 3 GB di spazio su disco per ogni profilo utente (consigliato)

### <a name="vdi-installation"></a>Installazione su VDI

Per una guida completa su come distribuire l'app desktop di Teams su VDI, vedere [Teams per Virtualized Desktop Infrastructure (VDI)](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedura di pulizia e redistribuzione

Se un utente disinstalla teams dal proprio profilo utente, il programma di installazione MSI rileva che l'utente ha disinstallato l'app teams e non ha più installato Team per il profilo utente. Per redistribuire Teams per tale utente su un determinato computer da cui era stato disinstallato, eseguire le operazioni seguenti:

> [!IMPORTANT]
> I passaggi successivi contengono informazioni su come modificare il registro di sistema. Verificare di eseguire il backup del registro di sistema prima di modificarlo e di sapere come ripristinare il registro di sistema, se si verifica un problema. Per altre informazioni su come eseguire il backup, ripristinare e modificare il registro di sistema, vedere [informazioni sul Registro di sistema di Windows per utenti avanzati](https://support.microsoft.com/help/256986).

1. Disinstallare l'app teams installata per ogni profilo utente. Per altre informazioni, vedere [disinstallare Microsoft teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Eliminare la directory in modo ricorsivo in `%localappdata%\Microsoft\Teams\` .
3. Eliminare il `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` valore del registro di sistema.
4. Redistribuire il pacchetto MSI su quel particolare computer.

> [!TIP]
> Per completare i passaggi 1 e 2, è anche possibile usare [lo script di pulizia della distribuzione di teams](scripts/powershell-script-deployment-cleanup.md) .  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impedire l'avvio automatico di Teams dopo l'installazione

Per impostazione predefinita, MSI installa l'app di Teams non appena un utente vi effettua l'accesso, avviando poi Teams automaticamente. Se non si desidera che Teams si avvii automaticamente per gli utenti dopo l'installazione, è possibile usare i Criteri di gruppo per definire un'impostazione dei criteri oppure disabilitare l'avvio automatico dal programma di installazione di MSI.

### <a name="use-group-policy-recommended"></a>Utilizzo dei Criteri di gruppo (consigliato)

Abilitare l'impostazione dei Criteri di gruppo **Impedire l'avvio automatico di Microsoft Teams dopo l'installazione** . Questa impostazione di criteri è disponibile in Configurazione utente\Criteri\Modelli amministrativi\Microsoft Teams. Si tratta del metodo consigliato perché è possibile disattivare o attivare l'impostazione dei criteri in base alle esigenze dell'organizzazione.

Se si abilita questa impostazione di criteri prima dell'installazione di Teams, si impedisce l'avvio automatico di Teams quando gli utenti eseguono l'accesso a Windows. Dopo il primo accesso, Teams viene configurato per avviarsi automaticamente al seguente accesso di tale utente al dispositivo.

Per saperne di più, vedere [Uso dei Criteri di gruppo per impedire l'avvio automatico di Teams dopo l'installazione](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se Teams è già stato distribuito e si vuole impostare questo criterio per disabilitarne l'avvio automatico, prima di tutto regolare l'impostazione dei Criteri di gruppo sul valore desiderato, quindi eseguire lo [script per il reset dell'avvio automatico di Teams](scripts/powershell-script-teams-reset-autostart.md) per ogni singolo utente.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Disabilitare l'avvio automatico per il programma di installazione di MSI

È possibile disabilitare l'avvio automatico per il programma di installazione di MSI usando il parametro **OPTIONS="noAutoStart=true"** come indicato di seguito.  

Per la versione a 32 bit:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Per la versione a 64 bit:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Quando un utente effettua l'accesso a Windows, Teams viene installato tramite MSI e sul desktop dell'utente viene aggiunto un collegamento per l'avvio di Teams. Teams non si avvierà finché l'utente non lo lancerà manualmente. Dopo l'avvio manuale, Teams si lancerà automaticamente ogni volta che l'utente effettua l'accesso.

Tieni presente che questi esempi usano anche il parametro **ALLUSERS = 1** . Quando si imposta questo parametro, teams Machine-Wide Installer viene visualizzato in programmi e funzionalità nel pannello di controllo e nelle app & caratteristiche nelle impostazioni di Windows per tutti gli utenti del computer. Tutti gli utenti possono quindi disinstallare teams se hanno credenziali di amministratore nel computer.

> [!Note]
> Se si esegue MSI manualmente, assicurarsi di farlo con autorizzazioni elevate. Anche se eseguito come amministratore, senza un'esecuzione con autorizzazioni elevate il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.
