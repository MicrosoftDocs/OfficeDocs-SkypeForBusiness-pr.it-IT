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
description: Risoluzione dei problemi relativi alla distribuzione di Cloud Connector Edition.
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220226"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Risolvere i problemi relativi alla distribuzione di Cloud Connector
 
Risoluzione dei problemi relativi alla distribuzione di Cloud Connector Edition.
  
In questo argomento vengono descritte le soluzioni ai problemi comuni relativi alle distribuzioni di Cloud Connector Edition. Se si verificano problemi con le chiamate da e verso la rete PSTN (Public Switched Telephone Network), è possibile indagare seguendo le soluzioni descritte in questo argomento.
  
Il connettore Cloud fornisce meccanismi incorporati per la risoluzione automatica di alcuni problemi. Un processo di rilevamento automatico consente di individuare eventuali problemi con gli apparecchi dei connettori cloud e, se possibile, di eseguire azioni correttive per risolvere tali problemi senza l'intervento dell'amministratore. Il processo di rilevamento funziona come indicato di seguito:
  
- **Sequenza di rilevamento:** Il servizio di gestione Cloud Connector esegue un processo ogni 60 secondi per rilevare se un dispositivo è inattivo. In Cloud Connector versione 2,0 e versioni successive, il processo di rilevamento utilizza l'opzione Corpnet di Skype for business per rendere le connessioni di PowerShell ai computer dei connettori cloud; per le versioni precedenti a 2,0, il processo di rilevamento utilizza l'opzione di gestione dei connettori cloud.
    
    > [!NOTE]
    > Affinché il ripristino automatico abbia esito positivo, è necessario che vi sia connettività di rete tra l'host e le macchine virtuali tramite l'opzione di rete host. Assicurarsi di controllare la connettività di rete per garantire che il rilevamento automatico e il ripristino possano avere esito positivo. 
  
- **Monitoraggio:** I servizi seguenti sono monitorati in Cloud Connector versione 2,0 e versioni successive:
    
  - Le macchine virtuali non sono connesse ai commutatori virtuali Corporate o Internet del connettore Cloud
    
  - Le macchine virtuali si trovano in uno stato salvato o interrotto
    
  - Servizi server di gestione centrale: REPLICA, MASTER
    
  - Servizi Mediation Server: REPLICA, RTCSRV e MEDSVC
    
  - Servizi server perimetrali: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Le regole del firewall in ingresso sono disattivate per CS RTCSRV sul server perimetrale, CS RTCMEDSRV su Mediation Server
    
    In Cloud Connector versione 1.4.2 sono monitorati solo i servizi seguenti:
    
  - Servizi Mediation Server: RTCSRV e MEDSVC
    
  - Servizio server perimetrale: RTCSRV
    
- **Processo di ripristino:** Se i servizi monitorati sono indesiderati, un dispositivo è segnato verso il basso e i servizi vengono interrotti e contrassegnati manualmente fino a quando non è possibile risolvere tutti i problemi. In questo modo si eviteranno le chiamate dal routing a un dispositivo che potrebbe causare errori di chiamata.
    
    Il servizio di gestione Cloud Connector ritenterà il ripristino automatico come indicato di seguito.
    
  - L'intervallo di tentativi iniziale è ogni dieci secondi con un intervallo di tempo massimo di un'ora.
    
  - Per i primi tre tentativi di ripristino, l'intervallo di tempo è di 10 secondi. A partire dal quarto tentativo, il tempo di intervallo aumenta di due volte l'intervallo di tempo precedente. Ad esempio, il quarto Riprova si verificherà tra 20 secondi, il quinto in 40 secondi e così via. 
    
  - Quando il tempo massimo di intervallo di un'ora viene raggiunto, i tentativi continueranno una volta all'ora.
    
  - Quando il ripristino ha esito positivo, i conteggi dell'intervallo e dei tentativi sono impostati sui valori iniziali.
    
  - Se il servizio di gestione viene riavviato, i conteggi dell'intervallo e dei tentativi vengono reimpostati sui valori iniziali.
    
## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito sono riportate le soluzioni ai problemi comunemente riscontrati:
  
