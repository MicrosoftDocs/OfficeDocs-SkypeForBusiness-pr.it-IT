---
title: Microsoft Teams Rooms la manutenzione e le operazioni
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
ms.localizationpriority: medium
description: Informazioni sulla gestione di Microsoft Teams Rooms.
ms.openlocfilehash: df9760694bd8e0c650be25eec7d435efcae02127
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761058"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams Rooms la manutenzione e le operazioni
 
 
Microsoft Teams Rooms è la soluzione per conferenze di Microsoft progettata per trasformare la sala riunioni in un'esperienza di collaborazione avanzata. Gli utenti apprezzeranno la familiare interfaccia Microsoft Teams o Skype for Business e gli amministratori IT apprezzeranno un'app Windows 10 Teams Rooms facilmente distribuita e gestita. Microsoft Teams Rooms è progettato per sfruttare le apparecchiature esistenti per facilitare l'installazione per portare Microsoft Teams o Skype for Business nella sala riunioni.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Raccolta dei log in Microsoft Teams Rooms
<a name="Logs"> </a>

Per raccogliere i log nell Teams interfaccia di amministrazione, passare a **Teams dispositivi > Teams Rooms in Windows**. Selezionare il nome visualizzato del dispositivo per cui si vogliono eseguire i log. Nel riquadro superiore selezionare "Scarica registri dispositivi". Dopo la conferma, i log saranno pronti per il download nella scheda Cronologia dopo alcuni minuti.

È anche possibile usare PowerShell per raccogliere i log. È necessario richiamare lo script di raccolta log fornito con l'app Microsoft Teams Rooms. In [modalità Amministrazione](rooms-operations.md) avviare un prompt dei comandi con privilegi elevati ed eseguire il comando seguente:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

I log verranno generati come file ZIP in c:\rigel.

### <a name="managing-disk-space"></a>Gestione dello spazio su disco
<a name="Space"> </a>

I log scaricati nel dispositivo possono occupare spazio su disco. Se i registri non vengono regolarmente puliti, possono interferire con la normale funzionalità della stanza. Teams Rooms elimina i log scaricati dopo 30 giorni. Gli amministratori IT possono ignorare la pulizia del log usando l'impostazione del Registro di sistema del dispositivo.

|Impostazione|Permette|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\PPI\SkypeSettings\LogCleanupAgeThreshold  <br/> |Pulisce i log dopo 30 giorni.  <br/> |
  
## <a name="front-of-room-display-settings"></a>Impostazioni dello schermo della sala davanti alla stanza
<a name="Display"> </a>

Configurare le impostazioni degli schermi della parte anteriore della sala per supportare Consumer Electronics Control (CEC) o abilitare la modalità PC.
  
Se si desidera che uno schermo della sala passi automaticamente a Teams Rooms quando viene riattivato dalla modalità standby, è necessario soddisfare determinate condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, purché l'hardware sottostante supporti la funzionalità. Un televisore utente usato come display frontale della sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionati (che potrebbe non supportare CEC, fare riferimento alla documentazione di supporto del produttore), potrebbe essere necessario un controller come un [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato.

### <a name="scale-and-resolution"></a>Scala e risoluzione

Per ottenere Teams Rooms'esperienza progettata, gli schermi della sala devono soddisfare i requisiti di risoluzione e scalabilità.

Per impostare la scala e la risoluzione della schermata Front of Rooms in remoto, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md#set-front-of-room-scale-and-resolution).

Per impostare manualmente la scala e la risoluzione nelle impostazioni di amministrazione Teams chat room:

1. Nella Teams Room passare alla [modalità amministratore](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Seleziona l'icona di avvio. Quindi **Impostazioni > schermo > di sistema**

3. Vai a **Ridimensionamento e layout**, quindi **Modifica le dimensioni di testo, app e altri elementi** e imposta il ridimensionamento su 100%.

4. Imposta la risoluzione dello schermo su 1080p. Se hai due monitor, imposta la scala e la risoluzione per entrambi gli schermi.

5. Seleziona quindi l'icona start e immetti **Prompt dei comandi**. Selezionare **Esegui come amministratore**.

6. Eseguire il comando seguente:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. Riavvia il dispositivo.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>ripristino Microsoft Teams Rooms (ripristino delle impostazioni predefinite)
<a name="Reset"> </a>

Se Microsoft Teams Rooms non funziona bene, il ripristino delle impostazioni predefinite può risultare utile. A questo scopo, usare lo [strumento Microsoft Teams Ripristino della sala](recovery-tool.md) e seguire le istruzioni di ripristino delle impostazioni di fabbrica.

> [!NOTE]
> Esiste un problema noto a causa del quale il Microsoft Teams Rooms può diventare inutilizzabile se l'opzione **Mantieni i miei file - Rimuove app e impostazioni, ma mantiene** selezionata l'opzione file personali durante il processo di reimpostazione Windows. *Non* usare questa opzione.
  
## <a name="supported-remote-options"></a>Opzioni remote supportate
<a name="RemoteOptions"> </a>

La tabella seguente riepiloga le possibili operazioni remote e i metodi che è possibile usare per eseguirle.
  

|Gruppo|Non aggiunto a un dominio|Aggiunta a un dominio|
|:-----|:-----|:-----|
|Riavviare  <br/> |Interfaccia di amministrazione di Teams  <br/> Desktop remoto  <br/> Remote PowerShell  <br/> | <br/>Desktop remoto (richiede un'ulteriore configurazione)  <br/> Remote PowerShell (richiede ulteriori configurazioni)  <br/> Configuration Manager  <br/> |
|Aggiornare il sistema operativo  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Aggiornamento dell'app  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configurazione account  <br/> |Interfaccia di amministrazione di Teams  <br/> |Interfaccia di amministrazione di Teams  <br/> |
|Log di Access  <br/> |Interfaccia di amministrazione di Teams  <br/> PowerShell  <br/> |Interfaccia di amministrazione di Teams <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurazione di Criteri di gruppo per Microsoft Teams Rooms
<a name="GroupPolicy"> </a>

Questa sezione illustra le impostazioni di sistema che Microsoft Teams Rooms dipendono dal corretto funzionamento. 

L'aggiunta di Teams Rooms a un dominio di Active Directory offre i vantaggi seguenti:

- L'Teams Rooms di aggiunta a un dominio consente di concedere a utenti e gruppi di dominio i diritti amministrativi. In questo modo, non sarà necessario ricordare la password dell'account amministratore a livello di computer locale.

- È possibile distribuire Windows configurazione della qualità del servizio in Teams Rooms.

- Se si usa Skype for Business, l'aggiunta al Teams Rooms automatizza l'importazione della catena di certificati radice privata dell'organizzazione.

Quando si aggiunge Teams Rooms a un dominio, è necessario creare un'unità organizzativa (OU) separata, in modo da poter fornire esclusioni oggetto Criteri di gruppo all'unità organizzativa in cui risiedono tutti gli oggetti Teams Rooms. Disabilitare tutta l'ereditarietà dell'oggetto Criteri di gruppo in modo che le impostazioni di Criteri di gruppo non supportate non vengano applicate a Teams Rooms. Creare oggetti computer nell'unità organizzativa prima di unire Teams Rooms al dominio per assicurarsi che i criteri di gruppo applicati all'unità organizzativa computer predefiniti non vengano applicati.

> [!NOTE]
> Anche se si crea un'unità organizzativa separata e si blocca l'ereditarietà, esistono alcuni criteri di gruppo che potrebbero causare problemi se non hanno impostato Nessun override. Un Criteri di gruppo con il set No Override batte un'unità organizzativa con l'ereditarietà dei criteri di blocco impostata.

Molte organizzazioni hanno gli oggetti Criteri di gruppo seguenti, che influiscono sulla funzionalità Teams Rooms. Assicurarsi di ignorare o bloccare l'ereditarietà di:

  - Timeout delle sessioni di accesso (blocco automatico)
  - Criteri correlati alla gestione del risparmio energia
  - Richiesta di ulteriori passaggi di autenticazione
  - Negare l'accesso alle unità locali
  - Richiesta agli utenti di connessioni di rete lente
  - Avviare un determinato programma all'accesso
  - Creare un altro account utente di dominio in tutti i computer aggiunti a un dominio.
  - Spostare Windows Update in Teams Rooms

Quando si aggiunge Microsoft Teams Rooms a un dominio, assicurarsi che i criteri di gruppo non sovrascrivano le impostazioni della tabella seguente.

|Impostazione|Permette|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Consente a Microsoft Teams Rooms di eseguire l'avvio  <br/> |
|Risparmio energia -\> In modalità CA, spegni lo schermo dopo 10 minuti  <br/> Risparmio energia -\> In modalità CA, non sospendere mai il sistema  <br/> |Consente Microsoft Teams Rooms di disattivare gli schermi collegati e riattivarsi automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O mezzi equivalenti per disabilitare la scadenza della password nell'account locale. In caso contrario, l'account Skype potrebbe non riuscire a eseguire l'accesso lamentandosi di una password scaduta. Si noti che questo influisce su tutti gli account locali sul computer, e quindi l'impostazione non viene impostata farà anche scadere anche l'account amministrativo sulla casella.  <br/> |Consente a Skype account di accedere sempre  <br/> |

> [!NOTE]
> Quando Microsoft Teams Rooms è compatibile con la prossima versione di Windows 10 sistema operativo, Teams Rooms esegue automaticamente l'aggiornamento alla versione successiva tramite Windows Update. Microsoft Teams Rooms non devono essere aggiornate manualmente alla versione successiva di Windows 10 o abilitando i criteri di gruppo di Windows Update for Business (WUFB) "Selezionare il livello di conformità Windows per gli aggiornamenti da ricevere" e "Selezionare la data di ricezione delle build di anteprima e degli aggiornamenti delle funzionalità" tramite l'oggetto Criteri di gruppo. Teams Rooms con questi criteri di gruppo abilitati si verificano problemi con Windows 10 aggiornamenti del sistema operativo.

## <a name="remote-management-using-powershell"></a>Gestione remota tramite PowerShell
<a name="RemotePS"> </a>

È possibile eseguire le operazioni di gestione seguenti in remoto usando PowerShell (vedere la tabella seguente per esempi di script):
  
- Scarica i dispositivi collegati
- Ottenere lo stato dell'app
- Ottieni informazioni di sistema
- Riavviare il sistema
- Recuperare i log
- Trasferire file (richiede un Microsoft Teams Rooms aggiunto a un dominio)
    
> [!NOTE]
> Questa funzionalità è disattivata per impostazione predefinita. Per eseguire le operazioni seguenti, è necessario abilitare powerShell remoto per l'ambiente nel sistema Microsoft Teams Rooms. Vedere la documentazione di **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** per informazioni su come abilitare la connessione remota PowerShell.
  
Ad esempio, è possibile abilitare Remote PowerShell come segue:
  
1. Accedi come Amministrazione su un dispositivo Microsoft Teams Rooms.
2. Aprire un prompt dei comandi con privilegi elevati di PowerShell.
3. Immettere il comando seguente: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Aprire i Criteri di sicurezza locali e aggiungere il gruppo di sicurezza *Administrators* **all'assegnazione** >  >  **dei diritti** >  utente criteri locali Impostazioni Accesso a **questo computer dalla rete**.

Per eseguire un'operazione di gestione:
  
1. Accedere a un PC con le credenziali dell'account che dispongono dell'autorizzazione per eseguire i comandi di PowerShell in un dispositivo Microsoft Teams Rooms.
2. Apri un normale prompt dei comandi di PowerShell nel PC.
3. Copiare il testo del comando dalla tabella seguente e incollarlo al prompt dei comandi.
4. Sostituire  `<Device fqdn>` i campi con valori FQDN appropriati per l'ambiente.
5. Sostituisci  *\<path\>*  con il nome file e il percorso locale del file di configurazione SkypeSettings.xml master (o immagine del tema).
    
Per ottenere i dispositivi collegati
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Ottieni lo stato dell'app
  
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

Per impostazione predefinita, Microsoft Teams Rooms tenta di connettersi al Windows Store per ottenere la versione più recente del software Microsoft Teams Rooms. Pertanto, Teams Rooms richiede un accesso a Internet regolare. Prima di contattare Microsoft con problemi di supporto, assicurati che Microsoft Teams Rooms sia caricata con l'ultima versione dell'app.
  
Microsoft Teams Rooms si connette a Windows Update per recuperare gli aggiornamenti del firmware del sistema operativo e delle periferiche. Si connette anche al Microsoft Store per recuperare gli aggiornamenti dell'applicazione.

Se è necessario gestire manualmente gli aggiornamenti delle applicazioni, ma non è possibile seguire la normale procedura per [Microsoft Store per le aziende](https://businessstore.microsoft.com/store) [distribuire le app offline](/microsoft-store/distribute-offline-apps), è possibile acquisire pacchetti di aggiornamento Teams Rooms per eseguire gli aggiornamenti delle app nei sistemi operativi supportati. Il rilascio dell'aggiornamento potrebbe essere in ritardo rispetto al rilascio dello Store e potrebbe non corrispondere sempre all'ultima build disponibile. Per altre informazioni, vedi [Aggiornare manualmente un dispositivo Microsoft Teams Rooms](manual-update.md).

## <a name="admin-mode-and-device-management"></a>modalità Amministrazione e gestione dei dispositivi
<a name="AdminMode"> </a>

Alcune funzioni di gestione, come l'installazione manuale di un certificato CA privato, richiedono l'inserimento di Teams Rooms in modalità Amministrazione. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passaggio alla modalità Amministrazione e ritorno quando l'app Microsoft Teams Rooms è in esecuzione

1. Riaggancia le chiamate in corso e torna alla schermata iniziale.
2. Seleziona l'icona a forma di ingranaggio e visualizza il menu (le opzioni sono **Impostazioni**, **Accessibilità** e **Riavvia dispositivo**).
3. Selezionare **Impostazioni**.
4. Immettere la password dell'amministratore. Verrà visualizzata la schermata Configurazione.  Se il dispositivo non fa parte di un dominio, l'account amministrativo locale (nome utente "Amministrazione") verrà usato per impostazione predefinita. La password predefinita per questo account è 'sfb'. Cambia questa password il prima possibile. Se il computer fa parte di un dominio, è possibile accedere con un account di dominio con privilegi appropriati.
5. Selezionare **Windows Impostazioni** nella colonna sinistra.
6. Accedere al desktop con le credenziali amministrative. Avrai i privilegi necessari per gestire il dispositivo.
7. Eseguire le attività amministrative necessarie.
8.  Al termine, riavvia il computer.
    
La console è tornata in modalità di funzionamento normale. La procedura seguente richiede di collegare una tastiera al dispositivo, se non è già collegata. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Passaggio alla modalità Amministrazione e ritorno quando l'app Microsoft Teams Rooms si arresta in modo anomalo

1. Premere il tasto Windows cinque volte in rapida successione. Verrà visualizzata la schermata di accesso Windows. 
2. Accedere al desktop con le credenziali amministrative.
3. Eseguire le attività amministrative necessarie.
4. Al termine, riavvia il computer.

    > [!NOTE]
    > Questo metodo non disconnette l'utente Skype o termina correttamente l'app, ma se l'app non risponde e l'altro metodo non è disponibile. 

   La console viene riavviato nella modalità di funzionamento normale, eseguendo l'app Microsoft Teams Rooms. Se ne è stata collegata una per completare questa procedura, è possibile rimuovere la tastiera.
   ## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
   <a name="TS"> </a>

- Gli inviti alle riunioni potrebbero non essere visualizzati quando vengono inviati oltre i limiti del dominio, ad esempio tra due società. In questi casi, gli amministratori IT devono decidere se consentire agli utenti esterni di pianificare una riunione. Vedere l'articolo per il cmdlet di Exchange PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), in particolare il parametro 'ProcessExternalMeetingMessages'.
- Microsoft Teams Rooms non supporta Exchange reindirizzamenti automatici tramite Exchange 2010.
- In generale, è buona norma che gli amministratori IT disabilitino gli endpoint audio che non intendono usare.
- Nel caso in cui un'immagine speculare venga visualizzata nell'anteprima della sala, l'amministratore IT può correggere attivando la fotocamera o capovolgendo l'orientamento dell'immagine usando le impostazioni della fotocamera.
- È noto che si è verificata la perdita dell'accesso al touchscreen della console. In questi casi, il problema viene talvolta risolto riavviando Teams Rooms.
- È noto che si è verificata la perdita dell'audio locale durante la connessione di un PC alla console tramite ingest cablato. In questi casi, il riavvio del PC può risolvere il problema di riproduzione audio locale.
