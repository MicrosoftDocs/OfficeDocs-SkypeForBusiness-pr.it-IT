---
title: Ottenere client per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i vari client disponibili per Microsoft teams, che includono Web, desktop (Windows e Mac) e dispositivi mobili (Android e iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d656e78ca839255f45e9335ca881c564e07c4cc
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047102"
---
<a name="get-clients-for-microsoft-teams"></a>Ottenere client per Microsoft Teams 
===========================

Microsoft teams include client disponibili per desktop (Windows e Mac), Web e dispositivi mobili (Android e iOS). Questi client richiedono tutti una connessione Internet attiva e non supportano una modalità offline.

> [!NOTE]
> Efficace il 29 novembre 2018 non sarà più possibile usare l'app Microsoft teams per Windows 10 S (Preview), disponibile presso Microsoft Store. È ora possibile scaricare e installare il client desktop di Teams nei dispositivi in cui è in uso la modalità Windows 10 S. Per scaricare il client desktop, vai a [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). Le build MSI del client desktop teams non sono ancora disponibili per i dispositivi che usano la modalità Windows 10 S.
>
> Per altre informazioni sulla modalità Windows 10 S, vedere [Introduzione a Windows 10 in modalità s](https://www.microsoft.com/windows/s-mode). 

<a name="desktop-client"></a>Client desktop
--------------

> [!Tip]
> Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la procedura e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)

Il client desktop Microsoft teams è un'applicazione autonoma ed è [disponibile anche in Office 365 ProPlus](https://docs.microsoft.com/en-us/deployoffice/teams-install). Teams è disponibile sia per Windows (7 +), sia per le versioni a 32 bit che a 64 bit e macOS (10.10 +). In Windows i team richiedono .NET Framework 4,5 o versioni successive; il programma di installazione di teams offrirà l'installazione per se non è disponibile. 

I client desktop supportano il supporto delle comunicazioni in tempo reale (audio, video e condivisione di contenuti) per le riunioni del team, le chiamate di gruppo e quelle private uno-a-uno.

I client desktop possono essere scaricati e installati dagli utenti finali direttamente [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) da se hanno le autorizzazioni locali appropriate (i diritti di amministratore non sono necessari per installare il client teams su un PC, ma sono necessari in un Mac).

Gli amministratori IT possono scegliere il metodo preferito per distribuire i file di installazione nei computer dell'organizzazione, ad esempio System Center Configuration Manager (Windows) o grafp Pro (macOS). Per ottenere il pacchetto MSI per la distribuzione di Windows, vedere [installare Microsoft teams con MSI](msi-deployment.md).  

> [!NOTE]
> La distribuzione del client tramite questi meccanismi è solo per l'installazione iniziale dei client di Microsoft Team e non per gli aggiornamenti futuri.

### <a name="windows"></a>Windows

L'installazione di Microsoft teams per Windows offre programmi di installazione scaricabili in architettura a 32 bit e a 64 bit.

> [!NOTE]
> L'architettura (32 bit e 64 bit) di Microsoft teams è agnostica rispetto all'architettura di Windows e Office installata.

Il client Windows viene distribuito nella cartella AppData che si trova nel profilo dell'utente. La distribuzione nel profilo locale dell'utente consente di installare il client senza richiedere diritti elevati. Il client Windows sfrutta le posizioni seguenti:

- % LocalAppData%\\Microsoft\\Teams

- % LocalAppData%\\Microsoft\\TeamsMeetingAddin

- % AppData%\\Microsoft\\Teams

- % LocalAppData%\\SquirrelTemp

Quando gli utenti avviano una chiamata con il client Microsoft teams per la prima volta, potrebbero notare un avviso con le impostazioni di Windows Firewall che chiedono agli utenti di consentire la comunicazione. Agli utenti potrebbe essere richiesto di ignorare questo messaggio perché la chiamata funzionerà anche quando l'avviso viene chiuso.

![Screenshot della finestra di dialogo avviso di sicurezza di Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configurazione di Windows Firewall verrà modificata anche quando il messaggio viene chiuso selezionando "Annulla". Verranno create due regole in ingresso per Teams. exe con l'azione blocca per i protocolli TCP e UDP.

### <a name="mac"></a>Mac

Gli utenti di Mac possono installare teams usando un file di installazione di PKG per i computer macOS. Per installare il client Mac è necessario l'accesso amministrativo. Il client macOS viene installato nella cartella/Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installare teams usando il file PKG

1. Nella [pagina Download teams](https://teams.microsoft.com/downloads), in **Mac**, fare clic su **Scarica**.
2. Fare doppio clic sul file PKG.
3. Seguire l'installazione guidata per completare l'installazione.
4. I team verranno installati nella cartella/Applications. Si tratta di un'installazione a livello di computer.

> [!NOTE]
> Durante l'installazione, il PKG richiederà le credenziali di amministratore. L'utente deve immettere le credenziali di amministratore, indipendentemente dal fatto che l'utente sia o meno un amministratore.

Se un utente ha attualmente un'installazione DMG di teams e vuole sostituirla con l'installazione di PKG, l'utente deve:

1. Uscire dall'app teams.
2. Disinstallare l'app teams.
3. Installare il file PKG.

Gli amministratori IT possono usare la distribuzione gestita di teams per distribuire i file di installazione in tutti i Mac dell'organizzazione, ad esempio grafp Pro.

> [!NOTE]
> Se si verificano problemi durante l'installazione del PKG, avvisaci. Nella sezione **feedback** alla fine di questo articolo fare clic su **feedback prodotto**.

<a name="web-client"></a>Client Web 
----------

Il client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) è un client completo e funzionale che può essere usato da un'ampia varietà di browser. Il client Web supporta le chiamate e le riunioni tramite webRTC, quindi non è necessario alcun plug-in o download per l'esecuzione di team in un Web browser. Il browser deve essere configurato per consentire i cookie di terze parti. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Il client Web esegue il rilevamento della versione del browser [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)al momento della connessione. Se viene rilevata una versione del browser non supportata, si bloccherà l'accesso all'interfaccia Web e si consiglia che l'utente scarichi il client desktop o l'app per dispositivi mobili.

<a name="mobile-clients"></a>Client per dispositivi mobili
--------------

Le app Microsoft teams per dispositivi mobili sono disponibili per Android e iOS e sono orientate per gli utenti che partecipano a conversazioni basate su chat e consentono chiamate audio peer-to-peer. Per le app per dispositivi mobili, accedi ai negozi di dispositivi mobili di Google Play e all'App Store Apple. L'app Windows Phone è stata ritirata il 20 luglio 2018 e potrebbe non funzionare più. 

Le piattaforme mobili supportate per le app per dispositivi mobili Microsoft teams sono le seguenti:

-   **Android**: 4,4 o versione successiva

-   **iOS**: 10,0 o versione successiva

> [!NOTE]
> La versione per dispositivi mobili deve essere disponibile al pubblico in modo che i team funzionino come previsto.

Le app per dispositivi mobili vengono distribuite e aggiornate solo nell'App Store della piattaforma mobile corrispondente. La distribuzione delle app per dispositivi mobili tramite MDM o il caricamento laterale non è supportata da Microsoft. Quando l'app per dispositivi mobili è stata installata in una piattaforma mobile supportata, l'app teams per dispositivi mobili verrà supportata purché la versione sia entro tre mesi dalla data di rilascio corrente.


| | | |
|---------|---------|---------|
|![Icona che descrive un punto decisionale](media/Get_clients_for_Microsoft_Teams_image4.png)      |Punto decisionale         |Esistono restrizioni per impedire agli utenti di installare il client Microsoft teams appropriato nei propri dispositivi?         |
|![Icona che descrive i passaggi successivi](media/Get_clients_for_Microsoft_Teams_image5.png)     |Operazioni successive         |Se l'organizzazione limita l'installazione del software, verificare che il processo sia compatibile con Microsoft teams. Nota: i diritti di amministratore non sono necessari per l'installazione del client PC, ma sono necessari per l'installazione in un Mac.         |

<a name="client-update-management"></a>Gestione degli aggiornamenti client
------------------------

I client sono attualmente aggiornati automaticamente dal servizio Microsoft teams senza l'intervento dell'amministratore IT richiesto. Se è disponibile un aggiornamento, il client scaricherà automaticamente l'aggiornamento e quando l'app verrà inattiva per un periodo di tempo, il processo di aggiornamento inizierà.

<a name="client-side-configurations"></a>Configurazioni lato client
---------------------------

Attualmente non sono disponibili opzioni supportate per configurare il client tramite l'amministratore del tenant, PowerShell, gli oggetti Criteri di gruppo o il registro di sistema.

<a name="notification-settings"></a>Impostazioni di notifica
----------------------------

Al momento non sono disponibili opzioni per gli amministratori IT per configurare le impostazioni di notifica sul lato client. Tutte le opzioni di notifica vengono impostate dall'utente. La figura seguente illustra le impostazioni predefinite del client.

![Screenshot delle impostazioni delle notifiche.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>Esempio di script di PowerShell
----------------------------

Questo script di esempio, che deve essere eseguito nei computer client nel contesto di un account di amministratore con privilegi elevati, creerà una nuova regola del firewall in ingresso per ogni cartella utente trovata in c:\Users. Quando teams trova questa regola, impedirà all'applicazione teams di richiedere agli utenti di creare regole del firewall quando gli utenti effettuano la prima chiamata da teams. 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
