---
title: Risolvere i problemi relativi alla distribuzione di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359332"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Risolvere i problemi relativi alla distribuzione di Cloud Connector

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.
  
In questo argomento vengono descritte le soluzioni ai problemi comuni relativi alle distribuzioni di Cloud Connector Edition. Se si verificano problemi con le chiamate da e verso la rete PSTN (Public Switched Telephone Network), è possibile analizzare seguendo le soluzioni descritte in questo argomento.
  
Cloud Connector fornisce meccanismi predefiniti per la risoluzione automatica di alcuni problemi. Un processo di rilevamento automatico consente di cercare potenziali problemi con gli appliance Cloud Connector e, se possibile, di intervenire in modo correttivo per risolvere tali problemi senza l'intervento dell'amministratore. Il processo di rilevamento funziona come segue:
  
- **Sequenza di rilevamento:** Il servizio di gestione del connettore cloud esegue un processo ogni 60 secondi per rilevare se un'applicazione è in stato di in esecuzione. In Cloud Connector versione 2.0 e successive, il processo di rilevamento utilizza l'opzione Corpnet di Skype for Business per effettuare connessioni PowerShell ai computer Cloud Connector; per le versioni precedenti alla 2.0, il processo di rilevamento utilizza l'opzione di gestione Cloud Connector.
    
    > [!NOTE]
    > Per il ripristino automatico, è necessario che ci sia connettività di rete tra l'host e le macchine virtuali tramite il commutatore di rete host. Assicurati di controllare la connettività di rete per assicurarti che il rilevamento e il ripristino automatici possano avere esito positivo. 
  
- **Monitoraggio:** I servizi seguenti vengono monitorati in Cloud Connector versione 2.0 e successive:
    
  - Le macchine virtuali non sono connesse ai commutatori virtuali Aziendali o Internet del connettore cloud
    
  - Le macchine virtuali sono in stato salvato o arrestato
    
  - Servizi del server di gestione centrale: REPLICA, MASTER
    
  - Servizi Mediation Server: REPLICA, RTCSRV e MEDSVC
    
  - Servizi server perimetrale: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Le regole del firewall in ingresso sono disabilitate per CS RTCSRV nel server perimetrale, CS RTCMEDSRV nel Mediation Server
    
    In Cloud Connector versione 1.4.2 vengono monitorati solo i servizi seguenti:
    
  - Servizi Mediation Server: RTCSRV e MEDSVC
    
  - Servizio Server perimetrale: RTCSRV
    
- **Processo di ripristino:** Se i servizi monitorati sono in servizio, un'applicazione viene contrassegnata e i servizi vengono arrestati e contrassegnati manualmente fino a quando non è possibile risolvere tutti i problemi. In questo modo si impedirà il routing delle chiamate a un dispositivo che potrebbe causare errori di chiamata.
    
    Il servizio di gestione del connettore cloud ritenterà il ripristino automatico come indicato di seguito
    
  - L'intervallo tra tentativi iniziali è ogni dieci secondi con un intervallo massimo di un'ora.
    
  - Per i primi tre tentativi di ripristino, l'intervallo è di 10 secondi. A partire dal quarto tentativo, l'intervallo aumenta di due volte rispetto all'intervallo precedente. Ad esempio, il quarto tentativo verrà eseguito in 20 secondi, il quinto in 40 secondi e così via. 
    
  - Quando viene raggiunto l'intervallo massimo di un'ora, i tentativi continueranno una volta all'ora.
    
  - Quando il ripristino ha esito positivo, il numero di intervalli e tentativi viene impostato sui valori iniziali.
    
  - Se il servizio di gestione viene riavviato, i conteggi degli intervalli e dei tentativi vengono reimpostati sui valori iniziali.
    
## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito sono riportate le soluzioni ai problemi più comuni:
  
