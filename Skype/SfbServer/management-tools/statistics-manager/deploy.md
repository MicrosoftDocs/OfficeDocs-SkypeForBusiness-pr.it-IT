---
title: Distribuire il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire Gestione statistiche per Skype for Business Server.'
ms.openlocfilehash: 6444f89f43ea4951e186af589f5986e5a3e7bc9e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778156"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Distribuire il gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire Gestione statistiche per Skype for Business Server.
  
 Gestione statistiche per Skype for Business Server è un potente strumento che consente di visualizzare Skype for Business Server dati sull'integrità e sulle prestazioni in tempo reale. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare immediatamente i risultati nel sito Web Gestione statistiche.
  
Prima di tentare di installare Gestione statistiche, assicurarsi di avere familiarità con i requisiti software, di rete e hardware. Per ulteriori informazioni, vedere [Plan for Statistics Manager for Skype for Business Server](plan.md).
  
> [!NOTE]
> Se si esegue l'aggiornamento da una versione precedente di Gestione statistiche, vedere Gestione statistiche [di aggiornamento per Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> Il sito Web Gestione statistiche è stato testato e funziona correttamente in Internet Explorer 11+, Edge 20.10240+ e Chrome 46+ (versione sempreverde corrente). 
  
È possibile trovare Gestione statistiche scaricabile all'indirizzo [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) . 
  
In questa sezione sono contenute le seguenti sezioni:
  
