---
title: Manutenzione e operazioni di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Leggere questo argomento per informazioni sulla gestione di Microsoft teams rooms, la nuova generazione di sistemi room Skype.
ms.openlocfilehash: 4e1c554d5ae21d845fed9a543875feb631e0e264
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952729"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Manutenzione e operazioni di Microsoft teams rooms 
 
Leggere questo argomento per informazioni sulla gestione di Microsoft teams rooms, la nuova generazione di sistemi room Skype.
  
Microsoft teams Rooms è la soluzione di conferenza più recente di Microsoft progettata per trasformare la sala riunioni in un'esperienza ricca e collaborativa. Gli utenti apprezzeranno l'interfaccia familiare di Microsoft o Skype for business e gli amministratori IT apprezzeranno un'app di Windows 10 Skype meeting facilmente distribuita e gestita. Microsoft teams Rooms è progettato per sfruttare le attrezzature esistenti, come i pannelli LCD, per facilitare l'installazione per consentire a Microsoft teams o Skype for business di accedere alla sala riunioni.
  
Con la configurazione aggiuntiva, la gestione remota è possibile usando Microsoft Azure monitor come descritto in [pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md), [distribuire Microsoft teams Rooms Management con Azure monitor](azure-monitor-deploy.md), [gestire i dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md). È anche possibile [gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md), che include l'applicazione di un tema di visualizzazione personalizzato. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Raccolta di registri in Microsoft teams rooms
<a name="Logs"> </a>

Per raccogliere i log, è necessario richiamare lo script di raccolta log fornito con l'app Microsoft teams rooms. In modalità amministratore avviare un prompt dei comandi con privilegi elevati ed eseguire il comando seguente:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

I log verranno emessi come file ZIP in c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Inizio delle impostazioni di visualizzazione della sala
<a name="Display"> </a>

Configurare il lato anteriore della visualizzazione della sala in modalità estesa. In questo modo si verificherà che l'interfaccia utente della console non sia duplicata in tale visualizzazione quando si esegue il ciclo di alimentazione sullo schermo.
  
> [!NOTE]
> Se si desidera che venga visualizzata una parte anteriore della visualizzazione della sala per passare automaticamente a una sorgente video attiva, ad esempio una console MTR, quando la sorgente viene riattivata dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa caratteristica è facoltativa ma supportata dal software Microsoft teams rooms, purché l'hardware sottostante supporti la funzionalità. Un televisore consumer usato come parte anteriore della visualizzazione della sala deve supportare la funzionalità CEC (Consumer Electronics Control) di HDMI.  In base al dock o alla console selezionato (che potrebbe non supportare la CEC, vedere la documentazione del supporto del produttore), è possibile che sia necessario un controller come [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Reimpostazione di Microsoft teams Rooms (ripristino di fabbrica)
<a name="Reset"> </a>

Se Microsoft teams Rooms non è in esecuzione bene, potrebbe essere utile eseguire un ripristino di fabbrica. A questo scopo, USA lo [strumento di ripristino della sala Microsoft teams](recovery-tool.md) e segui le istruzioni per il ripristino di fabbrica.

> [!NOTE]
> Si è verificato un problema noto in cui le sale di Microsoft teams possono diventare inutilizzabili se la funzione **Mantieni file-rimuove le app e le impostazioni, ma mantiene l'opzione file personali** selezionata durante il processo di ripristino di Windows. Non *usare questa* opzione.
  
## <a name="supported-remote-options"></a>Opzioni remote supportate
<a name="RemoteOptions"> </a>

La tabella seguente riepiloga le possibili operazioni remote e i metodi che è possibile usare per realizzarle.
  

|Gruppo|Non è stato aggiunto un dominio|Dominio Unito|
|:-----|:-----|:-----|
|Riavviare  <br/> |Desktop remoto  <br/> PowerShell remoto  <br/> |Desktop remoto (richiede ulteriore configurazione)  <br/> PowerShell remoto (richiede ulteriore configurazione)  <br/> SCCM  <br/> |
|Aggiornare il sistema operativo  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Aggiornamento dell'app  <br/> |Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configurazione dell'account Skype  <br/> |Attualmente non supportato  <br/> |Attualmente non supportato  <br/> |
|Registri di Access  <br/> |Attualmente non supportato  <br/> |Attualmente non supportato  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurazione dei criteri di gruppo per le sale di Microsoft Teams
<a name="GroupPolicy"> </a>

In questa sezione vengono illustrate le impostazioni di sistema di cui le sale di Microsoft teams dipendono per funzionare correttamente. Quando si partecipa a Microsoft teams Rooms a un dominio, verificare che i criteri di gruppo non eseguano l'override delle impostazioni nella tabella seguente.
  

