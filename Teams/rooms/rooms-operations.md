---
title: Manutenzione e operazioni di Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Leggere questo argomento per informazioni sulla gestione di Microsoft Teams Rooms, la nuova generazione di Skype Room Systems.
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117434"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Manutenzione e operazioni di Microsoft Teams Rooms 
 
Leggere questo argomento per informazioni sulla gestione di Microsoft Teams Rooms, la nuova generazione di Skype Room Systems.
  
Microsoft Teams Rooms è l'ultima soluzione di conferenza di Microsoft progettata per trasformare la sala riunioni in un'esperienza di collaborazione completa. Gli utenti potranno usufruire della sua familiare interfaccia di Microsoft Teams o Skype for Business e gli amministratori IT apprezzeranno un'app Riunione Skype di Windows 10 facilmente distribuita e gestita. Microsoft Teams Rooms è progettato per sfruttare le apparecchiature esistenti come i pannelli LCD per facilitare l'installazione per portare Microsoft Teams o Skype for Business nella sala riunioni.
  
Con un'ulteriore configurazione, la gestione remota è possibile usando Monitor di Microsoft Azure, come descritto in Pianificare la gestione delle sale di Microsoft Teams con [Monitor di Azure,](azure-monitor-plan.md)Distribuire la gestione delle sale di Microsoft Teams con [Monitor di Azure,](azure-monitor-deploy.md)Gestire i dispositivi di Microsoft Teams Rooms con [Monitor di Azure.](azure-monitor-deploy.md) È anche possibile gestire le impostazioni della console di Microsoft Teams Rooms in remoto con un file di configurazione [XML,](xml-config-file.md)che include l'applicazione di un tema di visualizzazione personalizzato. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Raccolta di log nelle chat room di Microsoft Teams
<a name="Logs"> </a>

Per raccogliere i log, è necessario richiamare lo script di raccolta dei log fornito con l'app Microsoft Teams Rooms. In modalità amministratore avviare un prompt dei comandi con privilegi elevati ed eseguire il comando seguente:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

I log verranno restituiti come file ZIP in c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Fronte delle impostazioni di visualizzazione della sala
<a name="Display"> </a>

Configurare la visualizzazione anteriore della chat room in modalità estesa. In questo modo si garantisce che l'interfaccia utente della console non sia duplicata sullo schermo quando si esegue il ciclo dell'alimentazione sullo schermo.
  