- **Problema: la distribuzione ha esito negativo o si blocca durante l'esecuzione degli script di distribuzione. Dopo aver eseguito l'accesso a ogni VM, l'indirizzo IP è mancante o non corretto per la scheda di gestione/interno/esterno.**
    
    **Soluzione:** Questo problema non può essere risolto automaticamente. Le schede NIC non possono essere aggiunte alle macchine virtuali mentre sono in esecuzione. Chiudere e rimuovere le macchine virtuali in gestione Hyper-v, quindi eseguire i cmdlet seguenti:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: dopo l'installazione del server e della foresta di Active Directory, il server CMS e/o il Mediation Server non hanno partecipato correttamente al dominio.**
    
    **Soluzione:** Per risolvere il problema, eseguire la procedura seguente:
    
  - Accedere al server Active Directory e verificare che il dominio sia stato creato correttamente.
    
  - Accedere a CMS/Mediation Server e verificare che nella scheda NIC di corpnet sia assegnato un indirizzo IP valido e che l'indirizzo IP e il DNS statici validi siano configurati come indirizzi IP del server Active Directory.
    
  - Accedere a CMS/Mediation Server e aprire un prompt dei comandi. Verificare che sia possibile eseguire il ping del nome di dominio completo e dell'indirizzo IP del server Active Directory. Se non è possibile, potrebbe essere presente un conflitto di indirizzi IP. Provare a assegnare un nuovo IP per Active Directory e aggiornare il DNS su CMS/Mediation Server di conseguenza.
    
- **Problema: viene visualizzato il messaggio di errore "Remove-VMSwitch: failed durante la rimozione dello switch Ethernet virtuale. Lo switch virtuale ' switch di gestione dei connettori cloud ' non può essere eliminato perché viene utilizzato eseguendo macchine virtuali o assegnato ai pool di bambini.**
    
    **Soluzione:** L'opzione "gestione dei connettori cloud" non è stata eliminata dopo la distribuzione. Se si preme questo errore, visitare il sito di gestione di Hyper-v e verificare che non vi sia ancora una macchina virtuale ancora connessa. Se sono ancora connesse macchine virtuali, disconnetterle ed eliminare l'opzione di gestione. Se non è ancora possibile eliminare l'opzione di gestione, riavviare il server host e riprovare.
    
- **Problema: viene visualizzato il messaggio di errore "Service RTCMRAUTH non è stato avviato. Verificare che il servizio non sia disabilitato. "**
    
    > [!NOTE]
    > Questo problema si applica solo alle versioni dei connettori cloud precedenti a 1.4.2. 
  
    L'errore di avvio potrebbe anche essere dovuto al fatto che in precedenza questo server front-end non è stato eseguito correttamente (utilizzando il failover del computer). In questo caso, è consigliabile richiamare il failback (con il failback del computer).
    
    **Soluzione:** Questo problema si verifica su un server perimetrale quando il certificato CA radice o il certificato CA intermedio non è considerato attendibile dal server perimetrale. Anche se il certificato esterno può essere importato, ma la catena di certificati è interrotta. In questa condizione, il servizio RTCMRAUTH e/o RTCSRV non può essere avviato.
    
    Importare manualmente il certificato della CA radice e tutti i certificati di CA intermedi del certificato esterno nel server perimetrale e quindi riavviare il server perimetrale. Dopo aver visualizzato i servizi RTCMRAUTH e RTCSRV avviati nel server perimetrale, tornare al server host, avviare una console PowerShell come amministratore ed eseguire il cmdlet seguente per passare alla nuova distribuzione:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: il server host è stato riavviato quando sono stati applicati gli aggiornamenti di Windows e le chiamate servite dal server sono in errore.**
    
    **Soluzione:** Se è stato distribuito un ambiente a disponibilità elevata, Microsoft fornisce un cmdlet che consente di spostare un computer host (istanza di distribuzione) all'interno o all'esterno della topologia corrente quando si controlla e si installa Windows Update manualmente. Per ottenere questo risultato, attenersi alla procedura seguente:
    
1. Nel server host avviare una console di PowerShell come amministratore e quindi eseguire le operazioni seguenti:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Controllare se sono disponibili aggiornamenti e installarli.
    
