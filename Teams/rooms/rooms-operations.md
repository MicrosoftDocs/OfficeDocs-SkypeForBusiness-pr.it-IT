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
description: Leggere questo argomento per informazioni sulla gestione di Microsoft Teams Room, la nuova generazione di Skype Room Systems.
ms.openlocfilehash: a6ab68200002035632314ac976cd45a2ee4ff714
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662461"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Manutenzione e operazioni di Microsoft Teams Rooms 
 
Leggere questo argomento per informazioni sulla gestione di Microsoft Teams Room, la nuova generazione di Skype Room Systems.
  
Sale di Microsoft Teams è l'ultima soluzione di conferenza di Microsoft progettata per trasformare la sala riunioni in un'esperienza collaborativa completa. Gli utenti apprezzeranno la nota interfaccia di Microsoft Teams o Skype for Business e gli amministratori IT apprezzeranno un'app Riunione Skype Per Windows 10 facilmente distribuita e gestita. Microsoft Teams Rooms è progettato per sfruttare apparecchiature esistenti come i pannelli LCD per facilitare l'installazione, per portare Microsoft Teams o Skype for Business nella sala riunioni.
  
Con una configurazione aggiuntiva, la gestione remota è possibile usare Microsoft Azure Monitor, come descritto in Pianificare la gestione delle sale di Microsoft Teams con [Il monitor Di Azure,](azure-monitor-plan.md)distribuire la gestione delle sale di Microsoft Teams con Il monitor [di Azure,](azure-monitor-deploy.md)gestire i dispositivi delle sale di Microsoft Teams con [Il monitor di Azure.](azure-monitor-deploy.md) È anche possibile gestire le impostazioni della console di Microsoft Teams Rooms in remoto con un file di configurazione [XML,](xml-config-file.md)che include l'applicazione di un tema di visualizzazione personalizzato. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Raccolta di log nelle sale di Microsoft Teams
<a name="Logs"> </a>

Per raccogliere i log, è necessario richiamare lo script della raccolta di log fornito con l'app Sale di Microsoft Teams. In modalità amministratore avviare un prompt dei comandi con privilegi elevati ed eseguire il comando seguente:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

L'output dei log verrà generato come file ZIP in c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Fronte delle impostazioni di visualizzazione della sala
<a name="Display"> </a>

Configurare la visualizzazione anteriore della sala alla modalità estesa. In questo modo, l'interfaccia utente della console non verrà duplicata sullo schermo durante l'accensione dello schermo.
  
> [!NOTE]
> Se si desidera che la visualizzazione anteriore della stanza passare automaticamente a un'origine video attiva (ad esempio una console MTR) quando l'origine si riattiva dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, a condizione che l'hardware sottostante supporti la funzionalità. Una TV consumer usata come schermo davanti alla sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionata (che potrebbe non supportare CEC, consulta la documentazione del supporto tecnico del produttore), potrebbe essere necessario un controller come [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Reimpostazione sale di Microsoft Teams (Ripristino delle impostazioni factory)
<a name="Reset"> </a>

Se La funzionalità Sale di Microsoft Teams non è in esecuzione, potrebbe essere utile eseguire un ripristino delle impostazioni factory. A questo scopo, usare lo strumento di ripristino delle chat [room di Microsoft Teams](recovery-tool.md) e seguire le istruzioni per il ripristino del produttore.

> [!NOTE]
> Esiste un problema noto in cui le sale di Microsoft Teams possono diventare inutilizzabili se l'opzione Mantieni i file - Rimuove app e **impostazioni,** mantenendo però i file personali selezionata durante il processo di reimpostazione di Windows. Non *usare* questa opzione.
  
## <a name="supported-remote-options"></a>Opzioni remote supportate
<a name="RemoteOptions"> </a>

La tabella seguente riepiloga le possibili operazioni remote e i metodi che è possibile usare per eseguire queste operazioni.
  

|Gruppo di lavoro|Non aggiunto a un dominio|Domain joined|
|:-----|:-----|:-----|
|Riavvia  <br/> |Desktop remoto  <br/> Powershell remoto  <br/> |Desktop remoto (richiede ulteriori configurazioni)  <br/> Remote Powershell (richiede ulteriori configurazioni)  <br/> Configuration Manager  <br/> |
|Aggiornare il sistema operativo  <br/> |Windows Update  <br/> |Windows Update  <br/> Windows Server Update Services  <br/> |
|Aggiornamento dell'app  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configurazione dell'account Skype  <br/> |Non attualmente supportato  <br/> |Non attualmente supportato  <br/> |
|Log di Access  <br/> |Non attualmente supportato  <br/> |Non attualmente supportato  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurazione di Criteri di gruppo per sale di Microsoft Teams
<a name="GroupPolicy"> </a>

