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
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094824"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Risolvere i problemi relativi alla distribuzione di Cloud Connector

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)
 
Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.
  
In questo argomento vengono descritte le soluzioni ai problemi comuni relativi alle distribuzioni di Cloud Connector Edition. Se si verificano problemi con le chiamate da e verso la rete PSTN (Public Switched Telephone Network), è possibile analizzare seguendo le soluzioni descritte in questo argomento.
  
Cloud Connector fornisce meccanismi incorporati per la risoluzione automatica di alcuni problemi. Un processo di rilevamento automatico cerca potenziali problemi con le appliance cloud Connector e, se possibile, adotta azioni correttive per risolvere tali problemi senza l'intervento dell'amministratore. Il processo di rilevamento funziona come segue:
  
- **Sequenza di rilevamento:** Il servizio di gestione dei connettori cloud esegue un processo ogni 60 secondi per rilevare se un'appliance è in stato di inossamento. In Cloud Connector versione 2.0 e successive, il processo di rilevamento usa l'opzione Skype for Business Corpnet per effettuare connessioni PowerShell ai computer Cloud Connector; per le versioni precedenti alla 2.0, il processo di rilevamento utilizza l'opzione di gestione Cloud Connector.
    
    > [!NOTE]
    > Per il ripristino automatico, è necessario che sia presente una connettività di rete tra l'host e le macchine virtuali tramite il commutatore di rete host. Verificare la connettività di rete per assicurarsi che il rilevamento e il ripristino automatici possano avere esito positivo. 
  
- **Monitoraggio:** I servizi seguenti vengono monitorati in Cloud Connector versione 2.0 e successive:
    
  - Le macchine virtuali non sono connesse ai commutatori virtuali Corporate o Internet del connettore cloud
    
  - Le macchine virtuali sono in stato salvato o arrestato
    
  - Servizi del server di gestione centrale: REPLICA, MASTER
    
  - Servizi Mediation Server: REPLICA, RTCSRV e MEDSVC
    
  - Servizi server perimetrali: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Le regole del firewall in ingresso sono disabilitate per CS RTCSRV nel server perimetrale, CS RTCMEDSRV nel Mediation Server
    
    In Cloud Connector versione 1.4.2 vengono monitorati solo i servizi seguenti:
    
  - Servizi Mediation Server: RTCSRV e MEDSVC
    
  - Servizio Server perimetrale: RTCSRV
    
- **Processo di ripristino:** Se i servizi monitorati non sono disponibili, un'appliance viene contrassegnata e i servizi vengono arrestati e contrassegnati come manuali fino a quando non è possibile risolvere tutti i problemi. In questo modo si impedirà il routing delle chiamate a un'appliance che potrebbe causare errori di chiamata.
    
    Il servizio di gestione del connettore cloud ritenterà il ripristino automatico come indicato di seguito
    
  - L'intervallo tra tentativi iniziale è ogni dieci secondi con un intervallo massimo di un'ora.
    
  - Per i primi tre tentativi di ripristino, l'intervallo è di 10 secondi. A partire dal quarto tentativo, l'intervallo aumenta di due volte l'intervallo precedente. Ad esempio, il quarto tentativo si verificherà in 20 secondi, il quinto in 40 secondi e così via. 
    
  - Quando viene raggiunto l'intervallo massimo di un'ora, i tentativi continueranno una volta all'ora.
    
  - Quando il ripristino ha esito positivo, i conteggi degli intervalli e dei tentativi vengono impostati sui valori iniziali.
    
  - Se il servizio di gestione viene riavviato, l'intervallo e i tentativi vengono reimpostati sui valori iniziali.
    
## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito sono riportate le soluzioni ai problemi più comuni:
  