- **Problema: la distribuzione non riesce o smette di rispondere durante l'esecuzione degli script di distribuzione. Dopo l'accesso a ogni macchina virtuale, l'indirizzo IP non è presente o non è corretto per la scheda nic gestione/interna/esterna.**
    
    **Soluzione:** Questo problema non può essere risolto automaticamente. Le schede di interfaccia di rete non possono essere aggiunte alle macchine virtuali mentre sono in esecuzione. Arrestare e rimuovere queste macchine virtuali nella console di gestione di Hyper-v, quindi eseguire i cmdlet seguenti:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: dopo l'installazione del server Active Directory e della foresta, il server CMS e/o il Mediation Server non sono stati uniti correttamente al dominio.**
    
    **Soluzione:** Per risolvere questo problema, eseguire la procedura seguente:
    
  - Accedere al server Active Directory e verificare che il dominio sia stato creato correttamente.
    
  - Accedere al CMS/Mediation Server e verificare che nella scheda NIC della rete corpnet sia assegnato un indirizzo IP valido e che ip statico e DNS validi siano configurati come indirizzo IP del server Active Directory.
    
  - Accedere a CMS/Mediation Server e aprire un prompt dei comandi. Assicurarsi di poter eseguire il ping dell'FQDN e dell'indirizzo IP del server Active Directory. Se non è possibile, potrebbe verificarsi un conflitto di indirizzi IP. Provare ad assegnare un nuovo INDIRIZZO IP per Active Directory e aggiornare il DNS nel server CMS/Mediation Server di conseguenza.
    
- **Problema: viene visualizzato il messaggio di errore "Remove-VMSwitch : Failed while removing virtual Ethernet switch. Il commutatore virtuale 'Cloud Connector Management Switch' non può essere eliminato perché viene utilizzato da macchine virtuali o assegnato a pool figlio."**
    
    **Soluzione:** Il "Cloud Connector Management Switch" non è stato eliminato dopo la distribuzione. Se si verifica questo errore, passare alla console di gestione di Hyper-v e verificare che non ci sia ancora una macchina virtuale ancora connessa. Se sono ancora connesse macchine virtuali, disconnetterle ed eliminare il commutatore di gestione. Se l'opzione di gestione non può ancora essere eliminata, riavviare il server host e riprovare.
    
- **Problema: viene visualizzato il messaggio di errore seguente, "Avvio del servizio RTCMRAUTH non riuscito. Verificare che il servizio non sia disabilitato."**
    
    > [!NOTE]
    > Questo problema si applica solo alle versioni di Cloud Connector precedenti alla 1.4.2. 
  
    L'errore di avvio potrebbe anche essere dovuto al failover di questo Front End Server (utilizzando il failover del computer). In questo caso, richiamare il fail back (utilizzando il fail back del computer).
    
    **Soluzione:** Questo problema si verifica in un server perimetrale quando il certificato CA radice o intermedio non è considerato attendibile dal server perimetrale. Anche se il certificato esterno può essere importato ma la catena di certificati è interrotta. In questa condizione, il servizio RTCMRAUTH e/o RTCSRV non può essere avviato.
    
    Importare manualmente il certificato DELLA CA radice e tutti i certificati della CA intermedia del certificato esterno nel server perimetrale, quindi riavviare il server perimetrale. Dopo aver visualizzato i servizi RTCMRAUTH e RTCSRV avviati nel server perimetrale, tornare al server host, avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per passare alla nuova distribuzione:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: il server host è stato riavviato quando sono stati applicati gli aggiornamenti di Windows e le chiamate effettuate dal server hanno esito negativo.**
    
    **Soluzione:** Se è stato distribuito un ambiente a disponibilità elevata, Microsoft fornisce un cmdlet che consente di spostare un computer host (istanza di distribuzione) all'interno o all'esterno della topologia corrente quando si archivia e si installa Windows Update manualmente. A tale scopo, eseguire la procedura seguente:
    
1. Nel server host avviare una console di PowerShell come amministratore, quindi eseguire:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Verificare la disponibilità di aggiornamenti e installare gli eventuali aggiornamenti disponibili.
    