3. Nella console PowerShell, eseguire il cmdlet seguente:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando viene effettuata una chiamata da un client Skype for business utilizzando un numero PSTN, la chiamata non può essere inoltrata a una conferenza invitando un altro numero PSTN.**
    
    **Soluzione:** Per risolvere il problema, vedere [Configure online Hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: viene visualizzato un messaggio di avviso relativo all'installazione di Windows Update quando si installa Active Directory Server-"l'aggiornamento automatico di Windows non è abilitato. Per assicurarsi che il ruolo o la caratteristica appena installata venga aggiornata automaticamente, attiva Windows Update. "**
    
    **Soluzione:** Avviare una sessione di PowerShell remote tenant con le credenziali di amministratore del tenant di Skype for business, quindi eseguire il seguente cmdlet per controllare la configurazione di _EnableAutoUpdate_ del sito:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se _EnableAutoUpdate_ è impostato su **true**, è possibile ignorare il messaggio di avviso in modo sicuro perché il servizio CCEManagement gestirà il download e l'installazione degli aggiornamenti di Windows sia per le macchine virtuali sia per il server host. Se _EnableAutoUpdate_ è impostato su **false**, eseguire il cmdlet seguente per impostarlo su **true**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    In alternativa, è possibile cercare e installare manualmente gli aggiornamenti. Vedere la sezione successiva.
    
- **Problema: viene visualizzato un messaggio di errore: non è possibile registrare l'apparecchio perché l'input corrente/nomesito di configurazione o il nome utente o l'FQDN del Mediation \< \> \< \> \< server \> o l' \< indirizzo IP di Mediation Server sono \> in conflitto con gli apparecchi esistenti. Rimuovere un dispositivo di conflitto o aggiornare le informazioni di input/configurazione e quindi registrarsi di nuovo. ' quando si esegue Register-CcAppliance per registrare l'accessorio corrente in linea.**
    
    **Soluzione:** I valori per l' \< indirizzo IP di appliancename \> , \< FQDN Mediation Server \> e \< Mediation Server \> devono essere univoci e utilizzati solo per la registrazione di un dispositivo. Per impostazione predefinita, \< appliancename \> deriva dal nome host. \<FQDN Mediation Server \> e \< indirizzo IP di Mediation Server \> definito nel file ini di configurazione.
    
    Ad esempio, utilizzando (Appliancename = MyserverNew, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10) per la registrazione a sitename = sito, ma se è presente un dispositivo registrato (Appliancename = MyServer, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10), si avrà il conflitto.
    
    Per prima cosa, controllare il file CloudConnector. ini nella sezione Directory di ApplianceRoot. Si otterrà \< siteName \> , \< FQDN Mediation Server \> e \< i valori degli indirizzi IP Mediation Server \> nel file. \<Appliancename \> è il nome del server host.
    
    In secondo luogo, avviare tenant Remote PowerShell usando le credenziali di amministratore del tenant di Skype for business, quindi eseguire il seguente cmdlet per controllare gli apparecchi registrati.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Dopo aver identificato i conflitti, è possibile aggiornare il file CloudConnector. ini con le informazioni corrispondenti all'apparecchio registrato oppure annullare la registrazione dell'accessorio esistente per risolvere i conflitti.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: il cmdlet Get-CcRunningVersion restituisce un valore vuoto se è in esecuzione un dispositivo distribuito nell'host.**
    
  **Soluzione:** Ciò può verificarsi quando si esegue l'aggiornamento da 1.3.4 o 1.3.8 a 1.4.1. Dopo aver installato la versione 1.4.1 con il. msi, è necessario eseguire `Register-CcAppliance` prima di eseguire qualsiasi altro cmdlet. `Register-CcAppliance`eseguirà la migrazione del file Module. ini da%UserProfile%\CloudConnector a%ProgramData%\CloudConnector. In caso di mancato recapito, verrà creato un nuovo modulo. ini nella cartella%ProgramData%\CloudConnector e verranno sostituite le informazioni sulla versione di esecuzione/backup per 1.3.4 o 1.3.8.
    
  Confrontare i file Module. ini in%UserProfile%\CloudConnector e%ProgramData%\CloudConnector. Se sono presenti differenze, eliminare il file Module. ini in%ProgramData%\CloudConnector e rieseguire `Register-CcAppliance` . È inoltre possibile modificare manualmente il file nella versione di backup e esecuzione corretta.
    
- **Problema: dopo aver eseguito il cmdlet Switch-CcVersion per passare a una versione precedente diversa dalla versione dello script corrente, non è disponibile alcun supporto per la disponibilità elevata per questa versione precedente.**
    
    **Soluzione:** Ad esempio, è stato eseguito l'aggiornamento da 1.4.1 a 1.4.2. La versione corrente dello script, che può essere determinata dall'esecuzione `Get-CcVersion` , e la versione in esecuzione, che può essere determinata eseguendo, `Get-CcRunningVersion` sono entrambe 1.4.2. In questo momento, se si esegue `Switch-CcVersion` per cambiare la versione in esecuzione di nuovo a 1.4.1, quindi non vi sarà alcun supporto per la disponibilità elevata per questa versione precedente.
    
    Per ottenere un supporto completo per la disponibilità elevata, tornare a 1.4.2, quindi la versione in esecuzione e la versione script sono uguali. Se si verificano problemi con la distribuzione di 1.4.2, disinstallare e reinstallare il più presto possibile.
    
- **Problema: i certificati dell'autorità di certificazione o i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono quasi scaduti o sono compromessi.**
    
    **Soluzione:** I certificati dell'autorità di certificazione Skype for business sono validi per cinque anni. I certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono validi per due anni.
    
    > [!NOTE]
    > In Cloud Connector versione 2,0 e versioni successive, il cmdlet Renew-CcServerCertificate è stato modificato in Update-CcServerCertificate e il cmdlet Renew-CcCACertificate è stato modificato in Update-CcCACertificate. 
  
    Se i certificati interni rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono vicini alla scadenza o sono compromessi, eseguire il cmdlet Renew-CcServerCertificate o Update-CcServerCertificate per rinnovare i certificati.
    
    Se i certificati dell'autorità di certificazione sono vicini alla scadenza, eseguire il cmdlet Renew-CcCACertificate o Update-CcCACertificate per rinnovare i certificati.
    
    **Se i certificati dell'autorità di certificazione sono compromessi ed è presente un solo dispositivo nel sito,** eseguire le operazioni seguenti:
    
1. Eseguire il cmdlet Enter-CcUpdate per scaricare i servizi e inserire l'accessorio in modalità di manutenzione.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:
    
    Per i rilasci dei connettori cloud prima 2,0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    O per il connettore Cloud Release 2,0 e versioni successive:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se si utilizza TLS tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate dall'accessorio e quindi installare il certificato esportato nei gateway PSTN. È inoltre possibile che venga richiesto di riemettere il certificato nel gateway.

   ```powershell
   Export-CcRootCertificate
   ```

4. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione.

   ```powershell
   Exit-CcUpdate
   ```


    **Se i certificati dell'autorità di certificazione sono compromessi e sono presenti più dispositivi nel sito,** eseguire i passaggi sequenziali seguenti in ogni accessorio del sito.
    
    Microsoft consiglia di eseguire questi passaggi durante i periodi di utilizzo non di picco.
    
1. Nel primo dispositivo, eseguire il cmdlet Remove-CcCertificationAuthorityFile per pulire i file di backup della CA nella \< directory SiteRoot \>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Eseguire il cmdlet Enter-CcUpdate per scaricare i servizi e inserire ogni dispositivo in modalità di manutenzione.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Sul primo dispositivo, eseguire i cmdlet seguenti per reimpostare e creare nuovi certificati dell'autorità di certificazione e tutti i certificati server interni:
    
     Per i rilasci dei connettori cloud prima 2,0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     O per il connettore Cloud Release 2,0 e versioni successive:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Sul primo dispositivo, eseguire il seguente cmdlet per eseguire il backup dei file della CA nella \< \> cartella SiteRoot
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. In tutti gli altri dispositivi nello stesso sito, eseguire i seguenti comandi per utilizzare i file di backup della CA, in modo che tutti gli elettrodomestici utilizzino lo stesso certificato radice e quindi richiedere nuovi certificati. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se si utilizza TLS tra il gateway e il Mediation Server, eseguire il cmdlet Export-CcRootCertificate da qualsiasi accessorio del sito e quindi installare il certificato esportato nei gateway PSTN. È inoltre possibile che venga richiesto di riemettere il certificato nel gateway.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Eseguire il cmdlet Exit-CcUpdate per avviare i servizi e uscire dalla modalità di manutenzione. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: viene visualizzato il messaggio di errore seguente nel registro del servizio di gestione Cloud Connector, "C:\Program Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0: Unexpected exception when report status to online: System. Management. Automation. CmdletInvocationException: logon failed for the user \< Global tenant admin \> . Creare un nuovo oggetto Credential, assicurandosi di aver utilizzato il nome utente e la password corretti. ---\>**
    
    **Soluzione:** Le credenziali di amministratore del tenant globale di Microsoft 365 o Office 365 sono state modificate dopo la registrazione dell'accessorio Cloud Connector. Per aggiornare le credenziali memorizzate localmente nell'accessorio Cloud Connector, eseguire le operazioni seguenti dall'amministratore PowerShell nell'accessorio host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: dopo aver modificato la password per l'account del server host utilizzato per la distribuzione, viene visualizzato il messaggio di errore seguente: "ConvertTo-SecureString: Key non valido per l'utilizzo nello stato specificato." in%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o durante l'esecuzione del cmdlet Get-CcCredential.**
    
    **Soluzione:** Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ". Quando la password sul server host cambia, sarà necessario aggiornare le credenziali memorizzate localmente.
    
    **Se si esegue il Cloud Connector versione 1.4.2,** rigenerare tutte le password dei connettori cloud attenendosi alla procedura seguente:
    
  1. Riavviare il server host.
    
  2. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".
    
  3. Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione. Immettere le stesse password immesse prima per la distribuzione del connettore Cloud.
    
     **Se si esegue il Cloud Connector versione 2,0 o successiva,** rigenerare tutte le password dei connettori cloud attenendosi alla procedura seguente:
    
  4. Riavviare il server host.
    
  5. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".
    
  6. Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione. 
    
     Se il file della password memorizzato nella cache è stato generato con Cloud Connector versione 1.4.2, utilizzare la password di VMAdmin per la password di CceService quando richiesto. Immettere la stessa password immessa prima per la distribuzione del connettore Cloud per tutti gli altri account.
    
     Se il file della password memorizzato nella cache è stato generato con il connettore Cloud versione 1.4.2 e le password di DomainAdmin e VMAdmin sono diverse, è necessario eseguire le operazioni seguenti:
    
  7. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
  8. Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.
    
  9. Quando viene richiesto di utilizzare la nuova credenziale account, immettere la password per la password di DomainAdmin utilizzata in precedenza.
    
     Se il file della password memorizzato nella cache è stato generato con il connettore Cloud versione 2,0 o successiva, per impostazione predefinita VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se sono state modificate le password di DomainAdmin e VMAdmin, è necessario eseguire le operazioni seguenti:
    
  10. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
       1. Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService
    
       2. Quando viene richiesto di utilizzare la nuova credenziale account, immettere la password per la password di DomainAdmin utilizzata in precedenza.
    
  11. Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:
    
       1. Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService
    
       2. Quando viene richiesto di utilizzare la nuova credenziale account, immettere la password per la password di VmAdmin utilizzata in precedenza. 
    
- **Problema: con il connettore Cloud versione 2,1 e versioni successive, quando si esegue Register-CcAppliance o altri cmdlet sull'accessorio, viene visualizzato un messaggio di errore, ad esempio: "per ogni oggetto: la proprietà' Common ' non può essere trovata su questo oggetto. Verificare che la proprietà esista. In C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **Soluzione:** Il connettore Cloud 2,1 e versioni successive richiede .NET Framework 4.6.1 o versione successiva. Aggiornare .NET Framework nell'accessorio alla versione 4.6.1 o successive ed eseguire di nuovo i cmdlet.

- **Problema: con Cloud Connector Edition 2,1, durante l'esecuzione di install-CcAppliance, viene visualizzato un messaggio di errore, ad esempio: "Impossibile installare una nuova istanza con errore: Impossibile impostare" stato "perché solo le stringhe possono essere utilizzate come valori per impostare le Proprietà XmlNode"**

   **Soluzione:** In Cloudconnector. ini, nella sezione [Common], aggiungere il file di configurazione "state" come indicato di seguito: CountryCode = US State = WA City = Redmond

   Non è obbligatorio che la riga "state" abbia valore, tuttavia la riga "state" non può essere rimossa dal file Cloudconnector. ini.

- **Problema: viene visualizzato il seguente messaggio di errore "Dismount-WindowsImage: Dismount-WindowsImage failed. Codice di errore = 0xc1550115 "durante l'installazione o l'aggiornamento di Cloud Connector Edition.**
    
    **Soluzione:** Avviare una console di PowerShell come amministratore, eseguire "DISM-Cleanup-Wim '". In questo modo vengono ripulite tutte le immagini problematiche. Eseguire di nuovo install-CcAppliance oppure attendere l'aggiornamento automatico dei bit.
    
- **Problema: la distribuzione del primo accessorio Cloud Connector in un ambiente HA HA esito negativo**
    
    **Soluzione:** I passaggi da eseguire dipendono dal motivo per cui la distribuzione non ha avuto esito positivo:
    
  - Se il primo accessorio Cloud Connector ha esito negativo e non è possibile determinare il motivo dell'errore, è necessario installarlo di nuovo finché la distribuzione non ha esito positivo e quindi installare gli altri dispositivi.
    
  - Se il primo accessorio Cloud Connector ha esito negativo con un problema secondario, ad esempio un problema di certificato esterno, potrebbe essere possibile risolvere il problema senza reinstallare l'accessorio. È quindi possibile utilizzare PowerShell remote tenant per contrassegnare la distribuzione con esito positivo come indicato di seguito. È inoltre possibile utilizzare la procedura seguente se la prima distribuzione ha avuto esito positivo, ma, per qualche motivo, il connettore Cloud non riesce a segnalare la distribuzione come esito positivo.
    
  - Per ottenere l'identità (GUID) del primo accessorio Cloud Connector, eseguire il cmdlet Get-CsHybridPSTNAppliance.
    
  - Per contrassegnare l'accessorio come distribuito correttamente, eseguire il set-CsCceApplianceDeploymentStatus come indicato di seguito:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: è necessario controllare e installare manualmente gli aggiornamenti di Windows nel server host o nelle macchine virtuali.**
    
   **Soluzione:** Si consiglia di usufruire degli aggiornamenti automatici del sistema operativo forniti da Skype for Business Cloud Connector Edition. Dopo che un dispositivo è stato registrato per la gestione online e l'aggiornamento automatico del sistema operativo è abilitato, il server host e le macchine virtuali controlleranno e installeranno automaticamente gli aggiornamenti di Windows in base alle impostazioni delle finestre di tempo di aggiornamento del sistema operativo.
    
   Se è necessario controllare e installare manualmente gli aggiornamenti di Windows, seguire la procedura descritta in questa sezione che si applicano al tipo di distribuzione. È consigliabile pianificare l'aggiornamento del server host e delle macchine virtuali in esecuzione contemporaneamente per ridurre al minimo la quantità di tempo di inattività necessaria per gli aggiornamenti.
    
   Se si preferisce, è possibile utilizzare un server Windows Server Update Services (WSUS) per fornire gli aggiornamenti ai server dei connettori cloud. Basta essere sicuri di configurare Windows Update per **non** installare automaticamente.
    
   Per informazioni su come aggiornare manualmente la distribuzione del connettore Cloud, vedere la sezione seguente.
    
- **Problema: quando il connettore Cloud viene aggiornato a una nuova generazione, i cmdlet del connettore Cloud non vengono aggiornati.** Questo accade talvolta se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.
    
  **Soluzione:** Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:
    
   - Chiudere PowerShell sull'accessorio Cloud Connector e quindi riaprire PowerShell.
    
     - In alternativa, è possibile eseguire Import-Module CloudConnector-Force. 
 
-   **Problema: "il termine ' Stop-CsWindowsService ' non è riconosciuto come nome di un cmdlet, di una funzione, di un file di script o di un programma eseguibile." quando si tenta di eseguire il cmdlet Enter-CcUpdate.**

    **Soluzione:** Eliminare il file $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea questo file come una cache di cmdlet dai moduli individuati in modo che non sia necessario analizzare di nuovo tutti i moduli ogni volta che renderebbe le cose davvero lente. È probabile che si sia verificato un danneggiamento dei file che ha fornito risultati contestabili a PowerShell durante la lettura di nuovo da tale cache.

-   **Problema: "Import-Module CloudConnector" genera un errore "Import-Module: il modulo specificato" CloudConnector "non è stato caricato perché non è stato trovato alcun file di modulo valido in nessuna directory del modulo"**

    **Risoluzione:**
    - Verificare che esista effettivamente il modulo CloudConnector in c:\Program Files\WindowsPowerShell\Modules
    
    - Dopo aver convalidato che il modulo CloudConnector esiste in questo percorso, è possibile modificare la variabile di ambiente PSModulePath archiviando il percorso delle posizioni dei moduli:
    
     a. Modifica temporanea: avviare PowerShell come amministratore ed eseguire il comando seguente: $env:P SModulePath = $env:P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Per le modifiche permanenti, avviare PowerShell come amministratore ed eseguire i comandi seguenti, uno per uno: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," computer ")

    
