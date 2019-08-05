---
title: Risolvere i problemi di distribuzione del Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.
ms.openlocfilehash: 1049ec2f8f3b85c71c7b9203916b79764e9be161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190592"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Risolvere i problemi di distribuzione del Cloud Connector
 
Risolvere i problemi relativi alla distribuzione di Cloud Connector Edition.
  
Questo argomento descrive le soluzioni ai problemi comuni relativi alle distribuzioni di Cloud Connector Edition. Se si verificano problemi con chiamate da e verso la rete PSTN (Public Switched Telephone Network), è possibile eseguire le analisi seguendo le soluzioni descritte in questo argomento.
  
Cloud Connector offre meccanismi predefiniti per la risoluzione automatica di alcuni problemi. Un processo di rilevamento automatico consente di individuare potenziali problemi con gli apparecchi per il Cloud Connector e, se possibile, di eseguire azioni correttive per risolvere questi problemi senza bisogno di un intervento di amministratore. Il processo di rilevamento funziona nel modo seguente:
  
- **Sequenza di rilevamento:** Il servizio di gestione di Cloud Connector esegue un processo ogni 60 secondi per rilevare se un dispositivo è in calo. In Cloud Connector versione 2,0 e successive, il processo di rilevamento usa l'opzione di Corpnet di Skype for business per rendere le connessioni di PowerShell ai computer del Cloud Connector; per le versioni precedenti a 2,0, il processo di rilevamento usa l'opzione di gestione del Cloud Connector.
    
    > [!NOTE]
    > Per avere successo il ripristino automatico, è necessario che ci sia connettività di rete tra l'host e le macchine virtuali tramite lo switch di rete host. Assicurati di controllare la connettività di rete per verificare che il rilevamento e il ripristino automatici possano avere esito positivo. 
  
- **Monitoraggio:** I servizi seguenti vengono monitorati in Cloud Connector versione 2,0 e successive:
    
  - Le macchine virtuali non sono connesse agli switch virtuali Corporate o Internet di Cloud Connector
    
  - Le macchine virtuali si trovano in uno stato salvato o arrestato
    
  - Servizi server di gestione centralizzati: REPLICA, MASTER
    
  - Servizi Mediation Server: REPLICA, RTCSRV e MEDSVC
    
  - Servizi Edge Server: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Le regole del firewall in ingresso sono disabilitate per CS RTCSRV su Edge Server, CS RTCMEDSRV su Mediation Server
    
    In Cloud Connector versione 1.4.2 vengono monitorati solo i servizi seguenti:
    
  - Servizi Mediation Server: RTCSRV e MEDSVC
    
  - Servizio Edge Server: RTCSRV
    
- **Processo di ripristino:** Se i servizi monitorati non sono disponibili, un dispositivo viene contrassegnato in basso e i servizi vengono arrestati e contrassegnati come manuali fino a quando non è possibile risolvere tutti i problemi. In questo modo si eviteranno le chiamate dal routing a un dispositivo che potrebbe causare errori di chiamata.
    
    Il servizio di gestione di Cloud Connector ritenterà il ripristino automatico nel modo seguente
    
  - L'intervallo di tentativi iniziale è ogni dieci secondi con un intervallo di tempo massimo di un'ora.
    
  - Per i primi tre tentativi di recupero, l'intervallo di tempo è di 10 secondi. A partire dal quarto tentativo, l'intervallo di tempo aumenta di due volte l'intervallo di tempo precedente. Ad esempio, il quarto tentativo si verificherà in 20 secondi, il quinto in 40 secondi e così via. 
    
  - Quando viene raggiunto l'intervallo di tempo massimo di un'ora, i tentativi continueranno una volta all'ora.
    
  - Quando il ripristino viene eseguito correttamente, i conteggi intervallo e riprova vengono impostati sui valori iniziali.
    
  - Se il servizio di gestione viene riavviato, i conteggi dell'intervallo e dei tentativi vengono reimpostati sui valori iniziali.
    
## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito sono riportate le soluzioni ai problemi comunemente incontrati:
  