3. Nella console di PowerShell eseguire il cmdlet seguente:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando viene effettuata una chiamata da un client Skype for Business utilizzando un numero PSTN, la chiamata non può essere inoltrata a una conferenza invitando un altro numero PSTN.**
    
    **Soluzione:** Per risolvere questo problema, vedere Configurare le impostazioni di Mediation Server ibrido [online.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)
    
- **Problema: viene visualizzato un messaggio di avviso relativo a Windows Update durante l'installazione del server Active Directory: "L'aggiornamento automatico di Windows non è abilitato. Per assicurarti che il ruolo o la funzionalità appena installata sia aggiornata automaticamente, attiva Windows Update."**
    
    **Soluzione:** Avviare una sessione di Tenant Remote PowerShell con le credenziali di amministratore tenant di Skype for Business, quindi eseguire il cmdlet seguente per controllare la configurazione _EnableAutoUpdate_ del sito:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se  _EnableAutoUpdate_ è impostato su **True,** è possibile ignorare questo messaggio di avviso perché il servizio CCEManagement gestirà il download e l'installazione degli aggiornamenti di Windows sia per le macchine virtuali che per il server host. Se _EnableAutoUpdate è_ impostato su **False,** eseguire il cmdlet seguente per impostarlo su **True.**
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    In alternativa, è possibile controllare e installare manualmente gli aggiornamenti. Vedere la sezione successiva.
    
- **Problema: viene visualizzato un messaggio di errore: Impossibile registrare l'applicazione perché l'input/configurazione corrente o o è in conflitto \<SiteName\> \<ApplianceName\> con le appliance \<Mediation Server FQDN\> \<Mediation Server IP Address\> esistenti. Rimuovere l'applicazione dei conflitti o aggiornare le informazioni di input/configurazione e quindi registrare di nuovo. ' when run Register-CcAppliance to register current appliance to online.**
    
    **Soluzione:** I valori per \<ApplianceName\> il parametro e devono essere \<Mediation Server FQDN\> \<Mediation Server IP Address\> univoci e utilizzati solo per la registrazione di un dispositivo. Per impostazione predefinita, \<ApplianceName\> proviene dal nome host. \<Mediation Server FQDN\> e \<Mediation Server IP Address\> definiti nel file ini di configurazione.
    
    Ad esempio, utilizzando (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) per eseguire la registrazione in SiteName=MySite, ma se è presente un'applicazione registrata (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), si avrà il conflitto.
    
    Prima di tutto, controllare il CloudConnector.ini file nella sezione della directory ApplianceRoot. Si otterrà \<SiteName\> e i valori nel \<Mediation Server FQDN\> \<Mediation Server IP Address\> file. \<ApplianceName\> è il nome del server host.
    
    In secondo momento, avvia Remote PowerShell del tenant usando le credenziali di amministratore tenant di Skype for Business, quindi esegui il cmdlet seguente per controllare gli appliance registrati.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Dopo aver identificato eventuali conflitti, è possibile aggiornare il file CloudConnector.ini con le informazioni corrispondenti all'appliance registrata oppure annullare la registrazione dell'applicazione esistente per risolvere i conflitti.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: il cmdlet Get-CcRunningVersion restituisce un valore vuoto se nell'host è in esecuzione un'applicazione distribuita.**
    
  **Soluzione:** Ciò può verificarsi quando si esegue l'aggiornamento da 1.3.4 o 1.3.8 a 1.4.1. Dopo aver installato la versione 1.4.1 con il file MSI, è necessario eseguirlo prima di `Register-CcAppliance` eseguire qualsiasi altro cmdlet. `Register-CcAppliance` eseguirà la migrazione module.ini file da %UserProfile%\CloudConnector a %ProgramData%\CloudConnector. Se non lo si è fatto, verrà creato un nuovo module.ini nella cartella %ProgramData%\CloudConnector e verranno sostituite le informazioni sulla versione di esecuzione/backup per 1.3.4 o 1.3.8.
    
  Confrontare module.ini file nella cartella %UserProfile%\CloudConnector e %ProgramData%\CloudConnector. In caso di differenze, eliminare il file module.ini in %ProgramData%\CloudConnector ed eseguire di nuovo  `Register-CcAppliance` . È inoltre possibile modificare manualmente il file con la versione di esecuzione e di backup corretta.
    
