---
title: Distribuire il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803966"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Distribuire il gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire Statistics Manager per Skype for Business Server.
  
 Statistics Manager per Skype for Business Server è un potente strumento che consente di visualizzare in tempo reale i dati di integrità e prestazioni di Skype for Business Server. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione statistiche.
  
Prima di provare a installare Statistics Manager, assicurati di avere familiarità con il software, la rete e i requisiti hardware. Per altre informazioni, vedere [pianificare la gestione delle statistiche per Skype for Business Server](plan.md).
  
> [!NOTE]
> Se si esegue l'aggiornamento da una versione precedente di gestione statistiche, vedere [aggiornare statistiche Manager per Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> Il sito Web di Statistics Manager è stato testato e funziona correttamente in Internet Explorer 11 +, Edge 20.10240 + e Chrome 46 + (versione Evergreen corrente). 
  
Puoi trovare il responsabile delle statistiche scaricabile all' [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)indirizzo. 
  
Questo argomento contiene le sezioni seguenti:
  
- [Distribuire Gestione statistiche](deploy.md#BKMK_Deploy)
    
- [Risolvere i problemi di distribuzione](deploy.md#BKMK_Troubleshoot)
    
- [Creare un certificato autofirmato](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Distribuire Gestione statistiche
<a name="BKMK_Deploy"> </a>

Per distribuire Gestione statistiche, eseguire le operazioni seguenti:
  
1. Preparare il computer host del listener installando il sistema di Caching in memoria di redis e assicurandosi di avere installato i certificati appropriati.
    
2. Installare il servizio listener nel computer host. 
    
3. Installare il sito Web nel computer host.
    
4. Installare un agente in ogni computer di Skype for Business Server che si vuole monitorare.
    
5. Importare la topologia per i server che si stanno monitorando.
    
> [!NOTE]
> I Redi, il servizio listener e il sito Web devono essere tutti installati nello stesso computer host. Assicurarsi che nel computer host non sia installato Skype for Business Server. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparare il computer host del listener

Per preparare il computer host, è necessario installare il sistema di Caching in memoria di redis e verificare che nel computer sia presente un certificato valido. Microsoft consiglia di installare l'ultima build stabile di redis 3,0. Statistics Manager versione 2,0 è stato testato con Redis 3.2.100. 
  
1. Scaricare Redis dal sito seguente: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    I programmi di installazione non firmati possono essere scaricati da[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Se necessario, i file binari firmati sono disponibili tramite i gestori di pacchetti più diffusi: [NuGet](https://www.nuget.org/packages/Redis-64/) e [choclatey](https://chocolatey.org/packages/redis-64).
    
   - Eseguire il file MSI fornito e seguire le istruzioni.
    
   - Non selezionare la casella di controllo per aggiungere una regola del firewall.
    
2. Il servizio listener richiede un certificato. Microsoft consiglia vivamente di avere un certificato firmato da un'autorità di certificazione attendibile. 
    
    Se si vuole usare un certificato autofirmato, ad esempio per scopi di test in un laboratorio, vedere [creare un certificato autofirmato](deploy.md#BKMK_SelfCert).
    
    Tieni presente che l'agente usa la verifica dell'identificazione personale del certificato anziché la verifica della catena. La convalida del certificato non sarà completa perché è possibile usare certificati autofirmati.
    
### <a name="install-the-listener-service"></a>Installare il servizio listener

Installare il servizio listener nel computer host eseguendo StatsManPerfAgentListener. msi e specificando quanto segue:
  
1. Esaminare il contratto di licenza e, se si è d'accordo, selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **Avanti**. 
    
2. Nella pagina successiva specificare le informazioni seguenti:
    
   - **Password del servizio:** Questa è la password che gli agenti remoti useranno per eseguire l'autenticazione nel servizio listener.
    
   - **Porta servizio:** Questo è il numero di porta HTTPS che il listener userà per comunicare con gli agenti. Durante l'installazione, questa porta sarà consentita tramite il firewall locale, verrà creato un ACL URL e verrà associato un certificato SSL alla porta. Il valore predefinito è 8443.
    
   - **Identificazione personale del certificato:** Questa è l'identificazione personale del certificato che il listener userà per crittografare il protocollo HTTPS. Il servizio di rete deve avere accesso in lettura alla chiave privata.
    
     Fare clic sul pulsante **Seleziona..** . per scegliere l'identificazione personale.
    
     È possibile trovare l'identificazione personale del certificato usando Gestione certificati o usando il comando di PowerShell seguente:
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Installare dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarlo dall'impostazione predefinita usando il pulsante **Sfoglia...** .
    
   - **Directory AppData:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarlo dall'impostazione predefinita. Non verrà eliminata durante la disinstallazione.
    
3. Fare clic su **Installa**.
    
Per convalidare l'installazione, eseguire la procedura seguente:
  
1. Aprire un browser e passare ahttps://localhost:\<service-port\>/healthcheck/
    
    Per impostazione predefinita, la porta del servizio è 8443 (a meno che non sia stata specificata un'altra porta).
    
2. Per assicurarsi che il listener sia installato correttamente, cercare le operazioni seguenti:
    
   - Se viene visualizzata la pagina Healthcheck, l'installazione del listener ha avuto esito positivo.
    
   - Se il valore di KnownServerCount è 1 o superiore, viene stabilita la connessione a Redis.
    
   - Dopo aver aspettato qualche minuto e dopo aver installato almeno un agente, verificare che il contatore ValuesWritten sia in incremento.
    
### <a name="install-the-website"></a>Installare il sito Web

Installare il sito Web nel computer host eseguendo il StatsManWebSite. msi (incluso in [Skype for Business Server, Real-Time Statistics Manager (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) e specificando quanto segue:
  
1. Esaminare il contratto di licenza e, se si è d'accordo, selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **Avanti**. 
    
2. Nella pagina successiva specificare le informazioni seguenti:
    
   - **Porta servizio:** Questo è il numero di porta su cui verrà ascoltato il sito Web. È possibile modificarla in un secondo momento usando il binding di gestione IIS. Durante l'installazione, questa porta sarà consentita tramite il firewall locale.
    
   - **Installare dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarlo dall'impostazione predefinita usando il pulsante **Sfoglia...** .
    
   - **Directory AppData:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarlo dall'impostazione predefinita. Non verrà eliminata durante la disinstallazione.
    
3. Fare clic su **Installa**.
    
Per visualizzare il sito Web, aprire un browser e passare a: http://localhostWebPort\>/.
  
Per visualizzare solo le informazioni sull'integrità, aprire un browser e passare a http://localhost:\<webport\>/healthcheck/:.
  
Per impostazione predefinita, il numero della porta Web è 8080. È possibile modificare il binding della porta del sito Web usando Gestione IIS.
  
Il programma di installazione Web aggiunge un gruppo di sicurezza locale, denominato StatsManWebSiteUsers. È possibile aggiungere account a questo gruppo di sicurezza per concedere l'accesso al sito Web. 
  
### <a name="install-the-agents"></a>Installare gli agenti

Installare un agente in ogni server Skype for business che si vuole monitorare eseguendo StatsManPerfAgent. msi e specificando quanto segue:
  
1. Esaminare il contratto di licenza e, se si è d'accordo, selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **Avanti**. 
    
2. Nella pagina successiva specificare le informazioni seguenti:
    
   - **Password del servizio:** Questa è la password che l'agente remoto userà per eseguire l'autenticazione nel servizio listener.
    
   - **URI del servizio:** Questo è l'URI in cui risiede il listener. Dovrebbe usare il https://name:port formato.
    
     Puoi usare un nome NETBIOS o un FQDN. È possibile usare il nome specificato anche come **oggetto** o **nomi alternativi oggetto** del certificato nel servizio listener, ma questo non è un requisito.
    
   - **Identificazione personale del servizio:** Questa è l'identificazione personale del certificato SSL usato dal listener. L'agente utilizzerà questa identificazione personale per eseguire l'autenticazione nel listener. (Non eseguirà la convalida completa dei certificati perché è possibile usare certificati autofirmati).
    
   - **Installare dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarlo dall'impostazione predefinita usando il pulsante **Sfoglia...** .
    
   - **Directory AppData:** Questa è la directory in cui verranno archiviati la cartella Logs e il file txt password crittografato. Potrebbe essere necessario modificarlo dall'impostazione predefinita. Non verrà eliminata durante la disinstallazione.
    
3. Fare clic su **Installa**.
    
Se si sta installando un agente in numerosi computer, è probabile che si voglia eseguire questa operazione in modalità automatica. Ad esempio: 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importare la topologia
<a name="BKMK_ImportTopology"> </a>

Dopo aver installato ed eseguito Gestione statistiche, è necessario importare la topologia di Skype for Business Server in modo che Statistics Manager conosca il sito, il pool e il ruolo di ogni server. Per importare la topologia di Skype for Business Server, puoi usare il cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) per recuperare informazioni su ogni pool in uso nell'organizzazione e quindi importare queste informazioni in gestione statistiche.
  
Per importare la topologia di Skype for Business Server, eseguire le operazioni seguenti:
  
1. In un host che include i cmdlet di PowerShell per Skype for Business Server:
    
    un. Eseguire il comando seguente: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copiare il file "mypoolinfo. xml" nel server in cui viene eseguito il listener.
    
2. Nell'host che esegue il listener:
    
   un. Eseguire PowerShell.
    
   b. Passare alla directory in cui è installato il listener. Il valore predefinito è: 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Per verificare quali server vengono aggiunti e aggiornati, eseguire il comando seguente:
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Il comando seguente consente di visualizzare tutte le opzioni:
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Per visualizzare le informazioni sul server attualmente importato, eseguire lo script seguente: 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

Se si vuole monitorare i server non presenti nella topologia di Skype for Business Server, ad esempio un server di Exchange, è possibile eseguire un'importazione a server singolo nell'host che esegue il listener. Per eseguire un'importazione a server singolo, eseguire le operazioni seguenti:
  
1. Passare alla directory in cui è installato il listener. Il valore predefinito è: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Eseguire il comando seguente:
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Risolvere i problemi di distribuzione
<a name="BKMK_Troubleshoot"> </a>

Se un agente non viene avviato, verificare quanto segue: 
  
- L'agente è registrato in Statistics Manager?
    
1. Verificare di aver seguito le istruzioni per l'importazione della topologia. Vedere [importare la topologia](deploy.md#BKMK_ImportTopology).
    
2. Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi di un cluster SQL AlwaysOn, sarà necessario aggiungere manualmente l'agente seguendo le istruzioni in [importare la topologia](deploy.md#BKMK_ImportTopology).
    
- L'agente può contattare l'ascoltatore?
    
1. Verificare che il servizio listener sia in funzione. 
    
    Se non è in corso, verificare che Redis sia in funzione e quindi provare a riavviare il listener.
    
2. Verificare che la porta sia aperta al servizio listener e che il computer dell'agente possa comunicare con la porta.
    
- Per assicurarsi che gestione statistiche raccolga dati, è possibile controllare il file CSV come indicato di seguito. 
    
    Il comando seguente recupera i nomi di archiviazione dei contatori: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Il comando successivo recupera i valori per i contatori specificati: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Per informazioni su tutti gli eventi che potrebbero essere visualizzati nel registro eventi applicazione, vedere [risoluzione dei problemi relativi a gestione statistiche per Skype for Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Creare un certificato autofirmato
<a name="BKMK_SelfCert"> </a>

Microsoft consiglia vivamente di usare un certificato firmato da un'autorità di certificazione attendibile. Se invece si vuole usare un certificato autofirmato per scopi di test, eseguire le operazioni seguenti: 
  
1. Da una console di PowerShell durante l'accesso come amministratore, digitare quanto segue:
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Digitare `certlm.msc`. Verrà aperto il gestore di certificati per il computer locale.
    
3. Passare a **personale**e quindi aprire **certificati**.
    
4. Fai clic con il pulsante destro del mouse su **StatsManListener\>-tutte le attività-\>Gestisci chiavi private..** .
    
5. Fare clic su **Aggiungi**.
    
6. Nella casella **immettere i nomi degli oggetti da selezionare** Digitare quanto segue: servizio di rete
    
7. Fare clic su **OK**.
    
8. In **controllo completo**deselezionare la casella di controllo **Consenti** . (È necessario solo l'accesso in lettura).
    
9. Fare clic su **OK**.
    
## <a name="for-more-information"></a>Per altre informazioni
<a name="BKMK_SelfCert"> </a>

Per altre informazioni, vedere quanto segue:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
    
- [Risoluzione dei problemi relativi a gestione statistiche per Skype for Business Server](troubleshoot.md) ß