|Impostazione|Permette|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Consente l'avvio delle sale di Microsoft Teams  <br/> |
|Power Management-\> in AC, disattivare lo schermo dopo 10 minuti  <br/> Power Management-\> su AC, non posizionare mai il sistema in modalità Sleep  <br/> |Consente alle sale di Microsoft teams di disattivare i display allegati e di riattivarsi automaticamente  <br/> |
|NET account/maxpwage: illimitato  <br/> O un mezzo equivalente per disabilitare la scadenza della password per l'account locale. La mancata esecuzione di questa operazione causerà l'errore di accesso dell'account Skype che lamenta una password scaduta. Tieni presente che questo ha un impatto su tutti gli account locali nel computer e quindi la mancata impostazione di questa operazione causerà anche l'eventuale scadenza dell'account amministrativo nella casella.  <br/> |Consente all'account Skype di accedere sempre  <br/> |
   
Il trasferimento di file tramite criteri di gruppo è illustrato in [configurare un elemento del file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).

> [!NOTE]
> Quando il dispositivo Microsoft teams Rooms è compatibile con la versione successiva del sistema operativo Windows 10, il dispositivo viene aggiornato automaticamente alla versione successiva tramite Windows Update. Il dispositivo Microsoft teams Rooms non deve essere aggiornato manualmente alla prossima versione di Windows 10 o tramite l'abilitazione dei criteri di gruppo di Windows Update for business (WUFB) "Seleziona il livello di conformità di Windows per gli aggiornamenti che vuoi ricevere" e "Seleziona quando si compila l'anteprima e Gli aggiornamenti delle caratteristiche vengono ricevuti tramite GPO. Un dispositivo con questi criteri di gruppo abilitato è noto per l'esecuzione in problemi relativi all'aggiornamento del sistema operativo Windows 10 dall'app Microsoft teams rooms.

## <a name="remote-management-using-powershell"></a>Gestione remota tramite PowerShell
<a name="RemotePS"> </a>

È possibile eseguire le operazioni di gestione seguenti in remoto usando PowerShell (vedere la tabella seguente per gli esempi di script):
  
- Ottenere i dispositivi allegati
- Ottenere lo stato dell'app
- Ottenere informazioni di sistema
- Riavviare il sistema
- Recuperare i registri
- Trasferire file (richiede un dominio-joined Microsoft teams rooms)
    
> [!NOTE]
> Questa funzionalità è disinserita per impostazione predefinita. Per eseguire le operazioni seguenti, è necessario abilitare Remote PowerShell per l'ambiente nel sistema Microsoft teams rooms. Vedere la documentazione relativa a **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** per informazioni su come abilitare Remote PowerShell.
  
Ad esempio, è possibile abilitare Remote PowerShell come indicato di seguito:
  
1. Accedere come amministratore in un dispositivo Microsoft teams rooms.
2. Aprire un prompt dei comandi di PowerShell con privilegi elevati.
3. Immettere il comando seguente: Enable-PSRemoting-force

Per eseguire un'operazione di gestione:
  
1. Accedere a un PC con le credenziali dell'account che dispongano delle autorizzazioni per eseguire i comandi di PowerShell in un dispositivo Microsoft teams rooms.
2. Aprire un prompt dei comandi di PowerShell normale nel PC.
3. Copiare il testo del comando dalla tabella seguente e incollarlo alla richiesta.
4. Sostituire `<Device fqdn>` i campi con valori FQDN appropriati per l'ambiente.
5. Sostituire * \<Path\> * con il nome file e il percorso locale del file di configurazione Master SkypeSettings. XML (o immagine del tema).
    
Per ottenere i dispositivi allegati
  
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