- **Problema: dopo aver eseguito il cmdlet Switch-CcVersion per passare a una versione precedente diversa dalla versione corrente dello script, non è disponibile alcun supporto di disponibilità elevata per questa versione precedente.**
    
    **Soluzione:** Ad esempio, è stato eseguito l'aggiornamento da 1.4.1 a 1.4.2. La versione corrente dello script, che può essere determinata eseguendo , e la versione in esecuzione, che può essere determinata dall'esecuzione, sono `Get-CcVersion`  `Get-CcRunningVersion` entrambe 1.4.2. Al momento, se si esegue per tornare a 1.4.1 la versione in esecuzione, non sarà disponibile alcun supporto per la disponibilità elevata per `Switch-CcVersion` questa versione precedente.
    
    Per ottenere il supporto completo per la disponibilità elevata, tornare alla versione 1.4.2, in modo che la versione in esecuzione e la versione dello script siano le stesse. Se si verificano problemi con la distribuzione 1.4.2, disinstallarla e reinstallarla il prima possibile.
    
- **Problema: i certificati dell'autorità di certificazione o i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono prossimi alla scadenza o sono compromessi.**
    
    **Soluzione:** I certificati dell'autorità di certificazione di Skype for Business sono validi per cinque anni. I certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono validi per due anni.
    
    > [!NOTE]
    > In Cloud Connector versione 2.0 e successive, il cmdlet Renew-CcServerCertificate è stato modificato in Update-CcServerCertificate e il cmdlet Renew-CcCACertificate è stato modificato in Update-CcCACertificate. 
  
    Se i certificati interni emessi per l'archivio di gestione centrale, il Mediation Server e il server perimetrale sono prossimi alla scadenza o sono compromessi, eseguire il cmdlet Renew-CcServerCertificate o Update-CcServerCertificate per rinnovare i certificati.
    
    Se i certificati dell'autorità di certificazione sono prossimi alla scadenza, eseguire il cmdlet Renew-CcCACertificate o Update-CcCACertificate per rinnovare i certificati.
    
    **Se i certificati dell'autorità** di certificazione sono compromessi e nel sito è presente un solo dispositivo, eseguire la procedura seguente:
    
1. Eseguire il cmdlet Enter-CcUpdate per svuotare i servizi e impostare l'applicazione in modalità manutenzione.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:
    
    Per le versioni di Cloud Connector precedenti alla 2.0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Oppure per Cloud Connector versione 2.0 e successive:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se tra il gateway e il Mediation Server viene utilizzato TLS, eseguire il cmdlet Export-CcRootCertificate dall'appliance e quindi installare il certificato esportato nei gateway PSTN. Potrebbe anche essere necessario emettere nuovamente il certificato nel gateway.

   ```powershell
   Export-CcRootCertificate
   ```

4. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.

   ```powershell
   Exit-CcUpdate
   ```


    **Se i certificati dell'autorità** di certificazione sono compromessi e nel sito sono presenti più appliance, eseguire i passaggi sequenziali seguenti in ogni applicazione del sito.
    
    Microsoft consiglia di eseguire questi passaggi durante i periodi di utilizzo non di punta.
    