- **Problema: la distribuzione non riesce o smette di rispondere durante l'uso degli script di distribuzione. Dopo aver eseguito l'accesso a ogni VM, l'indirizzo IP è mancante o non corretto per la scheda di amministrazione/interna/esterna.**
    
    **Risoluzione:** Questo problema non può essere risolto automaticamente. Le NIC non possono essere aggiunte alle VM mentre sono in esecuzione. Chiudere e rimuovere queste VM in gestione Hyper-v, quindi eseguire i cmdlet seguenti:
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **Problema: dopo l'installazione del server e della foresta di Active Directory, il server CMS e/o il server di mediazione non hanno aderito correttamente al dominio.**
    
    **Risoluzione:** Per risolvere il problema, eseguire le operazioni seguenti:
    
  - Accedere al server di Active Directory e verificare che il dominio sia stato creato correttamente.
    
  - Accedere a CMS/Mediation Server e verificare che nella corpnet NIC sia stato assegnato un indirizzo IP valido e che l'indirizzo IP e il DNS statici validi sia configurato come IP del server di Active Directory.
    
  - Accedere a CMS/Mediation Server e aprire un prompt dei comandi. Verificare che sia possibile eseguire il ping del nome di dominio completo e dell'indirizzo IP del server Active Directory. Se non è possibile, potrebbe essere presente un conflitto di indirizzi IP. Provare a assegnare un nuovo IP per Active Directory e ad aggiornare il DNS in CMS/Mediation Server di conseguenza.
    
- **Problema: viene visualizzato il messaggio di errore seguente, "Remove-VMSwitch: failed durante la rimozione di switch Ethernet virtuale. Impossibile eliminare l'opzione di gestione del Cloud Connector di Virtual Switch perché viene usata eseguendo macchine virtuali o assegnata ai pool di bambini. "**
    
    **Risoluzione:** L'opzione "Gestione connettore Cloud" non è stata eliminata dopo la distribuzione. Se si preme questo errore, passare a gestione Hyper-v e verificare che non ci sia ancora una macchina virtuale ancora connessa. Se sono ancora connesse macchine virtuali, scollegarle ed eliminare il pulsante di gestione. Se non è ancora possibile eliminare l'opzione di gestione, riavviare il server host e riprovare.
    
- **Problema: viene visualizzato il messaggio di errore seguente, "Impossibile avviare il servizio RTCMRAUTH. Verificare che il servizio non sia disabilitato. "**
    
    > [!NOTE]
    > Questo problema si applica solo alle versioni dei connettori cloud precedenti a 1.4.2. 
  
    L'errore di avvio potrebbe anche essere dovuto al fatto che il server front-end in precedenza era fallito (con il failover del computer). In questo caso, richiamare fail back (con il computer non riesci).
    
    **Risoluzione:** Questo problema si verifica in un server perimetrale quando il certificato della CA radice o del certificato CA intermedio non è considerato attendibile dall'Edge Server. Anche se il certificato esterno può essere importato, ma la catena di certificati viene interrotta. In questa condizione non è possibile avviare il servizio RTCMRAUTH e/o RTCSRV.
    
    Importare manualmente il certificato della CA radice e tutti i certificati intermedi della CA del certificato esterno nell'Edge Server e quindi riavviare il server perimetrale. Dopo aver visualizzato i servizi RTCMRAUTH e RTCSRV avviati nel server perimetrale, tornare al server host, avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per passare alla nuova distribuzione:
    
  ```
  Switch-CcVersion
  ```

- 
    
    **Problema: il server host è stato riavviato quando sono stati applicati gli aggiornamenti di Windows e le chiamate servite dal server non riescono.**
    
    **Risoluzione:** Se è stato distribuito un ambiente a elevata disponibilità, Microsoft fornisce un cmdlet che consente di trasferire un computer host (istanza di distribuzione) in entrata o in uscita dalla topologia corrente quando si controlla e si installa Windows Update manualmente. Eseguire la procedura seguente per eseguire questa operazione:
    
1. Nel server host avviare una console di PowerShell come amministratore, quindi eseguire:
    
   ```
   Enter-CcUpdate
   ```

2. Verificare la disponibilità di aggiornamenti e installarli.
    
