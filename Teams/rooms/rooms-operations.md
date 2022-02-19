---
title: Microsoft Teams Rooms manutenzione e operazioni
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Informazioni sulla gestione dei Microsoft Teams Rooms.
ms.openlocfilehash: 864438890bbaef87842f6cb4b77328906036ea56
ms.sourcegitcommit: 060ba9910b8d74cbf7097cd3b8e2834afdb3db95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2022
ms.locfileid: "62909018"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams Rooms manutenzione e operazioni
 
 
Microsoft Teams Rooms è la soluzione di conferenza di Microsoft progettata per trasformare la sala riunioni in un'esperienza di collaborazione completa. Gli utenti potranno usufruire della sua interfaccia Microsoft Teams o Skype for Business e gli amministratori IT apprezzeranno un'app di Windows 10 Teams Rooms facilmente distribuita e gestita. Microsoft Teams Rooms è progettato per sfruttare le apparecchiature esistenti per facilitare l'installazione per Microsoft Teams o Skype for Business nella sala riunioni.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Raccolta di log in Microsoft Teams Rooms
<a name="Logs"> </a>

Per raccogliere log nell'Teams di amministrazione, passare a Teams **dispositivi > Teams Rooms in Windows**. Selezionare il nome visualizzato del dispositivo per cui si vogliono usare i log. Nel riquadro superiore selezionare "Scarica log dei dispositivi". Dopo la conferma, i log saranno pronti per il download nella scheda Cronologia dopo alcuni minuti.

È anche possibile usare PowerShell per raccogliere log. È necessario richiamare lo script della raccolta di log fornito con l'app Microsoft Teams Rooms log. In [modalità amministratore](rooms-operations.md) avviare un prompt dei comandi con privilegi elevati ed eseguire il comando seguente:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

I log verranno restituiti come file ZIP in c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Parte anteriore dello schermo della sala Impostazioni
<a name="Display"> </a>

Configurare le impostazioni degli display front-of-room per supportare Consumer Electronics Control (CEC) o abilitare la modalità PC.
  
Se si vuole che la visualizzazione anteriore della sala Teams Rooms automaticamente quando si riattiva dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, purché l'hardware sottostante supporti la funzionalità. Un televisore utente usato come display frontale della sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionati (che potrebbe non supportare CEC, fare riferimento alla documentazione di supporto del produttore), potrebbe essere necessario un controller come un [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato.

### <a name="change-scale-and-resolution"></a>Modificare la scala e la risoluzione

Se le dimensioni del carattere sullo schermo frontale della sala sono troppo grandi o piccole, è necessario regolare la risoluzione dello schermo. 