1. Nel primo appliance, eseguire il cmdlet Remove-CcCertificationAuthorityFile per pulire i file di backup della CA nella \<SiteRoot\> directory.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Eseguire il cmdlet Enter-CcUpdate per svuotare i servizi e impostare ogni applicazione in modalità manutenzione.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Nel primo appliance, eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:
    
     Per le versioni di Cloud Connector precedenti alla 2.0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Oppure per Cloud Connector versione 2.0 e successive:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Nel primo appliance, eseguire il cmdlet seguente per eseguire il backup dei file della CA nella \<SiteRoot\> cartella.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. In tutti gli altri dispositivi nello stesso sito, eseguire i comandi seguenti per utilizzare i file di backup della CA, in modo che tutti gli appliance utilizzino lo stesso certificato radice e quindi richiedere nuovi certificati. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se tra il gateway e il Mediation Server viene utilizzato TLS, eseguire il cmdlet Export-CcRootCertificate da qualsiasi appliance del sito e quindi installare il certificato esportato nei gateway PSTN. Potrebbe anche essere necessario emettere nuovamente il certificato nel gateway.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: viene visualizzato il seguente messaggio di errore nel registro del servizio di gestione del connettore cloud, "C:\Programmi\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\> . Creare un nuovo oggetto credenziali, verificando di aver utilizzato il nome utente e la password corretti. ---\>**
    
    **Soluzione:** Le credenziali di amministratore del tenant globale di Microsoft 365 o Office 365 sono state modificate dopo la registrazione dell'applicazione Cloud Connector. Per aggiornare le credenziali archiviate localmente nell'applicazione Cloud Connector, eseguire le operazioni seguenti da Administrator PowerShell nell'applicazione host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: dopo aver modificato la password per l'account del server host utilizzato per la distribuzione, viene visualizzato il messaggio di errore seguente: "ConvertTo-SecureString : Chiave non valida per l'utilizzo nello stato specificato." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o durante l'esecuzione del cmdlet Get-CcCredential.**
    
    **Soluzione:** Tutte le credenziali del connettore cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml". Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.
    
    **Se si esegue Cloud Connector versione 1.4.2,** rigenerare tutte le password del connettore cloud eseguendo la procedura seguente:
    
  1. Riavviare il server host.
    
  2. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".
    
  3. Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere nuovamente le password seguendo la descrizione. Immettere le stesse password immesse prima per la distribuzione di Cloud Connector.
    
     **Se si esegue Cloud Connector versione 2.0 o successiva,** rigenerare tutte le password di Cloud Connector eseguendo la procedura seguente:
    
  4. Riavviare il server host.
    
  5. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" .
    
  6. Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere nuovamente le password seguendo la descrizione. 
    
     Se il file della password memorizzata nella cache è stato generato con Cloud Connector versione 1.4.2, utilizzare la password VMAdmin per la password di CceService quando richiesto. Immettere la stessa password immessa prima per la distribuzione di Cloud Connector per tutti gli altri account.
    
     Se il file delle password memorizzate nella cache è stato generato con Cloud Connector versione 1.4.2 e le password DomainAdmin e VMAdmin sono diverse, è necessario eseguire la procedura seguente:
    
  7. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
  8. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
  9. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin utilizzata in precedenza.
    
     Se il file delle password memorizzate nella cache è stato generato con Cloud Connector versione 2.0 o successiva, per impostazione predefinita, VmAdmin e DomainAdmin usano la stessa password di CceService. Se sono state modificate le password DomainAdmin e VMAdmin, è necessario eseguire la procedura seguente:
    
  10. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
       1. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService
    
       2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin utilizzata in precedenza.
    
  11. Eseguire Set-CcCredential -AccountType VmAdmin come segue:
    
       1. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService
    
       2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password vmadmin utilizzata in precedenza. 
    
- **Problema: con Cloud Connector versione 2.1 e successive, quando si esegue Register-CcAppliance o altri cmdlet nell'appliance, viene visualizzato un messaggio di errore, ad esempio: "Per Each-Object : Impossibile trovare la proprietà "Common" su questo oggetto. Verificare che la proprietà esista. In C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Soluzione:** Cloud Connector 2.1 e versioni successive richiede .NET Framework 4.6.1 o versione successiva. Aggiornare .NET Framework nell'applicazione alla versione 4.6.1 o successiva ed eseguire di nuovo i cmdlet.

- **Problema: con Cloud Connector Edition 2.1, quando si esegue Install-CcAppliance, viene visualizzato un messaggio di errore, ad esempio: "Impossibile installare una nuova istanza con errore: Impossibile impostare "State" perché solo le stringhe possono essere utilizzate come valori per impostare le proprietà XmlNode"**

   **Soluzione:** In Cloudconnector.ini, nella sezione [Comune], aggiungi la configurazione "State" come segue: CountryCode=US State=WA City=Redmond

   Non è obbligatorio che la riga "State" abbia valore, ma la riga "State" non può essere rimossa dal file Cloudconnector.ini.