3. Nella console di PowerShell eseguire il cmdlet seguente:
    
   ```
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando si effettua una chiamata da un client Skype for business usando un numero PSTN, la chiamata non può essere inoltrata a una conferenza invitando un altro numero PSTN.**
    
    **Risoluzione:** Per risolvere il problema, vedere [configurare le impostazioni del server di mediazione ibrida online](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: viene visualizzato un messaggio di avviso su Windows Update durante l'installazione di Active Directory Server-"l'aggiornamento automatico di Windows non è abilitato. Per assicurarsi che il ruolo o la caratteristica appena installata venga aggiornata automaticamente, attivare Windows Update.**
    
    **Risoluzione:** Avviare una sessione remota di PowerShell del tenant usando le credenziali di amministratore del tenant di Skype for business, quindi eseguire il cmdlet seguente per controllare la configurazione di _EnableAutoUpdate_ del sito:
    
  ```
  Get-CsHybridPSTNSite
  ```

    Se _EnableAutoUpdate_ è impostato su **true**, è possibile ignorare il messaggio di avviso in modo sicuro perché il servizio CCEManagement gestirà il download e l'installazione degli aggiornamenti di Windows sia per le macchine virtuali che per il server host. Se _EnableAutoUpdate_ è impostato su **false**, eseguire il cmdlet seguente per impostarlo su **true**.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    In alternativa, è possibile cercare e installare manualmente gli aggiornamenti. Vedere la sezione successiva.
    
- **Problema: viene visualizzato un messaggio di errore: non è possibile registrare l'appliance perché l' \<input\> corrente \<o l'\> indirizzo \<di configurazione di\> nomesito o di appliancename o di mediazione server \< \> conflitti con gli appliance o gli apparecchi esistenti. Rimuovere l'appliance di conflitto o aggiornare le informazioni di input/configurazione e quindi registrarsi di nuovo. ' quando Esegui Register-CcAppliance per registrare l'appliance corrente su online.**
    
    **Risoluzione:** I valori per \<l'indirizzo\>\> IP \<di appliancename\> , \<FQDN e Mediation Server devono essere univoci e usati solo per una registrazione Appliance. Per impostazione predefinita \<, appliancename\> deriva dal nome host. \<Indirizzo\> IP di\> Mediation Server FQDN e \<Mediation Server definito nel file ini di configurazione.
    
    Ad esempio, usando (Appliancename = MyserverNew, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10) per la registrazione a sitename = sito, ma in presenza di un dispositivo registrato (Appliancename = MyServer, Mediation Server FQDN = ms.contoso.com, Mediation Server IP address = 10.10.10.10), si avrà il conflitto.
    
    Per prima cosa, controlla il file CloudConnector. ini nella sezione Directory di ApplianceRoot. Nel file verranno \<consentiti i valori\> di \<indirizzo\> IP per nomesito\>, \<Mediation Server e Mediation Server. \<Appliancename\> è il nome del server host.
    
    In secondo luogo, avvia tenant Remote PowerShell usando le credenziali di amministratore del tenant di Skype for business, quindi Esegui il cmdlet seguente per controllare gli apparecchi o gli elettrodomestici registrati.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Dopo aver identificato qualsiasi conflitto, è possibile aggiornare il file CloudConnector. ini con le informazioni corrispondenti all'accessorio registrato oppure annullare la registrazione dell'appliance esistente per risolvere i conflitti.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: il cmdlet Get-CcRunningVersion restituisce un valore vuoto se è in uso un dispositivo distribuito nell'host.**
    
  **Risoluzione:** Questo problema può verificarsi quando si esegue l'aggiornamento da 1.3.4 o 1.3.8 a 1.4.1. Dopo aver installato la versione 1.4.1 con il file con estensione msi, `Register-CcAppliance` è necessario eseguire prima di eseguire qualsiasi altro cmdlet. `Register-CcAppliance`eseguirà la migrazione del file Module. ini da%UserProfile%\CloudConnector a%ProgramData%\CloudConnector. Se non è possibile, verrà creato un nuovo Module. ini nella cartella%ProgramData%\CloudConnector e le informazioni sulla versione in esecuzione/backup verranno sostituite per 1.3.4 o 1.3.8.
    
  Confrontare i file Module. ini nella cartella%UserProfile%\CloudConnector e%ProgramData%\CloudConnector. Se sono presenti differenze, eliminare il file Module. ini in%ProgramData%\CloudConnector e rieseguirlo `Register-CcAppliance`. È anche possibile modificare manualmente il file nella versione di backup e esecuzione corretta.
    
- **Problema: dopo aver eseguito il cmdlet Switch-CcVersion per passare a una versione precedente diversa dalla versione di script corrente, non esiste un supporto per la disponibilità elevata per questa versione precedente.**
    
    **Risoluzione:** Ad esempio, è stato eseguito l'aggiornamento da 1.4.1 a 1.4.2. La versione corrente dello script, che può essere determinata eseguendo `Get-CcVersion`, e la versione in esecuzione, che può essere determinata eseguendo `Get-CcRunningVersion` sono entrambi 1.4.2. In questo momento, se si esegue `Switch-CcVersion` per cambiare di nuovo la versione in esecuzione in 1.4.1, non sarà disponibile un supporto per la disponibilità elevata per questa versione precedente.
    
    Per ottenere il supporto completo della disponibilità elevata, tornare a 1.4.2, quindi la versione in esecuzione e la versione dello script sono le stesse. Se si verificano problemi con la distribuzione di 1.4.2, disinstallare e reinstallare il più presto possibile.
    
- **Problema: i certificati di autorità di certificazione o i certificati interni rilasciati a Central Management store, Mediation Server e Edge Server sono quasi scaduti o compromessi.**
    
    **Risoluzione:** I certificati dell'autorità di certificazione Skype for business sono validi per cinque anni. I certificati interni rilasciati a Central Management store, Mediation Server e Edge Server sono validi per due anni.
    
    > [!NOTE]
    > In Cloud Connector versione 2,0 e successive il cmdlet Renew-CcServerCertificate è stato modificato in Update-CcServerCertificate e il cmdlet Renew-CcCACertificate è stato modificato in Update-CcCACertificate. 
  
    Se i certificati interni rilasciati a Central Management store, Mediation Server e Edge Server sono quasi scaduti o compromessi, eseguire il cmdlet Renew-CcServerCertificate o Update-CcServerCertificate per rinnovare i certificati.
    
    Se i certificati dell'autorità di certificazione sono vicini alla scadenza, eseguire il cmdlet Renew-CcCACertificate o Update-CcCACertificate per rinnovare i certificati.
    
    **Se i certificati dell'autorità di certificazione sono compromessi ed è presente un solo dispositivo nel sito,** eseguire la procedura seguente:
    
1. Eseguire il cmdlet Enter-CcUpdate per scaricare i servizi e inserire l'appliance in modalità di manutenzione.
   
   ```
   Enter-CcUpdate
   ```
   
2. Eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati di autorità di certificazione e tutti i certificati server interni:
    
    Per i rilasci Cloud Connector prima di 2,0:
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Oppure per il rilascio di Cloud Connector 2,0 e versioni successive:
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se TLS viene usato tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate dall'appliance e quindi installare il certificato esportato nei gateway PSTN. Potrebbe essere anche necessario inviare di nuovo il certificato nel gateway.

   ```
   Export-CcRootCertificate
   ```

4. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.

   ```
   Exit-CcUpdate
   ```


    **Se i certificati dell'autorità di certificazione sono compromessi e nel sito sono presenti più dispositivi,** eseguire i passaggi sequenziali seguenti per ogni appliance del sito.
    
    Microsoft consiglia di eseguire questi passaggi durante i tempi di utilizzo non di punta.
    
1. Nel primo appliance eseguire il cmdlet Remove-CcCertificationAuthorityFile per pulire i file di backup della CA nella directory \<SiteRoot.\>

     ```
     Remove-CcCertificationAuthorityFile
     ```
    
2. Eseguire il cmdlet Enter-CcUpdate per scaricare i servizi e inserire ogni appliance in modalità di manutenzione.

     ```
     Enter-CcUpdate
     ```
    
3. Nel primo appliance eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati di autorità di certificazione e tutti i certificati server interni:
    
     Per i rilasci Cloud Connector prima di 2,0:
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Oppure per il rilascio di Cloud Connector 2,0 e versioni successive:
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Nel primo appliance eseguire il cmdlet seguente per il backup dei file della CA nella cartella \<SiteRoot.\>
    
     ```
     Backup-CcCertificationAuthority
     ```
   
5. In tutti gli altri dispositivi nello stesso sito eseguire i comandi seguenti per utilizzare i file di backup della CA, in modo che tutti gli apparecchi usino lo stesso certificato radice e quindi richiedere nuovi certificati. 
   
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se TLS viene usato tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate da qualsiasi appliance del sito e quindi installare il certificato esportato nei gateway PSTN. Potrebbe essere anche necessario inviare di nuovo il certificato nel gateway.
  
     ```
     Export-CcRootCertificate
     ```
     
7. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione. 

     ```
     Exit-CcUpdate
     ```
    
    
- **Problema: viene visualizzato il messaggio di errore seguente nel log del servizio di gestione di Cloud Connector, "C:\Program Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": errore CceService: 0: eccezione imprevista quando stato della segnalazione su online: System. Management. Automation. CmdletInvocationException: accesso non riuscito per \<l'amministratore\>del tenant globale dell'utente. Creare un nuovo oggetto credenziale, assicurandosi di avere usato il nome utente e la password corretti. ---\>**
    
    **Risoluzione:** Le credenziali di amministratore del tenant globale di Office 365 sono state modificate dopo la registrazione dell'appliance Cloud Connector. Per aggiornare le credenziali archiviate localmente nell'appliance Cloud Connector, eseguire le operazioni seguenti da PowerShell amministratore nell'appliance host:
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: dopo aver modificato la password per l'account del server host usato per la distribuzione, viene visualizzato il messaggio di errore seguente: "ConvertTo-SecureString: Key non valido per l'uso nello stato specificato." in%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o durante l'esecuzione del cmdlet Get-CcCredential.**
    
    **Risoluzione:** Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.
    
    **Se si esegue Cloud Connector versione 1.4.2,** rigenerare tutte le password dei connettori cloud eseguendo la procedura seguente:
    
  1. Riavviare il server host.
    
  2. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  3. Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione. Immettere le stesse password immesse prima per la distribuzione di Cloud Connector.
    
     **Se si esegue Cloud Connector versione 2,0 o successiva,** rigenerare tutte le password dei connettori cloud eseguendo la procedura seguente:
    
  4. Riavviare il server host.
    
  5. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  6. Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione. 
    
     Se il file della password memorizzato nella cache è stato generato con Cloud Connector versione 1.4.2, usare la password di VMAdmin per la password di CceService quando richiesto. Immettere la stessa password immessa prima per la distribuzione di Cloud Connector per tutti gli altri account.
    
     Se il file della password memorizzato nella cache è stato generato con Cloud Connector versione 1.4.2 e le password di DomainAdmin e VMAdmin sono diverse, è necessario eseguire le operazioni seguenti:
    
  7. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
  8. Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService.
    
  9. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di DomainAdmin usata in precedenza.
    
     Se il file della password memorizzato nella cache è stato generato con Cloud Connector versione 2,0 o successiva, per impostazione predefinita VmAdmin e DomainAdmin usano la stessa password di CceService. Se sono state modificate le password di DomainAdmin e VMAdmin, è necessario eseguire le operazioni seguenti:
    
  10. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
       1. Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService
    
       2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di DomainAdmin usata in precedenza.
    
  11. Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:
    
       1. Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService
    
       2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di VmAdmin usata in precedenza. 
    
- **Problema: con Cloud Connector versione 2,1 e versioni successive, quando si Esegui Register-CcAppliance o altri cmdlet nell'appliance, viene visualizzato un messaggio di errore, ad esempio: "For Each-Object: la proprietà" Common "non può essere trovata in questo oggetto. Verificare che la proprietà esista. In C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **Risoluzione:** Cloud Connector 2,1 e versioni successive richiede .NET Framework 4.6.1 o versione successiva. Aggiornare .NET Framework nell'appliance alla versione 4.6.1 o successive ed eseguire di nuovo i cmdlet.

- **Problema: con Cloud Connector Edition 2,1, durante l'installazione di install-CcAppliance, viene visualizzato un messaggio di errore simile al seguente: "Impossibile installare la nuova istanza con errore: non è possibile impostare" stato "perché solo le stringhe possono essere usate come valori per impostare le Proprietà XmlNode"**

   **Risoluzione:** In Cloudconnector. ini, nella sezione [Common], aggiungere la configurazione "state" come indicato di seguito: CountryCode = stato US = WA City = Redmond

   Non è obbligatorio che la riga "stato" abbia valore, ma la linea "stato" non può essere rimossa dal file Cloudconnector. ini.

- **Problema: viene visualizzato il messaggio di errore seguente "Dismount-WindowsImage: Dismount-WindowsImage non riuscito. Codice di errore = 0xc1550115 "durante l'installazione o l'aggiornamento di Cloud Connector Edition.**
    
    **Risoluzione:** Avviare una console di PowerShell come amministratore, eseguire "DISM-Cleanup-wim". In questo modo verranno ripulite tutte le immagini in difficoltà. Eseguire di nuovo install-CcAppliance o attendere che i bit vengano aggiornati automaticamente.
    
- **Problema: la distribuzione del primo accessorio Cloud Connector in un ambiente HA non riesce**
    
    **Risoluzione:** I passaggi da eseguire dipendono dal motivo per cui la distribuzione non è riuscita:
    
  - Se il primo dispositivo Cloud Connector non riesce e non si riesce a determinare il motivo dell'errore, è necessario installare di nuovo l'accessorio fino a quando non viene completata la distribuzione e quindi installare gli altri elettrodomestici.
    
  - Se il primo dispositivo Cloud Connector non riesce con un problema secondario, ad esempio un problema di certificato esterno, è possibile risolvere il problema senza reinstallare l'accessorio. Puoi quindi usare PowerShell remoto tenant per contrassegnare la distribuzione con successo come indicato di seguito. È anche possibile usare la procedura seguente se la prima distribuzione ha avuto esito positivo, ma, per qualche motivo, il connettore Cloud non riesce a segnalare la distribuzione come successo.
    
  - Per ottenere l'identità (GUID) del primo accessorio Cloud Connector, eseguire il cmdlet Get-CsHybridPSTNAppliance.
    
  - Per contrassegnare l'accessorio come distribuito correttamente, eseguire il set-CsCceApplianceDeploymentStatus nel modo seguente:
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: è necessario cercare e installare manualmente gli aggiornamenti di Windows nel server host o nelle macchine virtuali.**
    
   **Risoluzione:** Ti consigliamo di sfruttare gli aggiornamenti automatici del sistema operativo forniti da Skype for Business Cloud Connector Edition. Dopo che un dispositivo è stato registrato per la gestione online e l'aggiornamento automatico del sistema operativo è abilitato, il server host e le macchine virtuali controlleranno e installeranno automaticamente gli aggiornamenti di Windows in base alle impostazioni della finestra dell'ora di aggiornamento del sistema operativo.
    
   Se è necessario cercare e installare manualmente gli aggiornamenti di Windows, seguire i passaggi descritti in questa sezione che si applicano al tipo di distribuzione. È consigliabile pianificare l'aggiornamento sia del server host che delle macchine virtuali in esecuzione contemporaneamente per ridurre al minimo la quantità di tempo necessario per gli aggiornamenti.
    
   Se si preferisce, è possibile usare un server Windows Server Update Services (WSUS) per specificare gli aggiornamenti dei server di Cloud Connector. Basta essere sicuri di configurare Windows Update per **non** installare automaticamente.
    
   Per informazioni su come aggiornare manualmente la distribuzione di Cloud Connector, vedere la sezione seguente.
    
- **Problema: quando Cloud Connector viene aggiornato a una nuova build, i cmdlet di Cloud Connector non vengono aggiornati.** Ciò accade talvolta se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.
    
  **Risoluzione:** Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:
    
   - Chiudere PowerShell nell'accessorio Cloud Connector e quindi riaprire PowerShell.
    
     - In alternativa, è possibile eseguire Import-Module CloudConnector-Force. 
 
-   **Problema: "il termine" Stop-CsWindowsService "non è riconosciuto come nome di un cmdlet, di una funzione, di un file di script o di un programma eseguibile." errore durante il tentativo di esecuzione del cmdlet Enter-CcUpdate.**

    **Risoluzione:** Eliminare il file $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea questo file come una cache di cmdlet da moduli che trova in modo che non debba rianalizzare tutti i moduli ogni volta che renderebbe le cose molto lente. Molto probabilmente, c'è stato un certo danneggiamento dei file che ha fornito risultati fuorvianti a PowerShell durante la lettura di nuovo da tale cache.

-   **Problema: "Import-Module CloudConnector" genera l'errore "Import-Module: il modulo specificato" CloudConnector "non è stato caricato perché non è stato trovato alcun file di modulo valido in una directory del modulo"**

    **Risoluzione**
    - Verificare che il modulo CloudConnector esista in c:\Program Files\WindowsPowerShell\Modules
    
    - Dopo aver convalidato che il modulo CloudConnector esiste in questa posizione, la variabile di ambiente PSModulePath che archivia il percorso delle posizioni dei moduli può essere modificata:
    
     un. Modifica temporanea: avviare PowerShell come amministratore ed eseguire il comando seguente: $env:P SModulePath = $env:P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Per le modifiche permanenti, avviare PowerShell come amministratore ed eseguire i comandi seguenti, uno alla volta: $CurrentValue = [ambiente]:: GetEnvironmentVariable ("PSModulePath", "computer") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," computer ")

    
## <a name="install-windows-updates-manually"></a>Installare manualmente gli aggiornamenti di Windows

Se non si vogliono usare gli aggiornamenti automatici nell'ambiente, seguire questa procedura per verificare e applicare manualmente gli aggiornamenti di Windows. Per la verifica e l'installazione di aggiornamenti di Windows potrebbe essere necessario riavviare il server. Quando un server host viene riavviato, gli utenti non saranno in grado di usare il connettore Cloud per effettuare o ricevere chiamate. È possibile cercare e installare manualmente gli aggiornamenti per controllare quando vengono eseguiti gli aggiornamenti e quindi riavviare i computer in base alle esigenze durante il periodo di tempo scelto per evitare interruzioni dei servizi.
  
Per verificare manualmente la disponibilità di aggiornamenti, connettersi a ogni server host e aprire il **Pannello di controllo**. Selezionare **sistema e sicurezza \>di Windows Update**e quindi gestire gli aggiornamenti e riavviare il server in base alle esigenze dell'ambiente.
  
- Se nel sito è presente un solo dispositivo, connettersi a ogni macchina virtuale e aprire il **Pannello di controllo**. Selezionare **sistema e sicurezza \>di Windows Update**e quindi configurare gli aggiornamenti e riavviare il server in base alle esigenze.
    
- Se nel sito sono presenti più dispositivi, l'istanza aggiornata e riavviata non può essere letta dagli utenti durante gli aggiornamenti. Gli utenti si connetteranno ad altre istanze della distribuzione finché non verranno completate tutte le macchine virtuali e tutti i servizi Skype for business in tutte le macchine virtuali. Per evitare potenziali interruzioni del servizio, è possibile rimuovere l'istanza da HA mentre si applicano gli aggiornamenti e quindi ripristinarla al termine. Per eseguire questa operazione:
    
1. In ogni server host aprire una console di PowerShell come amministratore.
    
2. Rimuovere l'istanza da HA con il cmdlet seguente:
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    Seguire i passaggi per una singola istanza per applicare manualmente gli aggiornamenti e riavviare la macchina virtuale.
    
4. Impostare di nuovo l'istanza su HA con il cmdlet seguente:
    
   ```
   Exit-CcUpdate
   ```

Per le distribuzioni multisito, seguire i passaggi per un singolo sito per ogni sito nella distribuzione, applicando gli aggiornamenti a un sito alla volta.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Suggerimenti per l'installazione del software antivirus nel computer host del Cloud Connector

Se è necessario installare il software antivirus nel computer host del Cloud Connector, è necessario aggiungere le esclusioni seguenti:
  
- Directory locale Appliance in ogni computer.
    
- Directory del sito remoto in ogni computer.
    
- La directory locale del sito nel computer ospita la cartella radice del sito condivisa.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Il processo Microsoft. Rtc. CCE. ManagementService. exe.
