---
title: Ottenere i client per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i vari client disponibili per Microsoft Teams, che includono client Web, desktop (per Windows e Mac) e per dispositivi mobili (Android e iOS).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 928812619ff0f3f5c0194f75bdc93ced2f84c79b
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139129"
---
# <a name="get-clients-for-microsoft-teams"></a>Ottenere i client per Microsoft Teams 


Microsoft Teams dispone di client per PC (Windows, Mac e Linux), Web e dispositivi mobili (Android e iOS). Per questi client è necessaria una connessione Internet attiva e la modalità offline non è supportata.

> [!NOTE]
> Dal 29 novembre 2018 non è più possibile usare l'app Microsoft Teams per Windows 10 S (anteprima) disponibile in Microsoft Store. In alternativa, sui dispositivi che eseguono la modalità S di Windows 10 si può scaricare e installare il client desktop di Teams. Per scaricare il client desktop, passare alla pagina [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). Le build MSI del client desktop di Teams non sono ancora disponibili per i dispositivi che eseguono Windows 10 in modalità S.
>
> Per altre informazioni, vedere [Ti presentiamo Windows 10 in modalità S](https://www.microsoft.com/windows/s-mode). 

## <a name="desktop-client"></a>Client desktop

> [!TIP]
> Guardare la sessione seguente per informazioni sui vantaggi offerti dal client desktop per Windows e su come pianificare ed eseguire la distribuzione: [Teams Windows Desktop Client](https://aka.ms/teams-clients) (client desktop di Teams per Windows).

Il client desktop Microsoft teams è un'applicazione autonoma ed è [disponibile anche nelle app microsoft 365 per le aziende](https://docs.microsoft.com/deployoffice/teams-install). Teams è disponibile per le versioni a 32 bit e 64 bit di Windows (8,1 o versioni successive) e Windows Server (2012 R2 o versioni successive), nonché per macOS e Linux ( `.deb` in `.rpm` e formati). In Windows, Teams richiede .NET Framework 4.5 o versione successiva. Se non è disponibile, il programma di installazione di Teams offrirà la possibilità di installarlo. In Linux, i gestori di pacchetti come `apt` e `yum` cercheranno di installare automaticamente tutti i requisiti. Se questo non avviene, prima di installare Team su Linux sarà necessario installare i requisiti segnalati.

I client desktop supportano le comunicazioni in tempo reale (audio, video e condivisione del contenuto) per riunioni del team, chiamate di gruppo e chiamate private tra due persone.

I client desktop possono essere scaricati e installati direttamente dagli utenti finali dalla pagina [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754), se hanno le autorizzazioni locali appropriate. I diritti di amministratore non sono necessari per installare il client di Teams in un PC, ma lo sono per installarlo in un Mac.

> [!NOTE]
> Per altre informazioni sull'installazione di Team su un Chromebook, vedere [come installare ed eseguire Microsoft Office in un Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).

Gli amministratori IT possono usare il proprio metodo preferito per distribuire i file di installazione nei computer dell'organizzazione. Alcuni esempi sono Microsoft Endpoint Configuration Manager in Windows o Jamf Pro in macOS. Per ottenere il pacchetto MSI per la distribuzione in Windows, vedere [Installare Microsoft Teams con MSI](msi-deployment.md).  

> [!NOTE]
> La distribuzione tramite questi meccanismi è necessaria solo per l'installazione iniziale dei client di Microsoft Teams e non per gli aggiornamenti futuri.

### <a name="windows"></a>Windows

L'installazione di Microsoft Teams per Windows include programmi di installazione scaricabili con architettura a 32 bit e a 64 bit.

> [!NOTE]
> L'architettura (a 32 bit o a 64 bit) di Microsoft Teams è indipendente dall'architettura di Windows e di Office installata.

Il client Windows viene distribuito nella cartella AppData, all'interno del profilo dell'utente. La distribuzione nel profilo locale dell'utente consente di installare il client senza bisogno di diritti elevati. Il client Windows utilizza le posizioni seguenti:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Quando gli utenti avviano per la prima volta una chiamata usando il client di Microsoft Teams, potrebbe comparire un avviso relativo alle impostazioni di Windows Firewall in cui si chiede di consentire la comunicazione. Si potrebbe anche indicare agli utenti di ignorare il messaggio, perché la chiamata funzionerà anche se l'avviso viene ignorato.

![Screenshot di una finestra di dialogo Avviso di sicurezza di Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configurazione di Windows Firewall verrà modificata anche se il messaggio viene ignorato selezionando "Annulla". Verranno create due regole in entrata per teams.exe, con l'azione Blocca per i protocolli TCP e UDP.

Se si vuole impedire ai team di richiedere agli utenti di creare regole del firewall quando gli utenti effettuano la prima chiamata da teams, usare la [regola del firewall in ingresso script di PowerShell di esempio](#sample-powershell-script---inbound-firewall-rule) di seguito. 

### <a name="mac"></a>Mac

Gli utenti Mac possono installare Teams con un file di installazione PKG per i computer che eseguono macOS. Per installare il client Mac è necessario l'accesso amministrativo. Il client macOS viene installato nella cartella /Applicazioni.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installare Teams usando il file PKG

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

Gli amministratori IT possono usare la distribuzione gestita di Teams per distribuire i file di installazione in tutti i Mac dell'organizzazione, ad esempio Jamf Pro.

> [!NOTE]
> Se si verificano problemi durante l'installazione del file PKG, inviare una segnalazione a Microsoft. Nella sezione **Feedback** alla fine di questo articolo fare clic su **Feedback sul prodotto**.

### <a name="linux"></a>Linux

Gli utenti potranno installare pacchetti Linux nativi nei formati `.deb` e `.rpm`.
L'installazione del pacchetto DEB o RPM installerà automaticamente il repository del pacchetto.
- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams` 

La chiave di firma per abilitare l'aggiornamento automatico usando il gestore pacchetti del sistema viene installata automaticamente. Tuttavia, è disponibile anche alla pagina: (https://packages.microsoft.com/keys/microsoft.asc). Microsoft Teams viene aggiornato mensilmente. Se il repository è stato installato correttamente, il gestore pacchetti del sistema dovrebbe gestire l'aggiornamento automatico esattamente come per gli altri pacchetti presenti nel sistema.

> [!NOTE] 
> Se si trova un bug, inviarlo usando `Report a Problem` all'interno del client. Per i problemi noti, vedere [supportare team nell'organizzazione](Known-issues.md).
> Per il supporto di Teams per Linux è possibile usare il [canale di supporto del forum per Linux su Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html). Assicurarsi di usare il tag `teams-linux` quando si pubblicano le domande. 

#### <a name="install-teams-using-deb-package"></a>Installare Teams usando il pacchetto DEB

1. Scaricare il pacchetto da https://aka.ms/getteams.
2. Installare usando uno dei metodi seguenti:  
    - Aprire lo strumento di gestione dei pacchetti appropriato e seguire il processo guidato di installazione delle app di Linux.
    - Se si preferisce usare Terminale, digitare: `sudo apt install **teams download file**`

È possibile avviare Teams tramite Attività o tramite Terminale digitando `Teams`. 

#### <a name="install-teams-using-rpm-package"></a>Installare Team usando il pacchetto RPM

1. Scaricare il pacchetto da https://aka.ms/getteams.
2. Installare usando uno dei metodi seguenti:
    - Aprire lo strumento di gestione dei pacchetti appropriato e seguire il processo guidato di installazione delle app di Linux.
    - Se si preferisce usare Terminale, digitare: `sudo yum install **teams download file**`

È possibile avviare Teams tramite Attività o tramite Terminale digitando `Teams`.

#### <a name="install-manually-from-the-command-line"></a>Eseguire l'installazione manualmente dalla riga di comando

Installare manualmente nelle distribuzioni Debian e Ubuntu:
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

Installare manualmente nelle distribuzioni basate su RHEL, Fedora e CentOS:
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

In alternativa, per usare yum anziché dnf:
```
yum check-update
sudo yum install teams
```

Installare manualmente nelle distribuzioni basate su openSUSE:
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>Client Web 

Il client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) è un client completo di tutte le funzionalità che è possibile usare da più browser. Il client Web supporta le chiamate e le riunioni tramite webRTC, quindi non sono necessari plug-in o download per eseguire Teams in un Web browser. Il browser deve essere configurato in modo da consentire i cookie di terze parti. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Il client Web rileva la versione del browser al momento della connessione a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Se viene rilevata una versione del browser non supportata, blocca l'accesso all'interfaccia Web e invita l'utente a scaricare il client desktop o l'app per dispositivi mobili.

## <a name="mobile-clients"></a>Client per dispositivi mobili

Le app Microsoft Teams per dispositivi mobili sono disponibili per Android e iOS. Sono pensate per gli utenti che partecipano a conversazioni basate su chat mentre sono in movimento e consentono l'esecuzione di chiamate audio peer-to-peer. Per le app per dispositivi mobili, visitare Google Play Store e l'App Store di Apple. L'app per Windows Phone è stata ritirata il 20 luglio 2018 e potrebbe non funzionare più. 

Ecco come [ottenere Teams per Android](get-teams-android-in-china.md) in Cina. 

Le piattaforme supportate dalle app Microsoft Teams per dispositivi mobili sono le seguenti:

-   **Android**: il supporto è limitato alle ultime quattro versioni principali di Android. Quando viene rilasciata una nuova versione principale di Android, sono ufficialmente supportate la nuova versione e le tre versioni precedenti.

-   **iOS**: il supporto è limitato alle ultime due versioni principali di iOS. Quando viene rilasciata una nuova versione principale di iOS, sono ufficialmente supportate la nuova versione e la versione precedente.

> [!NOTE]
> Perché Teams funzioni come previsto, la versione per dispositivi mobili deve essere disponibile al pubblico.

Le app per dispositivi mobili vengono distribuite e aggiornate solo tramite l'app store della piattaforma corrispondente. La distribuzione delle app per dispositivi mobili tramite MDM o sideload non è supportata da Microsoft. Dopo l'installazione in una piattaforma mobile supportata, l'app Teams per dispositivi mobili sarà supportata purché la versione rientri entro tre mesi dalla versione corrente.


| | | |
|---------|---------|---------|
|![Icona che descrive un punto decisionale](media/Get_clients_for_Microsoft_Teams_image4.png)      |Punto decisionale         |Ci sono limitazioni che impediscono agli utenti di installare il client di Microsoft Teams appropriato nei dispositivi?         |
|![Icona che descrive i passaggi successivi](media/Get_clients_for_Microsoft_Teams_image5.png)     |Passaggi successivi         |Se l'organizzazione limita l'installazione di software, accertarsi che la procedura sia compatibile con Microsoft Teams. Nota: i diritti di amministratore non sono necessari per l'installazione del client in un PC ma sono necessari per l'installazione in un Mac.         |

## <a name="client-update-management"></a>Gestione degli aggiornamenti del client

I client vengono aggiornati automaticamente dal servizio Microsoft Teams e non è necessario alcun intervento da parte dell'amministratore IT. Se è disponibile un aggiornamento, il client lo scarica automaticamente e, quando l'app resta inattiva per un certo periodo di tempo, avvia il processo di aggiornamento.

## <a name="client-side-configurations"></a>Configurazioni lato client

Attualmente non sono disponibili opzioni supportate per configurare il client tramite amministrazione del tenant, PowerShell, oggetti Criteri di gruppo o il Registro di sistema.

## <a name="notification-settings"></a>Impostazioni di notifica

Per gli amministratori IT non sono attualmente disponibili opzioni per configurare le impostazioni di notifica sul lato client. Tutte le opzioni di notifica sono impostate dall'utente. La figura seguente illustra le impostazioni predefinite del client.

![Screenshot delle impostazioni di notifica.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a>Esempio di script di PowerShell-regola del firewall in ingresso

Questo script di esempio, che deve essere eseguito nei computer client nel contesto di un account amministratore con privilegi elevati, creerà una nuova regola del firewall in entrata per ogni cartella utente trovata in c:\Users. Questa regola impedisce all'applicazione di chiedere agli utenti di creare regole del firewall quando effettuano la loro prima chiamata da Teams. 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