Questa sezione illustra le impostazioni di sistema da cui Microsoft Teams Rooms dipende per il corretto funzionamento. Quando si uniscono sale di Microsoft Teams a un dominio, assicurarsi che i criteri di gruppo non sostituiscono le impostazioni della tabella seguente.
  

|Impostazione|Consente|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Consente l'avvio delle sale di Microsoft Teams  <br/> |
|Gestione risparmio energia - \> Su SCHERMO, disattivare lo schermo dopo 10 minuti  <br/> Gestione del risparmio di energia - \> Su CA, non mettere mai in sospensione il sistema  <br/> |Consente alle sale di Microsoft Teams di disattivare gli schermi collegati e riattivarsi automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O un metodo equivalente per disabilitare la scadenza della password nell'account locale. Se non si riesce a eseguire questa operazione, l'accesso all'account Skype non riesce, lamentando la password scaduta. Tenere presente che questa modifica influisce su tutti gli account locali del computer e quindi la mancata impostazione causerà anche la scadenza dell'account amministrativo nella casella.  <br/> |Consente all'account Skype di accedere sempre  <br/> |
   
Il trasferimento di file tramite Criteri di gruppo è illustrato in [Configurare un elemento file.](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

> [!NOTE]
> Quando il dispositivo Microsoft Teams Rooms è compatibile con la prossima versione di Windows 10 OS, il dispositivo si aggiorna automaticamente alla versione successiva tramite Windows Update. Il dispositivo Microsoft Teams Rooms non deve essere aggiornato manualmente alla prossima versione di Windows 10 o tramite l'abilitazione dei criteri di gruppo di Windows Update for Business (WUFB) "Seleziona il livello di conformità di Windows per gli aggiornamenti che vuoi ricevere" e "Seleziona quando vengono ricevuti le build di anteprima e gli aggiornamenti delle funzionalità" tramite l'oggetto Criteri di gruppo. È noto che in un dispositivo con questi criteri di gruppo abilitati si verificano problemi con l'aggiornamento del sistema operativo Windows 10 tramite l'app Sale di Microsoft Teams.

## <a name="remote-management-using-powershell"></a>Gestione remota con PowerShell
<a name="RemotePS"> </a>

È possibile eseguire le operazioni di gestione seguenti in remoto con PowerShell (vedere la tabella seguente per esempi di script):
  
- Scarica dispositivi collegati
- Ottenere lo stato dell'app
- Ottieni info di sistema
- Riavvia il sistema
- Recuperare i log
- Trasferire file (richiede una chat room di Microsoft Teams con un dominio)
    
> [!NOTE]
> Questa funzionalità è disattivata per impostazione predefinita. È necessario abilitare una sessione remota di PowerShell per l'ambiente nel sistema Microsoft Teams Room per eseguire le operazioni seguenti. Fare riferimento alla documentazione su **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** per informazioni su come abilitare una sessione remota di PowerShell.
  
Ad esempio, è possibile abilitare Una sessione remota di PowerShell come segue:
  
1. Accedere come amministratore in un dispositivo Microsoft Teams Rooms.
2. Aprire un prompt dei comandi di PowerShell con privilegi elevati.
3. Immettere il comando seguente: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Aprire i criteri di sicurezza locali e aggiungere il gruppo di sicurezza *Administrators* a Impostazioni di sicurezza - Assegnazione di diritti utente a questo  >    >    >  **computer dalla rete.**

Per eseguire un'operazione di gestione:
  
1. Accedere a un PC con credenziali dell'account che dispongono dell'autorizzazione per eseguire i comandi di PowerShell in un dispositivo Microsoft Teams Rooms.
2. Aprire un normale prompt dei comandi di PowerShell nel PC.
3. Copiare il testo del comando dalla tabella seguente e incollarlo al prompt dei comandi.
4. Sostituire  `<Device fqdn>` i campi con valori FQDN appropriati per l'ambiente.
5. Sostituire con il nome file e il percorso locale del  *\<path\>*  file di SkypeSettings.xml master (o immagine del tema).
    
Per ottenere dispositivi collegati
  
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

Push di un file di configurazione XML (o elemento grafico tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Aggiornamenti software
<a name="SWupdate"> </a>

Per impostazione predefinita, Microsoft Teams Rooms cerca di connettersi a Windows Store per ottenere l'ultima versione del software Microsoft Teams Rooms, quindi il dispositivo richiederà un normale accesso a Internet. Prima di contattare Microsoft per problemi di supporto, assicurarsi che il dispositivo Microsoft Teams Rooms sia caricato con la versione più recente dell'app.
  
Per impostazione predefinita, le sale di Microsoft Teams si connettono a Windows Update per recuperare gli aggiornamenti del firmware del sistema operativo e delle periferiche USB e le installa al di fuori dell'orario di ufficio configurato. È possibile configurare l'orario di ufficio accedendo all'account administrator ed eseguendo l'app Impostazioni.
  
Se si desidera gestire gli aggiornamenti manualmente e non si è in grado di seguire la normale procedura per la distribuzione di app [offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)da [Microsoft Store](https://businessstore.microsoft.com/store) per le aziende, è possibile acquisire il file APPX appropriato e le dipendenze dal [kit](https://go.microsoft.com/fwlink/?linkid=851168) di distribuzione (dalle istruzioni per configurare una console di Microsoft [Teams Room)](console.md)che può essere usata con Configuration Manager. Il rilascio del kit di distribuzione è in ritardo rispetto al rilascio dello Store, quindi potrebbe non corrispondere sempre alla build più recente disponibile.
  
### <a name="to-update-using-powershell"></a>Per eseguire l'aggiornamento con Powershell

1. Estrarre il pacchetto dal file [MSI](https://go.microsoft.com/fwlink/?linkid=851168) di installazione in una condivisione a cui il dispositivo può accedere.
2. Eseguire lo script seguente per i dispositivi della chat room di Microsoft Teams, modificando in base \<share\> alle esigenze la condivisione del dispositivo:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Modalità amministratore e gestione dispositivi
<a name="AdminMode"> </a>

Alcune funzioni di gestione, come l'installazione manuale di un certificato CA privato, richiedono l'inserimento del dispositivo Surface Pro in modalità amministratore. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passaggio alla modalità amministratore e ritorno quando l'app Sale di Microsoft Teams è in esecuzione

1. Blocca le chiamate in corso e torna alla schermata iniziale.
2. Selezionare l'icona a forma di ingranaggio e visualizzare il menu (le opzioni **sono Impostazioni,** **Accessibilità** e **Riavvia dispositivo).**
3. Selezionare **Impostazioni.**
4. Immettere la password dell'amministratore. Viene visualizzata la schermata Configurazione.  Se il dispositivo non fa parte di un dominio, verrà usato l'account amministrativo locale (nome utente "Amministratore") per impostazione predefinita. La password predefinita per questo account è "sfb", cambiala il più presto possibile. Se il computer fa parte di un dominio, è possibile accedere con un account di dominio con privilegi appropriati. 
5. Selezionare **Impostazioni di Windows** nella colonna a sinistra.
6. Scegliere **Vai ad Accesso amministratore.**
7. Immettere la password dell'amministratore. In questo modo si disconnette l'app e si accede alla schermata di accesso a Windows. 
8. Accedere al desktop con le credenziali di amministratore. Si dispone dei privilegi necessari per gestire il dispositivo.
9. Eseguire le attività amministrative necessarie.
10. Disconnettersi dall'account amministratore.
11. Tornare alle sale di Microsoft Teams selezionando l'icona dell'account utente all'estrema sinistra dello schermo e selezionando **Skype.**
    
    Se **l'utente Skype** non è presente  nell'elenco, potrebbe essere necessario selezionare un altro utente e immettere **.\skype** come nome utente ed eseguire l'accesso.
    
La console è tornata nella normale modalità di funzionamento. La procedura seguente richiede di collegare una tastiera al dispositivo, se non ne è già collegata una. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Passaggio alla modalità amministratore e ritorno quando l'app Sale di Microsoft Teams si arresta in modo anomalo

1. Premere il tasto WINDOWS cinque volte in rapida successione. Verrà visualizzata la schermata di accesso a Windows. 
2. Accedere al desktop con le credenziali di amministratore.
3. Eseguire le attività amministrative necessarie.
4. Al termine, riavviare il computer.

    > [!NOTE]
    > Questo metodo non disconnette l'utente Skype o termina in modo grace l'app, ma la userebbe se l'app non rispondeva e l'altro metodo non era disponibile. 

   La console viene riavviata nella normale modalità di funzionamento, con l'esecuzione dell'app Sale di Microsoft Teams. È possibile rimuovere la tastiera, se collegata, per consentire l'esecuzione di questa procedura.
   ## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
   <a name="TS"> </a>

- Gli inviti alle riunioni potrebbero non essere visualizzati quando vengono inviati oltre i confini del dominio, ad esempio tra due società. In questi casi, gli amministratori IT devono decidere se consentire agli utenti esterni di pianificare una riunione.
- La chat room di Microsoft Teams non supporta i reindirizzamenti di individuazione automatica di Exchange tramite Exchange 2010.
- In generale, è consigliabile che gli amministratori IT disabilitino gli endpoint audio che non intendono usare.
- Se nell'anteprima della sala viene visualizzata un'immagine speculare, l'amministratore IT può correggere l'alimentazione della videocamera in bicicletta o capovolgere l'orientamento dell'immagine con il telecomando della fotocamera.
- Si è nota la perdita dell'accesso al touchscreen della console. In questi casi, il problema viene talvolta risolto riavviando il sistema Microsoft Teams Rooms.
- Si è verificata una perdita di audio locale durante la connessione di un PC alla console tramite l'ingestimento cablato. In questi casi, il riavvio del PC può risolvere il problema della riproduzione audio locale.
    