Ottenere informazioni di sistema
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Riavviare il sistema
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperare i registri
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Spingere un file di configurazione XML (o un elemento grafico del tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Aggiornamenti software
<a name="SWupdate"> </a>

Per impostazione predefinita, Microsoft teams Rooms cerca di connettersi a Windows Store per ottenere l'ultima versione del software Microsoft teams rooms, in modo che il dispositivo necessiti di un regolare accesso a Internet. Prima di contattare Microsoft con i problemi di supporto, assicurati che il dispositivo Microsoft teams rooms sia caricato con la versione più recente dell'app.
  
Per impostazione predefinita, Microsoft teams Rooms si connette a Windows Update per recuperare gli aggiornamenti del firmware del sistema operativo e del dispositivo periferico USB e li installa all'esterno degli orari di ufficio configurati. Puoi configurare gli orari di ufficio effettuando l'accesso all'account di amministratore ed eseguendo l'app Impostazioni.
  
Per gestire manualmente gli aggiornamenti e non è possibile seguire la procedura normale per [Microsoft Store for business](https://businessstore.microsoft.com/store) per [distribuire le app offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), è possibile acquisire il file appx appropriato e le dipendenze dal [Kit di distribuzione](https://go.microsoft.com/fwlink/?linkid=851168) (dalle istruzioni per [configurare una console di Microsoft teams Rooms](console.md)) che può essere usata con SCCM. La versione del kit di distribuzione è in ritardo rispetto alla versione dello Store, quindi potrebbe non corrispondere sempre alla build più recente disponibile.
  
### <a name="to-update-using-powershell"></a>Per eseguire l'aggiornamento usando PowerShell

1. Estrai il pacchetto dal file [MSI](https://go.microsoft.com/fwlink/?linkid=851168) di installazione a una condivisione a cui il dispositivo può accedere.
2. Eseguire lo script seguente per la destinazione dei dispositivi Microsoft teams Rooms \<,\> modificando la condivisione alla condivisione del dispositivo in base alle esigenze:
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Modalità di amministrazione e gestione dei dispositivi
<a name="AdminMode"> </a>

Alcune funzioni di gestione, come l'installazione manuale di un certificato CA privato, richiedono l'immissione del dispositivo Surface Pro in modalità amministratore. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passare alla modalità amministratore e viceversa quando è in corso l'app Microsoft teams rooms

1. Riagganciare le chiamate in corso e tornare alla schermata iniziale.
2. Selezionare l'icona dell'ingranaggio e visualizzare il menu (le opzioni sono **Impostazioni**, **accessibilità**e **dispositivo di riavvio** ).
3. Selezionare **Impostazioni**.
4. Immettere la password di amministratore. Verrà visualizzata la schermata di configurazione.  Se il dispositivo non è collegato al dominio, per impostazione predefinita verrà usato l'account amministrativo locale (nome utente "amministratore"). La password predefinita per l'account è "SFB", cambiare la password il prima possibile. Se il computer è collegato al dominio, è possibile accedere con un account di dominio con privilegi appropriati. 
5. Selezionare **impostazioni di Windows** nella colonna sinistra.
6. Scegliere **Accedi ad amministratore**.
7. Immettere la password di amministratore. In questo modo si disconnetterà con garbo l'app e ti porterà alla schermata di accesso di Windows. 
8. Accedere al desktop con le credenziali amministrative. Avrai i privilegi necessari per gestire il dispositivo.
9. Eseguire le attività amministrative necessarie.
10. Disconnettersi dall'account di amministratore.
11. Tornare a Microsoft teams Rooms selezionando l'icona dell'account utente all'estrema sinistra dello schermo e quindi selezionando **Skype**.
    
    Se l'utente **Skype** non è elencato, potrebbe essere necessario selezionare un **altro utente** e immettere **.\skype** come nome utente ed eseguire l'accesso.
    
La console è ora tornata nella modalità operativa normale. La procedura seguente richiede di allegare una tastiera al dispositivo se non ne è già collegata una. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Passare alla modalità amministratore e viceversa quando l'app Microsoft teams Rooms si arresta in modo anomalo

1. Premere il tasto Windows cinque volte in rapida successione. Verrà visualizzata la schermata di accesso di Windows. 
2. Accedere al desktop con le credenziali amministrative.
3. Eseguire le attività amministrative necessarie.
4. Riavviare il computer al termine.

    > [!NOTE]
    > Questo metodo non disconnette l'utente Skype o chiude con garbo l'app, ma la userai se l'app non risponde e l'altro metodo non è disponibile. 

   La console viene riavviata nella modalità operativa normale, in cui è in esecuzione l'app Microsoft teams rooms. È possibile rimuovere la tastiera, se è stata allegata per consentire l'esecuzione di questa procedura.
   ## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
   <a name="TS"> </a>

- Gli inviti alle riunioni potrebbero non essere visualizzati quando vengono inviati oltre i limiti del dominio, ad esempio tra due società. In questi casi, gli amministratori IT devono decidere se consentire agli utenti esterni di pianificare una riunione.
- Microsoft teams Rooms non supporta il reindirizzamento di Exchange Autodiscover tramite Exchange 2010.
- In generale, è consigliabile che gli amministratori IT disattivino eventuali endpoint audio che non intendono usare.
- Se nell'anteprima della sala viene visualizzata un'immagine speculare, l'amministratore IT può correggere l'uso della videocamera in bicicletta o l'orientamento dell'immagine usando il telecomando della videocamera.
- Si nota che la perdita di accesso al touchscreen da console si verifica. In questi casi, il problema viene a volte risolto riavviando il sistema Microsoft teams rooms.
- La perdita di audio locale durante la connessione di un PC alla console tramite l'acquisizione tramite cavo è nota. In questi casi, il riavvio del PC può risolvere il problema di riproduzione audio locale.
    