## <a name="install-windows-updates-manually"></a>Installare manualmente gli aggiornamenti di Windows

Se non si desidera utilizzare gli aggiornamenti automatici nell'ambiente in uso, eseguire la procedura seguente per controllare e applicare manualmente gli aggiornamenti di Windows. Per il controllo e l'installazione degli aggiornamenti di Windows potrebbe essere necessario un riavvio del server. Quando un server host viene riavviato, gli utenti non saranno in grado di utilizzare il connettore Cloud per effettuare o ricevere chiamate. È possibile controllare e installare manualmente gli aggiornamenti per controllare quando si verificano gli aggiornamenti e quindi riavviare i computer in base alle esigenze nei periodi in cui si sceglie di evitare interruzioni dei servizi.
  
Per verificare manualmente la disponibilità di aggiornamenti, connettersi a ogni server host e aprire il **Pannello di controllo**. Selezionare **sistema e sicurezza \> Windows Update**, quindi gestire gli aggiornamenti e i riavvii del server in base alle proprie esigenze per l'ambiente.
  
- Se nel sito è presente un solo dispositivo, connettersi a ogni macchina virtuale e aprire il **Pannello di controllo**. Selezionare **sistema e sicurezza \> Windows Update**, quindi configurare gli aggiornamenti e i riavvii del server in base alle esigenze.
    