- **Problema: viene visualizzato il seguente messaggio di errore "Dismount-WindowsImage : Dismount-WindowsImage non riuscito. Codice di errore = 0xc1550115" durante l'installazione o l'aggiornamento di Cloud Connector Edition.**
    
    **Soluzione:** Avviare una console di PowerShell come amministratore, eseguire "DISM -Cleanup-Wim'". In questo modo verranno ripulite tutte le immagini con problemi. Eseguire Install-CcAppliance di nuovo o attendere l'aggiornamento automatico dei bit.
    
- **Problema: la distribuzione del primo dispositivo Cloud Connector in un ambiente ha esito negativo**
    
    **Soluzione:** I passaggi da eseguire dipendono dal motivo per cui la distribuzione non è riuscita:
    
  - Se si verifica un errore nel primo dispositivo Cloud Connector e non è possibile determinare il motivo dell'errore, è necessario installare di nuovo l'appliance fino al completamento della distribuzione e quindi installare le altre appliance.
    
  - Se il primo dispositivo Cloud Connector ha esito negativo con un problema minore, ad esempio un problema di certificato esterno, potrebbe essere possibile risolvere il problema senza installare di nuovo l'appliance. È quindi possibile utilizzare PowerShell remoto del tenant per contrassegnare la distribuzione come completata come segue. È inoltre possibile utilizzare i passaggi seguenti se la prima distribuzione ha avuto esito positivo, ma, per qualche motivo, Cloud Connector non riesce a segnalare la distribuzione come completata.
    
  - Per ottenere l'identità (GUID) del primo dispositivo Cloud Connector, eseguire il cmdlet Get-CsHybridPSTNAppliance cloud.
    
  - Per contrassegnare l'applicazione come distribuita correttamente, eseguire il Set-CsCceApplianceDeploymentStatus nel modo seguente:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: è necessario verificare e installare manualmente gli aggiornamenti di Windows nel server host o nelle macchine virtuali.**
    
   **Soluzione:** È consigliabile sfruttare gli aggiornamenti automatici del sistema operativo forniti da Skype for Business Cloud Connector Edition. Dopo la registrazione di un'applicazione per la gestione online e l'aggiornamento automatico del sistema operativo, il server host e le macchine virtuali controllano e installano automaticamente gli aggiornamenti di Windows in base alle impostazioni dell'intervallo di tempo per l'aggiornamento del sistema operativo.
    
   Se devi verificare e installare manualmente gli aggiornamenti di Windows, segui i passaggi di questa sezione applicabili al tipo di distribuzione. È consigliabile pianificare l'aggiornamento contemporaneamente del server host e delle macchine virtuali in esecuzione su di esso per ridurre al minimo il tempo di inerte necessario per gli aggiornamenti.
    
   Se si preferisce, è possibile utilizzare un server Windows Server Update Services (WSUS) per fornire aggiornamenti ai server Cloud Connector. Assicurati di configurare Windows Update in modo che **non si installi** automaticamente.
    
   Per informazioni su come aggiornare manualmente la distribuzione di Cloud Connector, vedere la sezione seguente.
    
- **Problema: quando Cloud Connector esegue l'aggiornamento a una nuova build, i cmdlet di Cloud Connector non vengono aggiornati.** Ciò accade a volte se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.
    
  **Soluzione:** Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:
    
   - Chiudere PowerShell nell'applicazione Cloud Connector e quindi riaprire PowerShell.
    
     - Oppure, è possibile eseguire Import-Module CloudConnector -Force. 
 
-   **Problema: "Il termine "Stop-CsWindowsService" non è riconosciuto come nome di un cmdlet, di una funzione, di un file di script o di un programma funzionante." quando si tenta di eseguire Enter-CcUpdate cmdlet.**

    **Soluzione:** Elimina il file $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea questo file come cache di cmdlet dai moduli trovati in modo che non sia necessario analizzare di nuovo tutti i moduli ogni volta in quanto ciò renderebbe le cose molto lente. Molto probabilmente, c'è stato un danneggiamento dei file che ha fornito risultati fuorvianti a PowerShell durante la lettura dalla cache.

