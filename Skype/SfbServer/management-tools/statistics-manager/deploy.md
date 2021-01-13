---
title: Distribuire il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire la gestione delle statistiche per Skype for Business Server.'
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814816"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Distribuire il gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire la gestione delle statistiche per Skype for Business Server.
  
 La gestione delle statistiche per Skype for Business Server è uno strumento potente che consente di visualizzare i dati di integrità e prestazioni di Skype for Business Server in tempo reale. È possibile eseguire il polling dei dati delle prestazioni tra centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione delle statistiche.
  
Prima di tentare di installare Gestione statistiche, accertarsi di conoscere i requisiti software, di rete e hardware. Per ulteriori informazioni, vedere [Plan for Statistics Manager for Skype for Business Server](plan.md).
  
> [!NOTE]
> Se si esegue l'aggiornamento da una versione precedente di gestione statistiche, vedere [upgrade Statistics Manager for Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> Il sito Web di gestione delle statistiche è stato testato e funziona correttamente in Internet Explorer 11 +, Edge 20.10240 + e Chrome 46 + (versione Evergreen corrente). 
  
È possibile trovare il responsabile delle statistiche scaricabile all'indirizzo [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) . 
  
In questa sezione sono contenute le seguenti sezioni:
  
- [Distribuire Gestione statistiche](deploy.md#BKMK_Deploy)
    
- [Risoluzione dei problemi relativi alla distribuzione](deploy.md#BKMK_Troubleshoot)
    
- [Creare un certificato autofirmato](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Distribuire Gestione statistiche
<a name="BKMK_Deploy"> </a>

Per distribuire Gestione statistiche, eseguire la procedura seguente:
  
1. Preparare il computer host del listener installando il sistema di memorizzazione nella cache di ReDim in memoria e assicurandosi di aver installato i certificati corretti.
    
2. Installare il servizio listener nel computer host. 
    
3. Installare il sito Web nel computer host.
    
4. Installare un agente in ogni computer Skype for Business Server che si desidera monitorare.
    
5. Importare la topologia per i server di cui si esegue il monitoraggio.
    
> [!NOTE]
> Le redini, il servizio listener e il sito Web devono essere installati nello stesso computer host. Assicurarsi che nel computer host non sia installato Skype for Business Server. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparare il computer host del listener

Per preparare il computer host, è necessario installare il sistema di memorizzazione nella cache di ReDim in memoria e verificare che il certificato sia valido nel computer. Microsoft consiglia di installare l'ultima build stabile di redis 3,0. Statistiche Manager versione 2,0 è stato testato con ReDim 3.2.100. 
  
1. Scaricare ReDim dal seguente sito: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) . 
    
    I programmi di installazione non firmati possono essere scaricati da [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Se necessario, i file binari firmati sono disponibili tramite i gestori di pacchetti più diffusi: [NuGet](https://www.nuget.org/packages/Redis-64/) e [choclatey](https://chocolatey.org/packages/redis-64).
    
   - Eseguire il MSI fornito e seguire le istruzioni visualizzate.
    
   - Non selezionare la casella di controllo per aggiungere una regola del firewall.
    
2. Il servizio listener richiede un certificato. Microsoft consiglia vivamente di disporre di un certificato firmato da un'autorità di certificazione attendibile. 
    
    Se si desidera utilizzare un certificato autofirmato, ad esempio per scopi di testing in un laboratorio, vedere [creare un certificato autofirmato](deploy.md#BKMK_SelfCert).
    
    Si noti che l'agente utilizza la verifica dell'identificazione personale del certificato (anziché la verifica della catena). La convalida del certificato non sarà completa perché è possibile utilizzare certificati autofirmati.
    
### <a name="install-the-listener-service"></a>Installare il servizio listener

Installare il servizio listener nel computer host eseguendo la StatsManPerfAgentListener.msi e specificando quanto segue:
  
1. Esaminare il contratto di licenza e, se lo si desidera, selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**. 
    
2. Nella pagina successiva, specificare le informazioni seguenti:
    
   - **Password del servizio:** Questa è la password che gli agenti remoti utilizzeranno per eseguire l'autenticazione nel servizio listener.
    
   - **Porta del servizio:** Si tratta del numero di porta HTTPS che verrà utilizzato dal listener per comunicare con gli agenti. Durante l'installazione, questa porta sarà consentita tramite il firewall locale, verrà creato un elenco di controllo di accesso all'URL e un certificato SSL verrà associato a questa porta. Il valore predefinito è 8443.
    
   - **Identificazione personale del certificato:** Questa è l'identificazione personale del certificato che il listener utilizzerà per crittografare il protocollo HTTPS. Il servizio di rete deve disporre dell'accesso in lettura alla chiave privata.
    
     Fare clic sul pulsante **Seleziona..** . per scegliere l'identificazione personale.
    
     È possibile trovare l'identificazione personale del certificato utilizzando Gestione certificati oppure utilizzando il seguente comando di PowerShell:
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **Install dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarlo dal valore predefinito utilizzando il pulsante **Sfoglia...** .
    
   - **Directory AppData:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarlo dal valore predefinito. Non verrà eliminato alla disinstallazione.
    
3. Fare clic su **Installa**.
    
Per convalidare l'installazione, eseguire le operazioni seguenti:
  
1. Aprire un browser e passare a https://localhost: \<service-port\> /Healthcheck/
    
    Per impostazione predefinita, la porta del servizio è 8443 (a meno che non sia stata specificata un'altra porta).
    
2. Per assicurarsi che il listener sia stato installato correttamente, cercare gli elementi seguenti:
    
   - Se viene visualizzata la pagina Healthcheck, l'installazione del listener ha avuto esito positivo.
    
   - Se il valore di KnownServerCount è 1 o superiore, viene stabilita la connessione a ReDim.
    
   - Dopo aver aspettato qualche minuto e dopo che è stato installato almeno un agente, verificare che il contatore ValuesWritten sia in aumento.
    
### <a name="install-the-website"></a>Installare il sito Web

Installare il sito Web nel computer host eseguendo il StatsManWebSite.msi (incluso in [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) e specificando quanto segue:
  
1. Esaminare il contratto di licenza e, se lo si desidera, selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**. 
    
2. Nella pagina successiva, specificare le informazioni seguenti:
    
   - **Porta del servizio:** Questo è il numero di porta su cui il sito Web sarà in attesa. È possibile modificarlo in un secondo momento utilizzando binding di gestione IIS. Durante l'installazione, questa porta sarà consentita attraverso il firewall locale.
    
   - **Install dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarlo dal valore predefinito utilizzando il pulsante **Sfoglia...** .
    
   - **Directory AppData:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarlo dal valore predefinito. Non verrà eliminato alla disinstallazione.
    
3. Fare clic su **Installa**.
    
Per visualizzare il sito Web, aprire un browser e passare a: http://localhost , WebPort \> /.
  
Per visualizzare solo le informazioni di integrità, aprire un browser e passare a: http://localhost: \<webport\> /Healthcheck/.
  
Per impostazione predefinita, il numero della porta Web è 8080. È possibile modificare l'associazione di porta del sito Web utilizzando Gestione IIS.
  
Il programma di installazione Web aggiunge un gruppo di sicurezza locale denominato StatsManWebSiteUsers. È possibile aggiungere account a questo gruppo di sicurezza per concedere l'accesso al sito Web. 
  
### <a name="install-the-agents"></a>Installare gli agenti

Installare un agente in ogni server Skype for business che si desidera monitorare eseguendo il StatsManPerfAgent.msi e specificando quanto segue:
  
1. Esaminare il contratto di licenza e, se lo si desidera, selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**. 
    
2. Nella pagina successiva, specificare le informazioni seguenti:
    
   - **Password del servizio:** Questa è la password che l'agente remoto utilizzerà per eseguire l'autenticazione nel servizio listener.
    
   - **URI del servizio:** Si tratta dell'URI in cui risiede il listener. Deve utilizzare il https://name:port formato.
    
     È possibile utilizzare un nome NETBIOS o un FQDN. È possibile utilizzare il nome specificato anche come **oggetto** o **nomi alternativi del soggetto** del certificato nel servizio listener, ma non si tratta di un requisito.
    
   - **Identificazione personale del servizio:** Si tratta dell'identificazione personale del certificato SSL utilizzato dal listener. L'agente utilizzerà questa identificazione personale per eseguire l'autenticazione nel listener. (Non eseguirà la convalida completa dei certificati perché è possibile utilizzare certificati autofirmati).
    
   - **Install dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarlo dal valore predefinito utilizzando il pulsante **Sfoglia...** .
    
   - **Directory AppData:** Questa è la directory in cui verranno archiviati la cartella Logs e il file di password.txt crittografato. Potrebbe essere necessario modificarlo dal valore predefinito. Non verrà eliminato alla disinstallazione.
    
3. Fare clic su **Installa**.
    
Se si sta installando un agente su numerosi computer, è probabile che sia necessario eseguire questa operazione in modalità automatica. Ad esempio: 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importare la topologia
<a name="BKMK_ImportTopology"> </a>

Dopo l'installazione e l'esecuzione di gestione statistiche, è necessario importare la topologia di Skype for Business Server in modo che il responsabile delle statistiche conosca il sito, il pool e il ruolo di ogni server. Per importare la topologia di Skype for Business Server, è possibile utilizzare il cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) per recuperare le informazioni su ogni pool in uso nell'organizzazione e quindi importare queste informazioni in gestione statistiche.
  
Per importare la topologia di Skype for Business Server, eseguire la procedura seguente:
  
1. In un host con i cmdlet di PowerShell per Skype for Business Server:
    
    a. Eseguire il comando seguente: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copiare il file "mypoolinfo.xml" nel server che esegue il listener.
    
2. Nell'host che esegue il listener:
    
   a. Eseguire PowerShell.
    
   b. Passare alla directory in cui è installato il listener. Il valore predefinito è: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Per verificare quali server vengono aggiunti e aggiornati, eseguire il comando riportato di seguito:
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Il seguente comando consente di visualizzare tutte le opzioni:
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Per visualizzare le informazioni sul server attualmente importato, eseguire lo script seguente: 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

Se si desidera monitorare i server non presenti nella topologia di Skype for Business Server, ad esempio un server di Exchange, è possibile eseguire un'importazione a server singolo nell'host che esegue il listener. Per eseguire un'importazione a server singolo, eseguire la procedura seguente:
  
1. Passare alla directory in cui è installato il listener. Il valore predefinito è: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Eseguire il comando seguente:
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Risoluzione dei problemi relativi alla distribuzione
<a name="BKMK_Troubleshoot"> </a>

Se un agente non è in avvio, verificare quanto segue: 
  
- L'agente è registrato in statistica Manager?
    
    1. Assicurarsi di aver seguito le istruzioni per importare la topologia. Vedere [importare la topologia](deploy.md#BKMK_ImportTopology).
        
    2. Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi di un cluster di SQL AlwaysOn, è necessario aggiungere manualmente l'agente attenendosi alle istruzioni [riportate in importare la topologia](deploy.md#BKMK_ImportTopology).
    
- L'agente può contattare l'ascoltatore?
    
    1. Verificare che il servizio listener sia in esecuzione. 
        
        Se non è in esecuzione, verificare che ReDim sia in esecuzione e quindi provare a riavviare il listener.
        
    2. Verificare che la porta sia aperta al servizio listener e che il computer dell'agente sia in grado di comunicare con la porta.
    
- Per assicurarsi che la gestione delle statistiche stia raccogliendo dati, è possibile controllare il file CSV come indicato di seguito. 
    
    Il comando seguente consente di recuperare i nomi di archiviazione dei contatori: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Il comando seguente consente di recuperare i valori per i contatori specificati: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Per informazioni su tutti gli eventi che potrebbero essere visualizzati nel registro eventi applicazioni, vedere [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Creare un certificato autofirmato
<a name="BKMK_SelfCert"> </a>

Microsoft consiglia vivamente di utilizzare un certificato firmato da un'autorità di certificazione attendibile. Tuttavia, se si desidera utilizzare un certificato autofirmato per il testing, eseguire le operazioni seguenti: 
  
1. Da una console di PowerShell durante l'accesso come amministratore, digitare quanto segue:
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Tipo  `certlm.msc` . Verrà aperta la gestione dei certificati per il computer locale.
    
3. Passare a **Personal** e quindi aprire i **certificati**.
    
4. Fare clic con il pulsante destro del mouse su **StatsManListener- \> tutte le attività- \> Gestisci chiavi private...**
    
5. Fare clic su **Aggiungi**.
    
6. Nella casella **immettere i nomi degli oggetti da selezionare** Digitare quanto segue: servizio di rete
    
7. Fare clic su **OK**.
    
8. Sotto **controllo completo**, deselezionare la casella **Consenti** . (È necessario solo l'accesso in lettura).
    
9. Fare clic su **OK**.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_SelfCert"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
    
- [Risoluzione dei problemi relativi a gestione statistica per Skype for Business Server](troubleshoot.md) ß