- **Problema: la distribuzione non riesce o smette di rispondere durante l'esecuzione degli script di distribuzione. Dopo l'accesso a ogni macchina virtuale, l'indirizzo IP è mancante o non corretto per la scheda di interfaccia di rete gestione/interna/esterna.**
    
    **Risoluzione:** Questo problema non può essere risolto automaticamente. Le schede di interfaccia di rete non possono essere aggiunte alle macchine virtuali mentre sono in esecuzione. Arrestare e rimuovere queste macchine virtuali nella gestione di hyper-v, quindi eseguire i cmdlet seguenti:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: dopo l'installazione del server Active Directory e della foresta, il server CMS e/o il Mediation Server non sono stati uniti correttamente al dominio.**
    
    **Risoluzione:** Per risolvere questo problema, eseguire la procedura seguente:
    
  - Accedere al server Active Directory e verificare che il dominio sia stato creato correttamente.
    
  - Accedere a CMS/Mediation Server e verificare che nella scheda NIC corpnet sia assegnato un indirizzo IP valido e che l'IP statico e il DNS validi siano configurati come indirizzo IP del server AD.
    
  - Accedere a CMS/Mediation Server e aprire un prompt dei comandi. Assicurarsi di poter eseguire il ping dell'FQDN e dell'indirizzo IP del server Active Directory. Se non è possibile, potrebbe verificarsi un conflitto di indirizzi IP. Provare ad assegnare un nuovo INDIRIZZO IP per Active Directory e aggiornare il DNS nel server CMS/Mediation Server di conseguenza.
    
- **Problema: viene visualizzato il seguente messaggio di errore, "Remove-VMSwitch : Operazione non riuscita durante la rimozione del commutatore Ethernet virtuale. Il commutatore virtuale 'Cloud Connector Management Switch' non può essere eliminato perché viene utilizzato da macchine virtuali in esecuzione o assegnato a pool figlio."**
    
    **Risoluzione:** Il "Cloud Connector Management Switch" non è stato eliminato dopo la distribuzione. Se si verifica questo errore, passare alla console di gestione di Hyper-v e verificare che non vi sia ancora una macchina virtuale ancora connessa. Se sono ancora connesse macchine virtuali, disconnetterle ed eliminare il commutatore di gestione. Se non è ancora possibile eliminare l'opzione di gestione, riavviare il server host e riprovare.
    
- **Problema: viene visualizzato il messaggio di errore seguente, "Avvio del servizio RTCMRAUTH non riuscito. Verificare che il servizio non sia disabilitato."**
    
    > [!NOTE]
    > Questo problema si applica solo alle versioni di Cloud Connector precedenti alla 1.4.2. 
  
    L'errore di avvio potrebbe anche essere dovuto al fatto che in precedenza è stato eseguito il failover del server Front End (utilizzando il failover del computer). In questo caso, richiamare il fail back (utilizzando il fail back del computer).
    
    **Risoluzione:** Questo problema si verifica in un server perimetrale quando il certificato CA radice o il certificato CA intermedio non è considerato attendibile dal server perimetrale. Anche se il certificato esterno può essere importato ma la catena di certificati è interrotta. In questa condizione, non è possibile avviare il servizio RTCMRAUTH e/o RTCSRV.
    
    Importare manualmente il certificato della CA radice e tutti i certificati CA intermedi del certificato esterno nel server perimetrale e quindi riavviare il server perimetrale. Dopo aver visualizzato i servizi RTCMRAUTH e RTCSRV avviati nel server perimetrale, tornare al server host, avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per passare alla nuova distribuzione:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: il server host è stato riavviato quando sono stati applicati gli aggiornamenti di Windows e le chiamate effettuate dal server hanno esito negativo.**
    
    **Risoluzione:** Se è stato distribuito un ambiente a disponibilità elevata, Microsoft fornisce un cmdlet che consente di spostare un computer host (istanza di distribuzione) all'interno o all'esterno della topologia corrente quando si archivia e si installa windows update manualmente. A tale scopo, eseguire la procedura seguente:
    
1. Nel server host, avviare una console di PowerShell come amministratore, quindi eseguire:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Verificare la disponibilità di aggiornamenti e installare gli eventuali aggiornamenti disponibili.
    