- Se nel sito sono presenti più dispositivi, l'istanza che si sta aggiornando e riavviata non può essere letta dagli utenti durante gli aggiornamenti. Gli utenti si connetteranno ad altre istanze della distribuzione finché tutte le macchine virtuali e tutti i servizi Skype for business non avranno inizio nelle macchine virtuali dopo il completamento degli aggiornamenti. Per evitare possibili interruzioni del servizio, è possibile rimuovere l'istanza da HA quando si applicano gli aggiornamenti e quindi ripristinarli al termine. A questo scopo:
    
1. In ogni server host, aprire una console di PowerShell come amministratore.
    
2. Rimuovere l'istanza da HA con il cmdlet seguente:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Seguire la procedura per una singola istanza per applicare manualmente gli aggiornamenti e riavviare la macchina virtuale.
    
4. Impostare di nuovo l'istanza su HA con il cmdlet seguente:
    
   ```powershell
   Exit-CcUpdate
   ```

Per le distribuzioni multisito, eseguire i passaggi per un singolo sito per ogni sito nella distribuzione, applicando gli aggiornamenti a un sito alla volta.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Suggerimenti per l'installazione del software antivirus nel computer host del connettore Cloud

Se è necessario installare il software antivirus nel computer host del connettore Cloud, è necessario aggiungere le esclusioni seguenti:
  
- Directory degli apparecchi locali su ogni computer.
    
- Directory del sito remota su ogni computer.
    
- La directory del sito locale nel computer ospita la cartella radice del sito condiviso.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Il processo Microsoft. Rtc. CCE. ManagementService. exe.
