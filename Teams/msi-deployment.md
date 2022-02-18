---
title: Installazione in blocco Teams con Windows installer (MSI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Usare Windows installer (MSI) per distribuire il client Teams a più utenti e computer.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc9e17f958b1770573cf6729ef6aca9b22ffe03d
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893565"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Installazione in blocco Teams con Windows installer (MSI)

> [!Tip]
> Guardare la sessione seguente per informazioni sui vantaggi offerti dal client desktop per Windows e su come pianificare ed eseguire la sua distribuzione: [Client desktop di Teams per Windows](https://aka.ms/teams-clients).

Microsoft fornisce file MSI a 32 bit, a 64 bit e ARM64 che è possibile usare per distribuire in blocco Microsoft Teams per selezionare utenti e computer. I file MSI possono essere usati con [Microsoft Endpoint Configuration Manager](/configmgr/core/understand/introduction)[, Criteri](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) di gruppo o software di distribuzione di terze parti, per distribuire Teams all'organizzazione. Le distribuzioni in blocco sono utili perché gli utenti non devono scaricare e installare manualmente Teams client. Al contrario, Teams verrà distribuito nei computer e quindi verrà avviato automaticamente la prima volta che gli utenti a un computer a cui si accede.

È consigliabile distribuire il pacchetto nei computer invece che in un utente specifico. Con la destinazione dei computer, tutti i nuovi utenti di tali computer potranno trarre vantaggio da questa distribuzione.

>[!NOTE]
> Teams può anche essere distribuito all'organizzazione come parte di Microsoft 365 Apps for enterprise. Per altre informazioni, vedere [Distribuire Microsoft Teams con Microsoft 365 Apps for enterprise](/deployoffice/teams-install).

## <a name="msi-files"></a>File MSI

La tabella seguente contiene collegamenti a file MSI a 32 bit, a 64 bit e ARM64 per Teams. Scaricare il file MSI da installare nei computer dell'organizzazione. L'architettura x86 (a 32 bit o a 64 bit) Teams è indipendente dalle altre app Office installate in un computer.

Se si hanno computer a 64 bit, è consigliabile installare il file MSI di Teams a 64 bit anche se il computer esegue una versione a 32 bit di Office. Arm64 MSI può essere installato solo nei computer che usano l'architettura ARM, ad esempio Surface Pro X.

> [!IMPORTANT]
> Installare la versione a 64 bit di Teams solo nei sistemi operativi a 64 bit. Se si prova a installare la versione a 64 bit di Teams in un sistema operativo a 32 bit, l'installazione non riesce e non viene visualizzato un messaggio di errore.

|Entità  |32 bit      |64 bit      | ARM64 |
|---------|---------|---------|-----------|
|Commerciale     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Governo degli Stati Uniti - GCC     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|U.S. Government - GCC High    | [32 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo degli Stati Uniti - DoD     | [32 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Funzionamento del Microsoft Teams MSI

### <a name="pc-installation"></a>Installazione su PC

Il Teams MSI inserisce un programma di installazione in `%SystemDrive%\Program Files\Teams Installer` un Windows a 32 bit `%SystemDrive%\Program Files (x86)\Teams Installer` e in un Windows a 64 bit. Ogni volta che un utente accede a un nuovo profilo Windows utente, viene avviato il programma di installazione e viene installata una copia dell'app Teams nella cartella dell'utente`%LocalAppData%\Microsoft\Teams`. Se un utente ha già installato l Teams app `%LocalAppData%\Microsoft\Teams` nella cartella, il programma di installazione MSI ignora il processo per tale utente.

I file MSI non possono essere usati per distribuire gli aggiornamenti. Il Teams client verrà aggiornato automaticamente quando rileva che una nuova versione è disponibile dal servizio. Per ridistribuire il programma di installazione più recente, usare il processo di ridistribuzione di MSI descritto di seguito. Se si distribuisce una versione precedente del file MSI, il client si aggiornerà automaticamente (ad eccezione degli ambienti VDI) quando possibile per l'utente. Se viene distribuita una versione precedente obsoleta, MSI provvederà all'aggiornamento dell'app prima che l'utente possa far uso di Teams.

> [!IMPORTANT]
> Non è consigliabile modificare i percorsi di installazione predefiniti in quanto ciò potrebbe interrompere il flusso di aggiornamento. Una versione troppo obsoleta potrebbe impedire agli utenti l'accesso al servizio.

#### <a name="target-computer-requirements"></a>Requisiti del computer di destinazione

Assicurarsi che i computer installati Teams i requisiti elencati in [Requisiti hardware per](hardware-requirements-for-the-teams-app.md) Microsoft Teams.

### <a name="vdi-installation"></a>Installazione su VDI

Per una guida completa su come distribuire l'app desktop di Teams su VDI, vedere [Teams per Virtualized Desktop Infrastructure (VDI)](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedura di pulizia e redistribuzione

Se un utente disinstalla Teams dal proprio profilo utente, il programma di installazione di MSI rileverà che l'utente ha disinstallato Teams per quel profilo utente, senza reinstallarlo. Per redistribuire Teams per tale utente su un determinato computer da cui è stato disinstallato, eseguire le operazioni seguenti:

> [!IMPORTANT]
> Nei seguenti passaggi sono riportate informazioni su come modificare il Registro di sistema. Assicurarsi di eseguire il backup del Registro di sistema prima di modificarlo e di sapere come ripristinarlo in caso di problemi. Per ulteriori informazioni su come eseguire il backup, ripristinare e modificare il Registro di sistema, vedere [Informazioni sul Registro di sistema di Windows per utenti esperti](https://support.microsoft.com/help/256986).

1. Disinstallare l'app di Teams installata per ciascun profilo utente. Per altre informazioni, vedere [Disinstallare Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Eliminare la directory in modo ricorsivo in `%LocalAppData%\Microsoft\Teams\` per ogni profilo utente.
3. Eliminare il valore `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` del Registro di sistema per ogni profilo utente.
4. Ridistribuire il file MSI in quel particolare computer.

> [!TIP]
> È anche possibile usare lo [script di pulizia della distribuzione di Teams](scripts/powershell-script-deployment-cleanup.md) per completare i passaggi 1 e 2.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impedire l'avvio automatico di Teams dopo l'installazione

Per impostazione predefinita, MSI installa l'app di Teams non appena un utente vi effettua l'accesso, avviando poi Teams automaticamente. Se non si desidera che Teams si avvii automaticamente per gli utenti dopo l'installazione, è possibile usare i Criteri di gruppo per definire un'impostazione dei criteri oppure disabilitare l'avvio automatico dal programma di installazione di MSI.

### <a name="use-group-policy-recommended"></a>Utilizzo dei Criteri di gruppo (consigliato)

Abilitare **l'impostazione Impedisci Microsoft Teams l'avvio automatico dopo l'installazione di** [Criteri di](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) gruppo. Questa impostazione dei criteri è presente in **Modelli**\\ amministrativi di Configurazione **utente**\\\\ Microsoft Teams **.** Si tratta del metodo consigliato perché è possibile disattivare o attivare l'impostazione dei criteri in base alle esigenze dell'organizzazione.

Se si abilita questa impostazione di criteri prima dell'installazione di Teams, si impedisce l'avvio automatico di Teams quando gli utenti eseguono l'accesso a Windows. Dopo il primo accesso, Teams viene configurato per avviarsi automaticamente al seguente accesso di tale utente al dispositivo.

Per saperne di più, vedere [Uso dei Criteri di gruppo per impedire l'avvio automatico di Teams dopo l'installazione](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se Teams è già stato distribuito e si vuole impostare questo criterio per disabilitarne l'avvio automatico, prima di tutto regolare l'impostazione dei Criteri di gruppo sul valore desiderato, quindi eseguire lo [script per il reset dell'avvio automatico di Teams](scripts/powershell-script-teams-reset-autostart.md) per ogni singolo utente.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Disabilitare l'avvio automatico per il programma di installazione di MSI

È possibile disabilitare l'avvio automatico per il programma di installazione MSI usando il parametro `OPTIONS="noAutoStart=true"` come indicato di seguito.  

Per la versione a 32 bit:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Per la versione a 64 bit:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Quando un utente effettua l'accesso a Windows, Teams viene installato tramite MSI e sul desktop dell'utente viene aggiunto un collegamento per l'avvio di Teams. Teams non si avvierà finché l'utente non lo lancerà manualmente. Dopo l'avvio manuale, Teams si lancerà automaticamente ogni volta che l'utente effettua l'accesso.

Si noti che questi esempi usano anche il parametro **ALLUSERS=1**. Quando si imposta questo parametro, il programma di installazione di Teams per tutte le macchine viene visualizzato in Programmi e funzionalità nel Pannello di controllo e in App e funzionalità nelle Impostazioni di Windows per tutti gli utenti del computer. Pertanto, tutti gli utenti possono quindi disinstallare Teams se hanno credenziali di amministratore sul computer.

> [!Note]
> Se si esegue MSI manualmente, assicurarsi di farlo con autorizzazioni elevate. Anche se eseguito come amministratore, senza un'esecuzione con autorizzazioni elevate il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.
