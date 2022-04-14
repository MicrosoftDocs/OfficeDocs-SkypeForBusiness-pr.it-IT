---
title: Ottenere i client per Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come installare i vari client disponibili per Microsoft Teams su PC, Mac e dispositivi mobili.
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5b67137aa581aae5a27ccc18935f621f51d5093
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839017"
---
# <a name="get-clients-for-microsoft-teams"></a>Ottenere i client per Microsoft Teams

> [!TIP]
> **Installare Teams nel PC, nel Mac o nel dispositivo mobile?** Vedere [Installare il client di Teams](https://go.microsoft.com/fwlink/?linkid=855754).

Microsoft Teams può essere installato su PC, Mac e dispositivi mobili e può anche essere accessibile tramite un Web browser. La maggior parte degli utenti finali può iniziare a usare Teams [installando il client](https://go.microsoft.com/fwlink/?linkid=855754) stesso. Dopo aver installato il client Teams, è sufficiente accedere con il nome utente e la password.

Se sei un professionista IT Pro e vuoi saperne di più sull'esperienza di installazione di Teams e sui relativi requisiti, seleziona un sistema operativo client in questo articolo per altre informazioni.

Per informazioni dettagliate sulle funzionalità di ogni client su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="desktop-clients"></a>Client desktop

Il client desktop di Teams è disponibile come applicazione autonoma e come parte di [Microsoft 365 Apps for enterprise](/deployoffice/teams-install) per i sistemi operativi seguenti:

- Versioni a 32 bit e a 64 bit di Windows (8.1 o versioni successive, escluso Windows 10 LTSC) 
- ARM64 per Windows 10 in ARM 
- Windows Server (2012 R2 o versione successiva)
- macOS
- Linux (in formati `.deb` e `.rpm`)
- Chrome OS (per altre informazioni, vedere [Come usare Microsoft Office su un Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad))

I client desktop possono essere scaricati e installati dagli utenti finali direttamente da [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754), se dispongono delle autorizzazioni locali appropriate. I diritti di amministratore non sono necessari per installare il client di Teams in PC Windows, ma lo sono per installarlo sui Mac.

Gli amministratori IT Pros possono usare il proprio metodo preferito per distribuire i file di installazione nei computer dell'organizzazione. Alcuni esempi sono Microsoft Endpoint Configuration Manager in Windows o Jamf Pro in macOS. Per altre informazioni sulla distribuzione di Teams, vedere quanto segue.

- **Windows** [installare Teams usando Gestione configurazione endpoint](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> La distribuzione del client tramite questi meccanismi è solo per l'installazione iniziale dei client Teams e non per aggiornamenti futuri. Per informazioni sul processo di aggiornamento di Teams, vedere [Processo di aggiornamento di Teams](teams-client-update.md).

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Guardare la sessione seguente per informazioni sui vantaggi offerti dal client desktop per Windows e su come pianificare ed eseguire la distribuzione: [Teams Windows Desktop Client](https://aka.ms/teams-clients) (client desktop di Teams per Windows).

Teams in Windows offre programmi di installazione MSI scaricabili in architetture a [32-bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true), [64-bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true) e [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true). L'architettura x86 (a 32 bit e a 64 bit) di Teams è agnostica rispetto all'architettura di Windows e Office installata. È consigliabile usare la versione a 64 bit di Teams nei sistemi a 64 bit.

Teams richiede .NET Framework 4.5 o versione successiva. Se .NET Framework o versione successiva non è installato, il programma di installazione di Teams darà la possibilità di installarlo all’utente.

Il client Windows viene distribuito nella cartella AppData, all'interno del profilo dell'utente. La distribuzione nel profilo locale dell'utente consente di installare il client senza bisogno di diritti elevati. Il client Windows utilizza le posizioni seguenti:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Quando gli utenti avviano per la prima volta una chiamata usando il client di Teams, potrebbe comparire un avviso relativo alle impostazioni di Windows Firewall in cui si chiede di consentire la comunicazione. Si potrebbe anche indicare agli utenti di ignorare il messaggio, perché la chiamata funzionerà anche se l'avviso viene ignorato.

![Screenshot di una finestra di dialogo Avviso di sicurezza di Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configurazione di Windows Firewall verrà modificata anche se il messaggio viene ignorato selezionando "Annulla". Verranno create due regole in entrata per teams.exe, con l'azione Consenti per i protocolli TCP e UDP.

Se vuoi evitare che Teams chieda agli utenti di creare regole del firewall quando gli utenti effettuano la prima chiamata da Teams, usa lo script di PowerShell in [script di esempio - Script PowerShell del firewall di Microsoft Teams](client-firewall-script.md).

### <a name="mac"></a>[Mac](#tab/Mac)

Gli utenti Mac possono installare Teams con un file di installazione PKG per i computer che eseguono macOS. Per installare il client Mac è necessario l'accesso amministrativo. Il client macOS viene installato nella cartella /Applicazioni.

1. Nella pagina di download di [Teams](https://teams.microsoft.com/downloads), in **Mac** fare clic su **Scarica**.
2. Fare doppio clic sul file PKG.
3. Seguire la procedura guidata per completare l'installazione.
4. Teams verrà installato nella cartella /Applicazioni. Si tratta di un'installazione a livello di computer.

> [!NOTE]
> Durante l'installazione verranno richieste le credenziali di amministratore. L'utente deve immettere le credenziali di amministratore, indipendentemente dal fatto di esserlo o meno.

Se un utente ha un'installazione DMG di Teams e vuole sostituirla con l'installazione PKG, deve procedere come segue:

1. Uscire dall'app Teams.
2. Disinstallare l'app Teams.
3. Installare il file PKG.

Gli amministratori IT Pros possono usare una soluzione di distribuzione gestita, ad esempio Jamf Pro, per distribuire i file di installazione di Teams a tutti i Mac dell'organizzazione.

### <a name="linux"></a>[Linux](#tab/Linux)

In Linux, i gestori di pacchetti come `apt` e `yum` cercheranno di installare automaticamente tutti i requisiti. Se questo non avviene, prima di installare Team su Linux sarà necessario installare i requisiti segnalati.

Gli utenti potranno installare pacchetti Linux nativi nei formati `.deb` e `.rpm`. Installando il pacchetto DEB o RPM verrà installato automaticamente il repository del pacchetto.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

La chiave di firma per abilitare l'aggiornamento automatico usando il gestore pacchetti del sistema viene installata automaticamente. Tuttavia, è disponibile anche in: <https://packages.microsoft.com/keys/microsoft.asc>. Teams viene aggiornato mensilmente. Se il repository è stato installato correttamente, il gestore pacchetti del sistema dovrebbe gestire l'aggiornamento automatico esattamente come per gli altri pacchetti presenti nel sistema.

#### <a name="install-teams-using-deb-package"></a>Installare Teams usando il pacchetto DEB

1. Scaricare il pacchetto da <https://aka.ms/getteams>.
2. Installare usando uno dei metodi seguenti:
    - Aprire lo strumento di gestione dei pacchetti appropriato e seguire il processo guidato di installazione delle app di Linux.
    - Se si preferisce usare Terminale, digitare: `sudo dpkg -i **teams download file**`

È possibile avviare Teams tramite Attività o tramite Terminale digitando `teams`.

#### <a name="install-teams-using-rpm-package"></a>Installare Team usando il pacchetto RPM

1. Scaricare il pacchetto da <https://aka.ms/getteams>.
2. Installare usando uno dei metodi seguenti:
    - Aprire lo strumento di gestione dei pacchetti appropriato e seguire il processo guidato di installazione delle app di Linux.
    - Se si preferisce usare Terminale, digitare: `sudo yum install **teams download file**`

È possibile avviare Teams tramite Attività o tramite Terminale digitando `teams`.

#### <a name="install-manually-from-the-command-line"></a>Eseguire l'installazione manualmente dalla riga di comando

Installare manualmente nelle distribuzioni Debian e Ubuntu:

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

Installare manualmente nelle distribuzioni basate su RHEL, Fedora e CentOS:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

In alternativa, per usare yum anziché dnf:

```bash
yum check-update
sudo yum install teams
```

Installare manualmente nelle distribuzioni basate su openSUSE:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

---

## <a name="mobile-clients"></a>Client per dispositivi mobili

Le app teams per dispositivi mobili sono disponibili per Android e iOS e sono destinate agli utenti in viaggio che partecipano a conversazioni basate su chat e consentono chiamate audio peer-to-peer. Per le app per dispositivi mobili, visitare Google Play Store e l'App Store di Apple.

Le piattaforme per dispositivi mobili supportate per le app per dispositivi mobili di Teams sono le seguenti:

- **Android**: il supporto è limitato alle ultime quattro versioni principali di Android. Quando viene rilasciata una nuova versione principale di Android, sono ufficialmente supportate la nuova versione e le tre versioni precedenti.

- **iOS**: il supporto è limitato alle ultime due versioni principali di iOS. Quando viene rilasciata una nuova versione principale di iOS, sono ufficialmente supportate la nuova versione e la versione precedente.

> [!NOTE]
> Perché Teams funzioni come previsto, la versione per dispositivi mobili deve essere disponibile al pubblico.

Le app per dispositivi mobili vengono distribuite e aggiornate solo tramite l'app store della piattaforma corrispondente. La distribuzione delle app per dispositivi mobili tramite MDM o sideload non è supportata da Microsoft. Dopo l'installazione in una piattaforma mobile supportata, l'app Teams per dispositivi mobili sarà supportata purché la versione rientri entro tre mesi dalla versione corrente.

Se ti trovi in Cina, è possibile installare Teams dai seguenti app store:

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** Cercare per "Teams" nell’Oppo store
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

## <a name="browser-client"></a>Client del browser

Il client browser ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) è un client completo di tutte le funzionalità che è possibile usare da più browser. Il client browser supporta le chiamate e le riunioni tramite webRTC, quindi non sono necessari plug-in o download per eseguire Teams in un browser. Il browser deve essere configurato in modo da consentire i cookie di terze parti.

[!INCLUDE [browser-support](includes/browser-support.md)]

Il client del browser esegue il rilevamento della versione del browser al momento della connessione a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Se viene rilevata una versione del browser non supportata, l'accesso all'interfaccia browser verrà bloccato e l'utente verrà invitato a scaricare il client desktop o l'app per dispositivi mobili.