- [Distribuire Gestione statistiche](deploy.md#BKMK_Deploy)
    
- [Risolvere i problemi relativi alla distribuzione](deploy.md#BKMK_Troubleshoot)
    
- [Creare un certificato autofirmato](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Distribuire Gestione statistiche
<a name="BKMK_Deploy"> </a>

Per distribuire Gestione statistiche, attenersi alla seguente procedura:
  
1. Preparare il computer host Listener installando il sistema di memorizzazione nella cache redis in memoria e verificando di aver installato i certificati appropriati.
    
2. Installare il servizio Listener nel computer host. 
    
3. Installare il sito Web nel computer host.
    
4. Installare un agente in Skype for Business Server computer che si desidera monitorare.
    
5. Importare la topologia per i server da monitorare.
    
> [!NOTE]
> Redis, il servizio Listener e il sito Web devono essere tutti installati nello stesso computer host. Assicurarsi che il computer host non abbia Skype for Business Server installato. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparare il computer host listener

Per preparare il computer host, è necessario installare il sistema di memorizzazione nella cache redis in memoria e verificare che nel computer sia presente un certificato valido. Microsoft consiglia di installare la build stabile più recente di Redis 3.0. Statistics Manager versione 2.0 è stato testato con Redis 3.2.100. 
  
1. Scaricare Redis dal sito seguente: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) . 
    
    I programmi di installazione non firmati possono essere scaricati da [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Se necessario, i file binari firmati sono disponibili tramite i gestori di pacchetti più diffusi: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey.](https://chocolatey.org/packages/redis-64)
    
   - Eseguire il file msi fornito e seguire le istruzioni visualizzate.
    
   - Non selezionare la casella per aggiungere una regola del firewall.
    
2. Il servizio Listener richiede un certificato. Microsoft consiglia vivamente di disporre di un certificato firmato da un'autorità di certificazione attendibile. 
    
    Se si desidera utilizzare un certificato autofirmato, ad esempio a scopo di test in un laboratorio, vedere [Creare un certificato autofirmato.](deploy.md#BKMK_SelfCert)
    
    Si noti che l'agente usa la verifica dell'identificazione personale del certificato (anziché la verifica della catena). Non verrà eseguita la convalida completa del certificato perché è possibile utilizzare certificati autofirmati.
    
### <a name="install-the-listener-service"></a>Installare il servizio Listener

Installare il servizio Listener nel computer host eseguendo il StatsManPerfAgentListener.msi e specificando quanto segue:
  
1. Rivedere il Contratto di licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e quindi fare clic su **Avanti.** 
    
2. Nella pagina successiva specificare le informazioni seguenti:
    
   - **Password servizio:** Questa è la password che gli agenti remoti utilizzeranno per eseguire l'autenticazione nel servizio Listener.
    
   - **Porta servizio:** Questo è il numero di porta HTTPS che il listener utilizzerà per comunicare con gli agenti. Durante l'installazione, questa porta verrà consentita attraverso il firewall locale, verrà creato un elenco di controllo di accesso URL e verrà associato un certificato SSL a questa porta. Il valore predefinito è 8443.
    
   - **Identificazione personale certificato:** Questa è l'identificazione personale del certificato che verrà utilizzata dal listener per crittografare il protocollo HTTPS. Il servizio di rete deve disporre dell'accesso in lettura alla chiave privata.
    
     Fare clic **sul pulsante Seleziona...** per scegliere l'identificazione personale.
    
     È possibile trovare l'identificazione personale del certificato utilizzando Gestione certificati o il comando di PowerShell seguente:
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **Installa Dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarla rispetto all'impostazione predefinita utilizzando il **pulsante Sfoglia.**
    
   - **AppData Dir:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarla rispetto all'impostazione predefinita. Non verrà eliminato durante la disinstallazione.
    
3. Fare clic su **Installa**.
    
Per convalidare l'installazione, eseguire la procedura seguente:
  
1. Aprire un browser e passare a https://localhost: \<service-port\> /healthcheck/
    
    Per impostazione predefinita, la porta del servizio è 8443 (a meno che non sia stata specificata un'altra porta).
    
2. Per verificare che listener sia installato correttamente, cercare quanto segue:
    
   - Se viene visualizzata la pagina di controllo dell'integrità, l'installazione del listener ha avuto esito positivo.
    
   - Se KnownServerCount è 1 o superiore, viene stabilita la connessione a Redis.
    
   - Dopo aver atteso alcuni minuti e dopo aver installato almeno un agente, verificare che il contatore ValuesWritten sia in aumento.
    
### <a name="install-the-website"></a>Installare il sito Web

Installare il sito Web nel computer host eseguendo il StatsManWebSite.msi (incluso in [Skype for Business Server, Real-Time Statistics Manager (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)e specificando quanto segue:
  
1. Rivedere il Contratto di licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e quindi fare clic su **Avanti.** 
    
2. Nella pagina successiva specificare le informazioni seguenti:
    
   - **Porta servizio:** Questo è il numero di porta su cui il sito Web sarà in ascolto. È possibile modificarlo in un secondo momento utilizzando il binding di Gestione IIS. Durante l'installazione, questa porta verrà consentita attraverso il firewall locale.
    
   - **Installa Dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarla rispetto all'impostazione predefinita utilizzando il **pulsante Sfoglia.**
    
   - **AppData Dir:** Questa è la directory in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarla rispetto all'impostazione predefinita. Non verrà eliminato durante la disinstallazione.
    
3. Fare clic su **Installa**.
    
Per visualizzare il sito Web, aprire un browser e passare a: http://localhost ,webport \> /.
  
Per visualizzare solo le informazioni sull'integrità, aprire un browser e passare a: http://localhost: \<webport\> /healthcheck/.
  
Per impostazione predefinita, il numero di porta Web è 8080. È possibile modificare il binding di porta del sito Web utilizzando Gestione IIS.
  
Il programma di installazione Web aggiunge un gruppo di sicurezza locale, denominato StatsManWebSiteUsers. È possibile aggiungere account a questo gruppo di sicurezza per concedere l'accesso al sito Web. 
  
### <a name="install-the-agents"></a>Installare gli agenti

Installare un agente in ogni Skype for Business Server che si desidera monitorare eseguendo il StatsManPerfAgent.msi e specificando quanto segue:
  
1. Rivedere il Contratto di licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e quindi fare clic su **Avanti.** 
    
2. Nella pagina successiva specificare le informazioni seguenti:
    
   - **Password servizio:** Questa è la password che l'agente remoto utilizzerà per eseguire l'autenticazione nel servizio Listener.
    
   - **URI servizio:** Questo è l'URI in cui risiede il listener. Deve utilizzare il https://name:port formato.
    
     È possibile utilizzare un nome NETBIOS o un nome di dominio completo. È possibile utilizzare il nome specificato  anche come Subject o **Subject Alternative Names** del certificato nel servizio Listener, ma questo non è un requisito.
    
   - **Identificazione personale servizio:** Questa è l'identificazione personale del certificato SSL utilizzato dal listener. L'agente utilizzerà questa identificazione personale per eseguire l'autenticazione nel listener. Non verrà eseguita la convalida completa del certificato perché è possibile utilizzare certificati autofirmati.
    
   - **Installa Dir:** Questa è la directory in cui verranno installati i file binari. È possibile modificarla rispetto all'impostazione predefinita utilizzando il **pulsante Sfoglia.**
    
   - **AppData Dir:** Questa è la directory in cui verranno archiviati la cartella Logs e il file password.txt crittografato. È possibile modificare l'impostazione predefinita. Non verrà eliminato durante la disinstallazione.
    
3. Fare clic su **Installa**.
    
Se si installa un agente in più computer, è probabile che si desideri eseguire questa operazione in modalità automatica. Ad esempio: 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importare la topologia
<a name="BKMK_ImportTopology"> </a>

Dopo l'installazione e l'esecuzione di Gestione statistiche, è necessario importare la topologia di Skype for Business Server in modo che Gestione statistiche conosca il sito, il pool e il ruolo di ogni server. Per importare la topologia di Skype for Business Server, utilizzare il cmdlet [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) per recuperare le informazioni su ogni pool in uso nell'organizzazione e quindi importare tali informazioni in Gestione statistiche.
  
Per importare la Skype for Business Server, attenersi alla seguente procedura:
  
1. In un host con i cmdlet Skype for Business Server PowerShell:
    
    a. Eseguire il comando seguente: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copiare il file "mypoolinfo.xml" nel server che esegue il listener.
    
2. Nell'host che esegue il listener:
    
   a. Eseguire PowerShell.
    
   b. Passare alla directory in cui è installato listener. Il valore predefinito è: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Per verificare quali server vengono aggiunti e aggiornati, eseguire il comando seguente:
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Il comando seguente consente di visualizzare tutte le opzioni:
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Per visualizzare le informazioni sul server attualmente importato, eseguire lo script seguente: 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

Se si desidera monitorare i server non presenti nella topologia di Skype for Business Server, ad esempio un Exchange Server, è possibile eseguire un'importazione a server singolo nell'host che esegue il listener. Per eseguire un'importazione a server singolo, attenersi alla seguente procedura:
  
1. Passare alla directory in cui è installato listener. Il valore predefinito è: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Eseguire il comando seguente:
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Risolvere i problemi relativi alla distribuzione
<a name="BKMK_Troubleshoot"> </a>

Se l'avvio di un agente non riesce, verificare quanto segue: 
  
- L'agente è registrato in Gestione statistiche?
    
    1. Assicurarsi di aver seguito le istruzioni per l'importazione della topologia. Vedere [Import the topology](deploy.md#BKMK_ImportTopology).
        
    2. Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi in un cluster AlwaysOn di SQL, sarà necessario aggiungere manualmente l'agente seguendo le istruzioni in Importare la [topologia.](deploy.md#BKMK_ImportTopology)
    
- L'agente può contattare il listener?
    
    1. Verificare che il servizio Listener sia in esecuzione. 
        
        Se non è in esecuzione, assicurati che Redis sia in esecuzione e quindi prova a riavviare il listener.
        
    2. Verificare che la porta sia aperta per il servizio Listener e che il computer agente possa comunicare con la porta.
    
- Per assicurarsi che Gestione statistiche raccoglie dati, puoi controllare il file CSV come indicato di seguito. 
    
    Il comando seguente recupera i nomi di archiviazione dei contatori: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Il comando successivo recupera i valori per i contatori specificati: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Per informazioni su tutti gli eventi che è possibile visualizzare nel registro eventi dell'applicazione, vedere [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Creare un certificato autofirmato
<a name="BKMK_SelfCert"> </a>

Microsoft consiglia vivamente di utilizzare un certificato firmato da un'autorità di certificazione attendibile. Tuttavia, se si desidera utilizzare un certificato autofirmato a scopo di test, eseguire le operazioni seguenti: 
  
1. Da una console di PowerShell mentre si è connessi come amministratore, digitare quanto segue:
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Digitare  `certlm.msc` . Verrà aperto Gestione certificati per il computer locale.
    
3. Passare a **Personale** e quindi aprire **Certificati**.
    
4. Fai clic con il pulsante destro del mouse su **StatsManListener- \> Tutte le attività- \> Gestisci chiavi private...**
    
5. Fare clic su **Aggiungi**.
    
6. Nella casella **Immettere i nomi degli oggetti da selezionare** digitare quanto segue: Servizio di rete
    
7. Fare clic su **OK**.
    
8. In **Controllo completo** deselezionare la casella **di** controllo Consenti. È necessario solo l'accesso in lettura.
    
9. Fare clic su **OK**.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_SelfCert"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
    
- [Risolvere i problemi di Gestione statistiche per Skype for Business Server](troubleshoot.md) ß