-   **Problema: "Import-Module CloudConnector" genera l'errore "Import-Module: Il modulo specificato "CloudConnector" non è stato caricato perché non è stato trovato alcun file di modulo valido in alcuna directory del modulo"**

    **Risoluzione:**
    - Verificare che il modulo CloudConnector esista effettivamente in c:\Programmi\WindowsPowerShell\Modules
    
    - Dopo aver convalidato l'esistenza del modulo CloudConnector in questo percorso, è possibile modificare la variabile di ambiente PSModulePath in cui è archiviato il percorso dei percorsi dei moduli:
    
     a. Modifica temporanea: avviare Powershell come amministratore ed eseguire il comando seguente: $env:PSModulePath = $env:PSModulePath + "; C:\Programmi\WindowsPowerShell\Modules\"
        
     b. Per una modifica permanente, avviare PowerShell come amministratore ed eseguire i comandi seguenti, uno alla volta: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Programmi\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Installare manualmente gli aggiornamenti di Windows

Se non vuoi usare gli aggiornamenti automatici nel tuo ambiente, segui questi passaggi per verificare manualmente la disponibilità e applicare gli aggiornamenti di Windows. La verifica e l'installazione degli aggiornamenti di Windows potrebbero richiedere il riavvio del server. Quando un server host viene riavviato, gli utenti non potranno utilizzare Cloud Connector per effettuare o ricevere chiamate. Puoi controllare e installare manualmente gli aggiornamenti per controllare quando gli aggiornamenti vengono e quindi riavviare i computer in base alle esigenze durante i periodi in cui scegli di evitare interruzioni dei servizi.
  
Per verificare manualmente la disponibilità di aggiornamenti, connettersi a ogni server host e aprire il **Pannello di controllo.** Selezionare **Sistema e sicurezza di Windows \> Update** e quindi gestire gli aggiornamenti e i riavvii del server in base alle esigenze dell'ambiente.
  
- Se nel sito è presente un solo dispositivo, connettersi a ogni macchina virtuale e aprire il **Pannello di controllo.** Selezionare **Sistema e sicurezza di Windows \> Update** e quindi configurare gli aggiornamenti e i riavvii del server in base alle esigenze.
    
- Se nel sito sono presenti più applicazioni, gli utenti non potranno accedere all'istanza aggiornata e riavviata durante gli aggiornamenti. Gli utenti si connetteranno ad altre istanze della distribuzione fino a quando tutte le macchine virtuali e tutti i servizi Skype for Business non verranno avviati nelle macchine virtuali dopo il completamento degli aggiornamenti. Per evitare potenziali interruzioni del servizio, è possibile rimuovere l'istanza dall'ha mentre si applicano gli aggiornamenti e quindi ripristinarla al termine. A questo scopo:
    
1. In ogni server host, aprire una console di PowerShell come amministratore.
    
2. Rimuovere l'istanza dall'ha con il cmdlet seguente:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Seguire i passaggi per una singola istanza per applicare manualmente gli aggiornamenti e riavviare la macchina virtuale.
    
4. Impostare nuovamente l'istanza su HA con il cmdlet seguente:
    
   ```powershell
   Exit-CcUpdate
   ```

Per le distribuzioni multisnode, seguire la procedura per un singolo sito per ogni sito della distribuzione, applicando gli aggiornamenti a un sito alla volta.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Suggerimenti per l'installazione di software antivirus nel computer host cloud Connector

Se è necessario installare software antivirus nel computer host Cloud Connector, è necessario aggiungere le esclusioni seguenti:
  
- Directory appliance locale in ogni computer.
    
- Directory siti remota in ogni computer.
    
- La directory siti locale nel computer ospita la cartella radice del sito condiviso.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Il processo Microsoft.Rtc.CCE.ManagementService.exe.