1. Passare alla [modalità di amministrazione](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Selezionare l'icona di avvio. Quindi **Impostazioni > sistema > schermo**

3. Passare a **Scala e layout**, quindi modificare le dimensioni di testo **, app** e altri elementi e impostare la scala su 100%.

4. Impostare la risoluzione dello schermo su 1080p. Se si hanno due monitor, impostare la scala e la risoluzione per entrambi gli schermi.

5. Selezionare quindi l'icona Start e immettere **Prompt dei comandi**. Selezionare **Esegui come amministratore**.

6. Eseguire il comando seguente:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams Rooms ripristino (ripristino in fabbrica)
<a name="Reset"> </a>

Se Microsoft Teams Rooms non è in esecuzione, l'esecuzione di un ripristino di fabbrica potrebbe risultare utile. A questo scopo, usare lo strumento [di Microsoft Teams ripristino della sala e](recovery-tool.md) seguire le istruzioni per il ripristino in fabbrica.

> [!NOTE]
> Esiste un problema noto per cui il Microsoft Teams Rooms può diventare inutilizzabile se l'opzione Mantieni i file **personali -** Rimuove app e impostazioni, ma mantiene i file personali è selezionata durante il processo di Windows reimpostazione. Non *usare* questa opzione.
  
## <a name="supported-remote-options"></a>Opzioni remote supportate
<a name="RemoteOptions"> </a>

La tabella seguente riepiloga le possibili operazioni remote e i metodi che è possibile usare per eseguire queste operazioni.
  

|Gruppo di lavoro|Non aggiunto a un dominio|Dominio aggiunto|
|:-----|:-----|:-----|
|Riavvia  <br/> |Teams di amministrazione  <br/> Desktop remoto  <br/> PowerShell remoto  <br/> | <br/>Desktop remoto (richiede un'ulteriore configurazione)  <br/> Remote PowerShell (richiede un'ulteriore configurazione)  <br/> Configuration Manager  <br/> |
|Aggiornare il sistema operativo  <br/> |Windows aggiornamento  <br/> |Windows aggiornamento  <br/> WSUS  <br/> |
|Aggiornamento dell'app  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configurazione dell'account  <br/> |Teams di amministrazione  <br/> |Teams di amministrazione  <br/> |
|Log di Access  <br/> |Teams di amministrazione  <br/> PowerShell  <br/> |Teams di amministrazione <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurazione di Criteri di gruppo per Microsoft Teams Rooms
<a name="GroupPolicy"> </a>

Questa sezione illustra le impostazioni di sistema Microsoft Teams Rooms da cui dipende il corretto funzionamento. 

L Teams Rooms a un dominio Active Directory offre i vantaggi seguenti:

- L'aggiunta di Teams Rooms consente di concedere a utenti e gruppi di dominio diritti amministrativi. In questo modo, non sarà necessario ricordare la password dell'account di amministratore a livello di computer locale.

- È possibile distribuire Windows di qualità del servizio in Teams Rooms.

- Se si usa Skype for Business, l'aggiunta al dominio Teams Rooms l'importazione della catena di certificati radice privata dell'organizzazione.

Quando si aggiunge Teams Rooms a un dominio, è necessario creare un'unità organizzativa separata, in modo da poter fornire esclusioni di oggetti Criteri di gruppo all'unità organizzativa in cui si trovano tutti gli oggetti Teams Rooms. Disabilitare l'ereditarietà di tutti gli oggetti Criteri di gruppo in modo che le impostazioni di Criteri di gruppo non supportate non vengono applicate Teams Rooms. Creare oggetti computer nell'unità organizzativa prima di Teams Rooms al dominio per assicurarsi che i criteri di gruppo applicati all'unità organizzativa predefinita dei computer non siano applicati.

> [!NOTE]
> Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri di gruppo che potrebbero causare problemi se è impostata l'opzione Nessuna sostituzione. Un criterio di gruppo con set No Override supera un'unità organizzativa con l'opzione Blocca ereditarietà dei criteri impostata.

Molte organizzazioni hanno gli oggetti Criteri di gruppo seguenti, che influiscono sulla Teams Rooms funzionalità. Assicurarsi di ignorare o bloccare l'ereditarietà di questi elementi:

  - Timeout delle sessioni di accesso (blocco automatico)
  - Criteri correlati alla gestione del risparmio energia
  - Richiedere ulteriori passaggi di autenticazione
  - Negazione dell'accesso alle unità locali
  - Richiesta di connessioni di rete lente agli utenti
  - Avviare un determinato programma all'accesso
  - Creare un altro account utente di dominio in tutti i computer aggiunti al dominio.
  - Push Windows Aggiorna a Teams Rooms

Quando si Microsoft Teams Rooms a un dominio, assicurarsi che i criteri di gruppo non esercitino l'override delle impostazioni nella tabella seguente.

|Impostazione|Consente|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Consente Microsoft Teams Rooms l'avvio  <br/> |
|Power Management -\> In AC, disattivare lo schermo dopo 10 minuti  <br/> Gestione risparmio energia -\> In modalità di sospensione, non mettere mai in sospensione il sistema  <br/> |Consente Microsoft Teams Rooms disattivare gli schermi collegati e riattivarsi automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oppure mezzi equivalenti per disabilitare la scadenza delle password nell'account locale. Se non si riesce a eseguire questa operazione, l'account Skype non riesce ad accedere lamentando una password scaduta. Si noti che questa operazione influisce su tutti gli account locali del computer e quindi la mancata impostazione di questa impostazione causerà anche la scadenza dell'account amministrativo nella casella.  <br/> |Consente Skype'account di accesso  <br/> |

> [!NOTE]
> Se Microsoft Teams Rooms è compatibile con la versione successiva di Windows 10 OS, Teams Rooms automaticamente alla versione successiva tramite Windows Update. Microsoft Teams Rooms non deve essere aggiornato alla versione successiva di Windows 10 manualmente o tramite l'abilitazione dei criteri di gruppo di Windows Update for Business (WUFB) "Selezionare il livello di conformità di Windows per gli aggiornamenti da ricevere" e "Selezionare quando vengono ricevute le build di anteprima e gli aggiornamenti delle funzionalità" tramite l'oggetto Criteri di gruppo. Teams Rooms con questi criteri di gruppo abilitati si verificano problemi con gli Windows 10 del sistema operativo.

## <a name="remote-management-using-powershell"></a>Gestione remota con PowerShell
<a name="RemotePS"> </a>

È possibile eseguire le operazioni di gestione seguenti in remoto usando PowerShell (vedere la tabella seguente per gli esempi di script):
  
- Scarica i dispositivi collegati
- Ottenere lo stato dell'app
- Ottieni informazioni di sistema
- Riavvia il sistema
- Recuperare i log
- Trasferimento di file (richiede un account aggiunto al Microsoft Teams Rooms)
    
> [!NOTE]
> Questa funzionalità è disattivata per impostazione predefinita. È necessario abilitare PowerShell remoto per l'ambiente nel sistema Microsoft Teams Rooms per eseguire le operazioni seguenti. Per informazioni su come abilitare PowerShell remoto, vedere la documentazione in **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** .
  
Ad esempio, è possibile abilitare Remote PowerShell nel modo seguente:
  
1. Accedere come amministratore in un Microsoft Teams Rooms dispositivo.
2. Aprire un prompt dei comandi di PowerShell con privilegi elevati.
3. Immettere il comando seguente: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Aprire Criteri di sicurezza locali e aggiungere il  gruppo di sicurezza Administrators a **Criteri** >  Impostazioni **Criteri** >  >  localiUtenti Assegnazione **dirittiAccessire il computer dalla rete**.

Per eseguire un'operazione di gestione:
  
1. Accedere a un PC con le credenziali dell'account che hanno l'autorizzazione per eseguire i comandi di PowerShell in un Microsoft Teams Rooms dispositivo.
2. Aprire un normale prompt dei comandi di PowerShell nel PC.
3. Copiare il testo del comando dalla tabella seguente e incollarlo al prompt dei comandi.
4. Sostituire i  `<Device fqdn>` campi con valori FQDN appropriati per l'ambiente.
5. Sostituire  *\<path\>*  con il nome file e il percorso locale del file di SkypeSettings.xml master (o immagine del tema).
    
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

Per impostazione predefinita, Microsoft Teams Rooms tenta di connettersi al Windows Store per ottenere la versione più recente del software Microsoft Teams Rooms. Di conseguenza, Teams Rooms richiede un normale accesso a Internet. Prima di contattare Microsoft per problemi di supporto, assicurati che Microsoft Teams Rooms sia caricato con la versione più recente dell'app.
  
Microsoft Teams Rooms si connette a Windows aggiornamento per recuperare gli aggiornamenti del firmware del sistema operativo e delle periferiche. Si connette anche al Microsoft Store per recuperare gli aggiornamenti dell'applicazione.

Se è necessario gestire manualmente gli aggiornamenti delle applicazioni, ma non è possibile seguire la normale procedura per [Microsoft Store per le aziende](https://businessstore.microsoft.com/store) per distribuire le app [offline](/microsoft-store/distribute-offline-apps), è possibile acquisire pacchetti di aggiornamento Teams Rooms per eseguire gli aggiornamenti delle app nei sistemi operativi supportati. Il rilascio dell'aggiornamento potrebbe essere in ritardo rispetto al rilascio dello store e potrebbe non corrispondere sempre all'ultima build disponibile. Per [altre informazioni, vedere Aggiornare manualmente Microsoft Teams Rooms dispositivo](manual-update.md).

## <a name="admin-mode-and-device-management"></a>Modalità di amministrazione e gestione dei dispositivi
<a name="AdminMode"> </a>

Alcune funzioni di gestione, ad esempio l'installazione manuale di un certificato CA privato, richiedono l'Teams Rooms in modalità amministratore. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passaggio alla modalità di amministrazione e ritorno quando l'app Microsoft Teams Rooms è in esecuzione

1. Blocca le chiamate in corso e torna alla schermata iniziale.
2. Seleziona l'icona a forma di ingranaggio e visualizza il menu (le **opzioni sono Impostazioni**, **Accessibilità** e **Riavvia dispositivo**).
3. Selezionare **Impostazioni**.
4. Immettere la password di amministratore. Verrà visualizzata la schermata Configurazione.  Se il dispositivo non fa parte di un dominio, per impostazione predefinita verrà usato l'account amministrativo locale (nome utente "Amministratore"). La password predefinita per questo account è 'sfb'. Modificare la password il prima possibile. Se il computer fa parte di un dominio, è possibile accedere con un account di dominio con privilegi appropriati.
5. Selezionare **Windows Impostazioni** nella colonna sinistra.
6. Accedere al desktop con le credenziali amministrative. Avrai i privilegi necessari per gestire il dispositivo.
7. Eseguire le attività amministrative necessarie.
8.  Al termine, riavviare il computer.
    
La console è tornata nella modalità di funzionamento normale. La procedura seguente richiede di collegare una tastiera al dispositivo, se non è già collegata. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Passaggio alla modalità di amministrazione e ritorno quando l'app Microsoft Teams Rooms si arresta in modo anomalo

1. Premere il Windows cinque volte in rapida successione. Verrà visualizzata la schermata di Windows di accesso. 
2. Accedere al desktop con le credenziali amministrative.
3. Eseguire le attività amministrative necessarie.
4. Al termine, riavviare il computer.

    > [!NOTE]
    > Questo metodo non disconnette l'utente di Skype o termina normalmente l'app, ma lo userebbe se l'app non rispondeva e l'altro metodo non era disponibile. 

   La console viene riavviata nella modalità di funzionamento normale, eseguendo l Microsoft Teams Rooms app. È possibile rimuovere la tastiera, se è stata allegata una per completare questa procedura.
   ## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
   <a name="TS"> </a>

- Gli inviti alle riunioni potrebbero non essere visualizzati quando vengono inviati oltre i confini del dominio, ad esempio tra due società. In questi casi, gli amministratori IT devono decidere se consentire agli utenti esterni di pianificare una riunione. Vedere l'articolo per Exchange cmdlet di PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), in particolare il parametro 'ProcessExternalMeetingMessages'.
- Microsoft Teams Rooms non supporta i reindirizzamenti Exchange individuazione automatica tramite Exchange 2010.
- In generale, è consigliabile che gli amministratori IT disabilitino gli endpoint audio che non intendono usare.
- Nel caso in cui un'immagine speculare sia visualizzata nell'anteprima della sala, l'amministratore IT può eseguire la correzione usando l'alimentazione ciclica della fotocamera o capovolgere l'orientamento dell'immagine usando le impostazioni della fotocamera.
- Si è verificata una perdita dell'accesso al touchscreen della console. In questi casi, il problema viene talvolta risolto riavviando Teams Rooms.
- È stata nota la perdita dell'audio locale durante la connessione di un PC alla console tramite l'ingestione cablata. In questi casi, il riavvio del PC può risolvere il problema di riproduzione audio locale.