3. Nella console di PowerShell eseguire il cmdlet seguente:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando viene effettuata una chiamata da un client Skype for Business utilizzando un numero PSTN, non è possibile inoltrare la chiamata a una conferenza invitando un altro numero PSTN.**
    
    **Risoluzione:** Per risolvere questo problema, vedere [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: viene visualizzato un messaggio di avviso relativo a Windows Update durante l'installazione del server Active Directory: "L'aggiornamento automatico di Windows non è abilitato. Per assicurarti che il ruolo o la funzionalità appena installata sia aggiornata automaticamente, attiva Windows Update."**
    
    **Risoluzione:** Avviare una sessione di PowerShell remoto tenant utilizzando le credenziali di amministratore tenant di Skype for Business, quindi eseguire il cmdlet seguente per controllare la configurazione _EnableAutoUpdate_ del sito:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se  _EnableAutoUpdate_ è impostato su **True,** è possibile ignorare questo messaggio di avviso perché il servizio CCEManagement gestirà il download e l'installazione degli aggiornamenti di Windows sia per le macchine virtuali che per il server host. Se _EnableAutoUpdate_ è impostato su **False,** eseguire il cmdlet seguente per impostarlo su **True.**
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    In alternativa, è possibile controllare e installare manualmente gli aggiornamenti. Vedere la sezione successiva.
    
- **Problema: viene visualizzato un messaggio di errore: Impossibile registrare l'appliance perché l'input/configurazione corrente o \<SiteName\> o è in conflitto con le appliance \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> esistenti. Rimuovi l'appliance in conflitto o aggiorna le informazioni di input/configurazione e quindi registra di nuovo. ' quando viene eseguito Register-CcAppliance per registrare l'appliance corrente online.**
    
    **Risoluzione:** I valori per \<ApplianceName\> e \<Mediation Server FQDN\> devono essere \<Mediation Server IP Address\> univoci e utilizzati solo per la registrazione di un dispositivo. Per impostazione predefinita, \<ApplianceName\> proviene dal nome host. \<Mediation Server FQDN\> e \<Mediation Server IP Address\> definito nel file ini di configurazione.
    
    Ad esempio, utilizzando (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) per eseguire la registrazione in SiteName=MySite, ma se è presente un'appliance registrata (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), si avrà il conflitto.
    
    Prima di tutto, controllare il file CloudConnector.ini nella sezione Directory ApplianceRoot. Si otterrà \<SiteName\> e i valori nel \<Mediation Server FQDN\> \<Mediation Server IP Address\> file. \<ApplianceName\> è il nome del server host.
    
    In secondo momento, avvia Remote PowerShell tenant usando le credenziali di amministratore tenant di Skype for Business, quindi esegui il cmdlet seguente per controllare gli appliance registrati.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Dopo aver identificato eventuali conflitti, è possibile aggiornare il file CloudConnector.ini con le informazioni corrispondenti all'appliance registrata oppure annullare la registrazione dell'appliance esistente per risolvere i conflitti.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: il cmdlet Get-CcRunningVersion restituisce un valore vuoto se nell'host è in esecuzione un'appliance distribuita.**
    
  **Risoluzione:** Ciò può verificarsi quando si esegue l'aggiornamento da 1.3.4 o 1.3.8 a 1.4.1. Dopo aver installato la versione 1.4.1 con il file msi, è necessario eseguire `Register-CcAppliance` prima di eseguire qualsiasi altro cmdlet. `Register-CcAppliance` eseguirà la migrazione module.ini file da %UserProfile%\CloudConnector a %ProgramData%\CloudConnector. Se si è perso, verrà creato un nuovo module.ini nella cartella %ProgramData%\CloudConnector e verranno sostituite le informazioni sulla versione di esecuzione/backup per 1.3.4 o 1.3.8.
    
  Confronta module.ini file nella cartella %UserProfile%\CloudConnector e %ProgramData%\CloudConnector. In caso di differenze, eliminare il file module.ini in %ProgramData%\CloudConnector ed eseguire di nuovo  `Register-CcAppliance` . È inoltre possibile modificare manualmente il file con la versione di esecuzione e di backup corretta.
    
- **Problema: dopo aver eseguito il cmdlet Switch-CcVersion per passare a una versione precedente diversa dalla versione corrente dello script, non è disponibile alcun supporto disponibilità elevata per questa versione precedente.**
    
    **Risoluzione:** Ad esempio, è stato eseguito l'aggiornamento da 1.4.1 a 1.4.2. La versione corrente dello script, che può essere determinata dall'esecuzione, e la versione in esecuzione, che può essere determinata dall'esecuzione, sono `Get-CcVersion`  `Get-CcRunningVersion` entrambe 1.4.2. Al momento, se si esegue per tornare alla versione in esecuzione alla versione 1.4.1, non sarà disponibile alcun supporto per la `Switch-CcVersion` disponibilità elevata per questa versione precedente.
    
    Per ottenere il supporto completo della disponibilità elevata, tornare alla versione 1.4.2, in modo che la versione in esecuzione e la versione dello script siano uguali. Se si verificano problemi con la distribuzione 1.4.2, disinstallarla e reinstallarla il prima possibile.
    
- **Problema: i certificati dell'autorità di certificazione o i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono prossimi alla scadenza o sono compromessi.**
    
    **Risoluzione:** I certificati dell'Autorità di certificazione di Skype for Business sono validi per cinque anni. I certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono validi per due anni.
    
    > [!NOTE]
    > In Cloud Connector versione 2.0 e successive, il cmdlet Renew-CcServerCertificate è cambiato in Update-CcServerCertificate e il cmdlet Renew-CcCACertificate è cambiato in Update-CcCACertificate. 
  
    Se i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono quasi scaduti o compromessi, eseguire il cmdlet Renew-CcServerCertificate o Update-CcServerCertificate per rinnovare i certificati.
    
    Se i certificati dell'Autorità di certificazione sono prossimi alla scadenza, eseguire il cmdlet Renew-CcCACertificate o Update-CcCACertificate per rinnovare i certificati.
    
    **Se i certificati dell'Autorità** di certificazione vengono compromessi e nel sito è presente un solo dispositivo, eseguire la procedura seguente:
    
1. Eseguire il cmdlet Enter-CcUpdate per svuotare i servizi e mettere l'appliance in modalità manutenzione.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:
    
    Per i rilasci del connettore cloud prima della 2.0:
    
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
    
3. Se viene utilizzato TLS tra il gateway e Mediation Server, eseguire il cmdlet Export-CcRootCertificate dall'appliance e quindi installare il certificato esportato nei gateway PSTN. Potrebbe anche essere necessario riemettere il certificato nel gateway.

   ```powershell
   Export-CcRootCertificate
   ```

4. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.

   ```powershell
   Exit-CcUpdate
   ```


    **Se i certificati dell'Autorità** di certificazione sono compromessi e nel sito sono presenti più appliance, eseguire i passaggi sequenziali seguenti in ogni appliance del sito.
    
    Microsoft consiglia di eseguire questi passaggi durante i periodi di utilizzo non di punta.
    
1. Nel primo appliance, eseguire il cmdlet Remove-CcCertificationAuthorityFile per pulire i file di backup della CA nella \<SiteRoot\> directory.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Eseguire il cmdlet Enter-CcUpdate per svuotare i servizi e mettere ogni appliance in modalità manutenzione.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Nella prima appliance, eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'Autorità di certificazione e tutti i certificati del server interni:
    
     Per i rilasci del connettore cloud prima della 2.0:
    
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

4. Nel primo dispositivo, eseguire il cmdlet seguente per eseguire il backup dei file dell'autorità di certificazione nella \<SiteRoot\> cartella.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. In tutti gli altri dispositivi nello stesso sito, eseguire i comandi seguenti per utilizzare i file di backup della CA, in modo che tutti gli appliance utilizzino lo stesso certificato radice e quindi richiedere nuovi certificati. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se viene utilizzato TLS tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate da qualsiasi appliance del sito e quindi installare il certificato esportato nei gateway PSTN. Potrebbe anche essere necessario riemettere il certificato nel gateway.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: viene visualizzato il seguente messaggio di errore nel registro del servizio di gestione del connettore cloud, "C:\Programmi\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": Errore CceService: 0 : Eccezione imprevista durante la segnalazione dello stato online: System.Management.Automation.CmdletInvocationException: Accesso non riuscito per l'utente \<Global Tenant Admin\> . Creare un nuovo oggetto credenziali, verificando di aver utilizzato il nome utente e la password corretti. ---\>**
    
    **Risoluzione:** Le credenziali di amministratore del tenant globale di Microsoft 365 o Office 365 sono state modificate dopo la registrazione dell'appliance Cloud Connector. Per aggiornare le credenziali archiviate localmente nell'appliance Cloud Connector, eseguire le operazioni seguenti da PowerShell di amministratore nell'appliance host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: dopo aver modificato la password per l'account del server host utilizzato per la distribuzione, viene visualizzato il messaggio di errore seguente: "ConvertTo-SecureString : Chiave non valida per l'utilizzo nello stato specificato." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o durante l'esecuzione del cmdlet Get-CcCredential.**
    
    **Risoluzione:** Tutte le credenziali del connettore cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml". Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.
    
    **Se si esegue Cloud Connector versione 1.4.2,** rigenerare tutte le password del connettore cloud eseguendo la procedura seguente:
    
  1. Riavviare il server host.
    
  2. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
  3. Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere di nuovo le password dopo la descrizione. Immettere le stesse password immesse in precedenza per la distribuzione di Cloud Connector.
    
     **Se si esegue Cloud Connector versione 2.0 o successiva,** rigenerare tutte le password del connettore cloud eseguendo la procedura seguente:
    
  4. Riavviare il server host.
    
  5. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .
    
  6. Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere di nuovo le password dopo la descrizione. 
    
     Se il file della password memorizzata nella cache è stato generato con Cloud Connector versione 1.4.2, utilizzare la password VMAdmin per la password CceService quando richiesto. Immettere la stessa password immessa prima per la distribuzione di Cloud Connector per tutti gli altri account.
    
     Se il file delle password memorizzate nella cache è stato generato con Cloud Connector versione 1.4.2 e le password DomainAdmin e VMAdmin sono diverse, è necessario eseguire la procedura seguente:
    
  7. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
  8. Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
  9. Quando viene richiesto di immettere la nuova credenziale dell'account, immettere la password per la password DomainAdmin utilizzata in precedenza.
    
     Se il file della password memorizzata nella cache è stato generato con Cloud Connector versione 2.0 o successiva, per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se sono state modificate le password DomainAdmin e VMAdmin, è necessario eseguire la procedura seguente:
    
  10. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
       1. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService
    
       2. Quando viene richiesto di immettere la nuova credenziale dell'account, immettere la password per la password DomainAdmin utilizzata in precedenza.
    
  11. Eseguire Set-CcCredential -AccountType VmAdmin come segue:
    
       1. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService
    
       2. Quando viene richiesto di immettere la nuova credenziale dell'account, immettere la password per la password VmAdmin usata in precedenza. 
    
- **Problema: con Cloud Connector versione 2.1 e successive, quando si esegue Register-CcAppliance o altri cmdlet nell'appliance, viene visualizzato un messaggio di errore del tipo: "Per Each-Object : Impossibile trovare la proprietà 'Common' su questo oggetto. Verificare che la proprietà esista. In C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Risoluzione:** Cloud Connector 2.1 e versioni successive richiede .NET Framework 4.6.1 o versione successiva. Aggiornare il .NET Framework nell'appliance alla versione 4.6.1 o successiva ed eseguire di nuovo i cmdlet.

- **Problema: con Cloud Connector Edition 2.1, quando si esegue Install-CcAppliance, viene visualizzato un messaggio di errore simile al seguente: "Impossibile installare una nuova istanza con errore: Impossibile impostare "State" perché solo le stringhe possono essere utilizzate come valori per impostare le proprietà XmlNode"**

   **Risoluzione:** In Cloudconnector.ini, nella sezione [Common], aggiungi la configurazione "State" come segue: CountryCode=US State=WA City=Redmond

   Non è obbligatorio che la riga "State" abbia valore, tuttavia la riga "State" non può essere rimossa dal file Cloudconnector.ini file.

- **Problema: viene visualizzato il seguente messaggio di errore "Dismount-WindowsImage : Dismount-WindowsImage non riuscito. Codice di errore = 0xc1550115" durante l'installazione o l'aggiornamento di Cloud Connector Edition.**
    
    **Risoluzione:** Avviare una console di PowerShell come amministratore, eseguire "DISM -Cleanup-Wim'". In questo modo verranno ripulite tutte le immagini con problemi. Eseguire Install-CcAppliance o attendere l'aggiornamento automatico dei bit.
    
- **Problema: la distribuzione della prima appliance Cloud Connector in un ambiente ha esito negativo**
    
    **Risoluzione:** I passaggi da eseguire dipendono dal motivo per cui la distribuzione non è riuscita:
    
  - Se il primo dispositivo Cloud Connector non riesce e non è possibile determinare il motivo dell'errore, è necessario installare di nuovo l'appliance fino a quando la distribuzione non riesce e quindi installare le altre appliance.
    
  - Se il primo dispositivo Cloud Connector ha esito negativo con un problema secondario, ad esempio un problema di certificato esterno, potrebbe essere possibile risolvere il problema senza installare di nuovo l'appliance. È quindi possibile utilizzare PowerShell remoto tenant per contrassegnare la distribuzione come completata come segue. È inoltre possibile eseguire la procedura seguente se la prima distribuzione ha avuto esito positivo, ma, per qualche motivo, Cloud Connector non riesce a segnalare la distribuzione come completata.
    
  - Per ottenere l'identità (GUID) della prima appliance Cloud Connector, eseguire il cmdlet Get-CsHybridPSTNAppliance cloud.
    
  - Per contrassegnare l'appliance come distribuito correttamente, eseguire il Set-CsCceApplianceDeploymentStatus come segue:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: è necessario verificare e installare manualmente gli aggiornamenti di Windows nel server host o nelle macchine virtuali.**
    
   **Risoluzione:** Ti consigliamo di sfruttare gli aggiornamenti automatici del sistema operativo forniti da Skype for Business Cloud Connector Edition. Dopo la registrazione di un'appliance per la gestione online e l'aggiornamento automatico del sistema operativo è abilitato, il server host e le macchine virtuali controllano e installano automaticamente gli aggiornamenti di Windows in base alle impostazioni dell'intervallo di tempo di aggiornamento del sistema operativo.
    
   Se devi controllare e installare manualmente gli aggiornamenti di Windows, segui i passaggi di questa sezione che si applicano al tipo di distribuzione. È consigliabile pianificare l'aggiornamento contemporaneamente sia del server host che delle macchine virtuali in esecuzione su di esso per ridurre al minimo la quantità di tempo di in down time necessario per gli aggiornamenti.
    
   Se si preferisce, è possibile utilizzare un server Windows Server Update Services (WSUS) per fornire aggiornamenti ai server Cloud Connector. Assicurati di configurare Windows Update in modo che **non si installi** automaticamente.
    
   Per informazioni su come aggiornare manualmente la distribuzione di Cloud Connector, vedere la sezione seguente.
    
- **Problema: quando Cloud Connector si aggiorna a una nuova build, i cmdlet di Cloud Connector non vengono aggiornati.** Ciò accade a volte se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.
    
  **Risoluzione:** Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:
    
   - Chiudere PowerShell nell'appliance Cloud Connector e quindi riaprire PowerShell.
    
     - In caso contrario, puoi eseguire Import-Module CloudConnector -Force. 
 
-   **Problema: "Il termine "Stop-CsWindowsService" non viene riconosciuto come nome di un cmdlet, di una funzione, di un file di script o di un programma funzionante." quando si tenta di eseguire un cmdlet Enter-CcUpdate.**

    **Risoluzione:** Elimina il file $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea questo file come cache di cmdlet dai moduli trovati in modo che non sia necessario analizzare di nuovo tutti i moduli ogni volta perché ciò renderebbe le cose molto lente. Molto probabilmente, c'è stato un danneggiamento dei file che ha fornito risultati fuorvianti a PowerShell durante la lettura dalla cache.

-   **Problema: "Import-Module CloudConnector" genera l'errore "Import-Module: Il modulo specificato "CloudConnector" non è stato caricato perché non è stato trovato alcun file di modulo valido in alcuna directory dei moduli"**

    **Risoluzione:**
    - Verificare che il modulo CloudConnector esista effettivamente in c:\Programmi\WindowsPowerShell\Modules
    
    - Dopo aver convalidato l'esistenza del modulo CloudConnector in questo percorso, è possibile modificare la variabile di ambiente PSModulePath che archivia il percorso dei percorsi dei moduli:
    
     a. Modifica temporanea: avviare Powershell come amministratore ed eseguire il comando seguente: $env:PSModulePath = $env:PSModulePath + "; C:\Programmi\WindowsPowerShell\Modules\"
        
     b. Per la modifica persistente, avviare PowerShell come amministratore ed eseguire i comandi seguenti, uno alla volta: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Programmi\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Installare manualmente gli aggiornamenti di Windows

Se non vuoi usare gli aggiornamenti automatici nel tuo ambiente, segui questi passaggi per cercare e applicare manualmente gli aggiornamenti di Windows. Il controllo e l'installazione degli aggiornamenti di Windows potrebbero richiedere il riavvio del server. Quando un server host viene riavviato, gli utenti non potranno utilizzare Cloud Connector per effettuare o ricevere chiamate. È possibile verificare e installare manualmente gli aggiornamenti per controllare quando vengono evasi gli aggiornamenti e quindi riavviare i computer in base alle esigenze durante i periodi in cui si sceglie di evitare interruzioni dei servizi.
  
Per verificare manualmente la disponibilità di aggiornamenti, connettersi a ogni server host e aprire il **Pannello di controllo.** Selezionare **Sistema e sicurezza di Windows \> Update** e quindi gestire gli aggiornamenti e i riavvii del server in base alle esigenze dell'ambiente.
  
- Se nel sito è presente un solo dispositivo, connettersi a ogni macchina virtuale e aprire il **Pannello di controllo.** Selezionare **System and Security Windows \> Update** e quindi configurare gli aggiornamenti e i riavvii del server in base alle esigenze.
    
- Se nel sito sono presenti più appliance, gli utenti non potranno accedere all'istanza da aggiornare e riavviare durante gli aggiornamenti. Gli utenti si connetteranno ad altre istanze della distribuzione finché tutte le macchine virtuali e tutti i servizi Skype for Business non vengono avviati nelle macchine virtuali dopo il completamento degli aggiornamenti. Per evitare potenziali interruzioni del servizio, è possibile rimuovere l'istanza dall'ha mentre si applicano gli aggiornamenti e quindi ripristinarla al termine. A questo scopo:
    
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
    
- Directory siti remoti in ogni computer.
    
- La directory siti locale nel computer ospita la cartella radice del sito condiviso.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Il processo Microsoft.Rtc.CCE.ManagementService.exe.