> [!NOTE]
> Se si vuole che lo schermo anteriore della sala si sbiliti automaticamente a un'origine video attiva , ad esempio una console MTR, quando la fonte si riattiva dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, a condizione che l'hardware sottostante supporti la funzionalità. Una TV consumer usata come schermo davanti alla sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionata (che potrebbe non supportare CEC, vedere la documentazione del supporto del produttore), potrebbe essere necessario un controller come [hd-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Reimpostazione delle chat room di Microsoft Teams (ripristino in fabbrica)
<a name="Reset"> </a>

Se Microsoft Teams Rooms non è in esecuzione, l'esecuzione di un ripristino di fabbrica potrebbe risultare utile. A questo scopo, usare lo strumento di ripristino di [Microsoft Teams Room](recovery-tool.md) e seguire le istruzioni per il ripristino in fabbrica.

> [!NOTE]
> Esiste un problema noto per cui le chat room di Microsoft Teams possono diventare inutilizzabili se durante il processo di reimpostazione di Windows è selezionata l'opzione Mantieni i miei file - Rimuove app e **impostazioni,** ma mantiene i file personali. Non *usare* questa opzione.
  
## <a name="supported-remote-options"></a>Opzioni remote supportate
<a name="RemoteOptions"> </a>

La tabella seguente riepiloga le possibili operazioni remote e i metodi che è possibile usare per eseguire queste operazioni.
  

|Gruppo di lavoro|Non aggiunto a un dominio|Dominio aggiunto|
|:-----|:-----|:-----|
|Riavvia  <br/> |Interfaccia di amministrazione di Teams  <br/> Desktop remoto  <br/> Powershell remoto  <br/> | <br/>Desktop remoto (richiede un'ulteriore configurazione)  <br/> Remote Powershell (richiede un'ulteriore configurazione)  <br/> Configuration Manager  <br/> |
|Aggiornare il sistema operativo  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Aggiornamento dell'app  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configurazione dell'account  <br/> |Interfaccia di amministrazione di Teams  <br/> |Interfaccia di amministrazione di Teams  <br/> |
|Log di Access  <br/> |Interfaccia di amministrazione di Teams  <br/> |Interfaccia di amministrazione di Teams <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurazione di Criteri di gruppo per Le chat room di Microsoft Teams
<a name="GroupPolicy"> </a>

Questa sezione illustra le impostazioni di sistema da cui Microsoft Teams Rooms dipende per il corretto funzionamento. Quando si partecipa a Microsoft Teams Rooms a un dominio, assicurarsi che i criteri di gruppo non esercitino l'override delle impostazioni nella tabella seguente.
  

|Impostazione|Consente|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Consente l'avvio di Microsoft Teams Rooms  <br/> |
|Power Management - \> In AC, disattivare lo schermo dopo 10 minuti  <br/> Gestione risparmio energia - \> In modalità di sospensione, non mettere mai in sospensione il sistema  <br/> |Consente a Microsoft Teams Rooms di disattivare gli schermi collegati e riattivarsi automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oppure mezzi equivalenti per disabilitare la scadenza delle password nell'account locale. Se non si riesce a farlo, l'account Skype non riesce ad accedere lamentando una password scaduta. Si noti che questa operazione influisce su tutti gli account locali nel computer e quindi la mancata impostazione di questa impostazione causerà anche la scadenza dell'account amministrativo nella casella.  <br/> |Consente all'account Skype di accedere sempre  <br/> |
   
Il trasferimento di file tramite Criteri di gruppo è illustrato in [Configurare un elemento file.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

> [!NOTE]
> Quando il dispositivo Microsoft Teams Rooms è compatibile con la versione successiva del sistema operativo Windows 10, il dispositivo viene aggiornato automaticamente alla versione successiva tramite Windows Update. Il dispositivo Microsoft Teams Rooms non deve essere aggiornato alla prossima versione di Windows 10 manualmente o tramite l'abilitazione dei criteri di gruppo di Windows Update for Business (WUFB) "Selezionare il livello di conformità di Windows per gli aggiornamenti da ricevere" e "Selezionare quando vengono ricevuti gli aggiornamenti delle build di anteprima e delle funzionalità" tramite l'oggetto Criteri di gruppo. Un dispositivo con questi criteri di gruppo abilitato è noto per i problemi con l'aggiornamento del sistema operativo Windows 10 da parte dell'app Microsoft Teams Rooms.

## <a name="remote-management-using-powershell"></a>Gestione remota con PowerShell
<a name="RemotePS"> </a>

È possibile eseguire le operazioni di gestione seguenti in remoto usando PowerShell (vedere la tabella seguente per esempi di script):
  
- Scarica i dispositivi collegati
- Ottenere lo stato dell'app
- Ottieni informazioni di sistema
- Riavvia il sistema
- Recuperare i log
- Trasferire file (richiede una chat room di Microsoft Teams appartenente a un dominio)
    
> [!NOTE]
> Questa funzionalità è disattivata per impostazione predefinita. È necessario abilitare PowerShell remoto per l'ambiente nel sistema Microsoft Teams Rooms per eseguire le operazioni seguenti. Per informazioni su come abilitare PowerShell remoto, vedere la documentazione in **[Enable-PSRemoting.](/powershell/module/microsoft.powershell.core/enable-psremoting)**
  
Ad esempio, è possibile abilitare Remote PowerShell nel modo seguente:
  
1. Accedere come amministratore in un dispositivo Microsoft Teams Rooms.
2. Aprire un prompt dei comandi di PowerShell con privilegi elevati.
3. Immettere il comando seguente: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Aprire Criteri di sicurezza locali e aggiungere il gruppo di sicurezza *Amministratori* **a** Impostazioni sicurezza Criteri locali Assegnazione diritti utente Accesso al  >    >    >  **computer dalla rete.**

Per eseguire un'operazione di gestione:
  
1. Accedere a un PC con le credenziali dell'account che hanno l'autorizzazione per eseguire i comandi di PowerShell in un dispositivo Microsoft Teams Rooms.
2. Aprire un normale prompt dei comandi di PowerShell nel PC.
3. Copiare il testo del comando dalla tabella seguente e incollarlo al prompt dei comandi.
4. Sostituire  `<Device fqdn>` i campi con valori FQDN appropriati per l'ambiente.
5. Sostituire con il nome file e il percorso locale del file di SkypeSettings.xml master  *\<path\>*  (o immagine del tema).
    
Per ottenere i dispositivi collegati
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Ottenere lo stato dell'app
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Ottieni informazioni di sistema
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Riavvia il sistema
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperare i log
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Inserire un file di configurazione XML (o un elemento grafico del tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Aggiornamenti software
<a name="SWupdate"> </a>

Per impostazione predefinita, Microsoft Teams Rooms prova a connettersi a Windows Store per ottenere l'ultima versione del software Microsoft Teams Rooms, in modo che il dispositivo richieda un normale accesso a Internet. Prima di contattare Microsoft per problemi di supporto, assicurati che il dispositivo Microsoft Teams Rooms sia caricato con la versione più recente dell'app.
  
Per impostazione predefinita, Microsoft Teams Rooms si connette a Windows Update per recuperare gli aggiornamenti del firmware del sistema operativo e delle periferiche USB e le installa al di fuori dell'orario di ufficio configurato. È possibile configurare l'orario di ufficio accedendo all'account di amministratore ed eseguendo l'app Impostazioni.
  
Se si vogliono gestire gli aggiornamenti manualmente e non si riesce a seguire la normale procedura per [Microsoft Store per](https://businessstore.microsoft.com/store) le aziende per distribuire le app [offline,](/microsoft-store/distribute-offline-apps)è possibile acquisire il file APPX appropriato e le dipendenze dal [kit](https://go.microsoft.com/fwlink/?linkid=851168) di distribuzione (dalle istruzioni per configurare una console di Microsoft [Teams Rooms)](console.md)che può essere usato con Configuration Manager. Il rilascio del kit di distribuzione è in ritardo rispetto al rilascio dello store, quindi potrebbe non corrispondere sempre all'ultima build disponibile.
  
### <a name="to-update-using-powershell"></a>Per eseguire l'aggiornamento con Powershell

1. Estrarre il pacchetto dal file [MSI](https://go.microsoft.com/fwlink/?linkid=851168) di installazione in una condivisione a cui il dispositivo può accedere.
2. Eseguire lo script seguente per i dispositivi Microsoft Teams Rooms, modificando la condivisione \<share\> del dispositivo in base alle esigenze:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Modalità di amministrazione e gestione dei dispositivi
<a name="AdminMode"> </a>

Alcune funzioni di gestione, come l'installazione manuale di un certificato CA privato, richiedono l'inserimento del dispositivo Surface Pro in modalità amministratore. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passaggio alla modalità di amministrazione e ritorno quando l'app Microsoft Teams Rooms è in esecuzione

1. Blocca le chiamate in corso e torna alla schermata iniziale.
2. Selezionare l'icona a forma di ingranaggio e visualizzare il menu (le opzioni sono **Impostazioni,** **Accessibilità** e **Riavvia dispositivo).**
3. Selezionare **Impostazioni**.
4. Immettere la password dell'amministratore. Verrà visualizzata la schermata Configurazione.  Se il dispositivo non fa parte di un dominio, per impostazione predefinita verrà usato l'account amministrativo locale (nome utente "Amministratore"). La password predefinita per questo account è "sfb", modificare la password il prima possibile. Se il computer fa parte di un dominio, è possibile accedere con un account di dominio con privilegi appropriati. 
5. Selezionare **Impostazioni di Windows** nella colonna sinistra.
6. Scegliere **Accedi all'amministratore**.
7. Immettere la password dell'amministratore. In questo modo si disconnette l'app e si accede alla schermata di accesso a Windows. 
8. Accedere al desktop con le credenziali amministrative. Avrai i privilegi necessari per gestire il dispositivo.
9. Eseguire le attività amministrative necessarie.
10. Disconnettersi dall'account amministratore.
11. Tornare a Microsoft Teams Rooms selezionando l'icona dell'account utente sul lato sinistro dello schermo e quindi **skype**.
    
    Se **l'utente Skype** non è presente  nell'elenco, potrebbe essere necessario selezionare un altro utente e immettere **.\skype** come nome utente ed eseguire l'accesso.
    
La console è tornata nella modalità di funzionamento normale. La procedura seguente richiede di collegare una tastiera al dispositivo, se non è già collegata. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Passaggio alla modalità di amministrazione e ritorno quando l'app Microsoft Teams Rooms si arresta in modo anomalo

1. Premere il tasto Windows cinque volte in rapida successione. Verrà visualizzata la schermata di accesso di Windows. 
2. Accedere al desktop con le credenziali amministrative.
3. Eseguire le attività amministrative necessarie.
4. Al termine, riavviare il computer.

    > [!NOTE]
    > Questo metodo non disconnette l'utente Skype o termina normalmente l'app, ma la userebbe se l'app non rispondeva e l'altro metodo non era disponibile. 

   La console viene riavviata nella modalità di funzionamento normale, eseguendo l'app Microsoft Teams Rooms. È possibile rimuovere la tastiera, se è stata collegata per consentire di eseguire questa procedura.
   ## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
   <a name="TS"> </a>

- Gli inviti alle riunioni potrebbero non essere visualizzati quando vengono inviati oltre i confini del dominio, ad esempio tra due società. In questi casi, gli amministratori IT devono decidere se consentire agli utenti esterni di pianificare una riunione.
- Microsoft Teams Rooms non supporta i reindirizzamenti di Individuazione automatica di Exchange tramite Exchange 2010.
- In generale, è consigliabile che gli amministratori IT disabilitino gli endpoint audio che non intendono usare.
- Nel caso in cui un'immagine speculare sia visualizzata nell'anteprima della sala, l'amministratore IT può correggere l'impostazione ciclica dell'alimentazione della fotocamera o capovolgere l'orientamento dell'immagine usando il telecomando della fotocamera.
- Si è verificata una perdita dell'accesso al touchscreen della console. In questi casi, il problema viene talvolta risolto riavviando il sistema Microsoft Teams Rooms.
- È stata nota la perdita dell'audio locale durante la connessione di un PC alla console tramite l'ingestione cablata. In questi casi, il riavvio del PC può risolvere il problema di riproduzione audio locale.
