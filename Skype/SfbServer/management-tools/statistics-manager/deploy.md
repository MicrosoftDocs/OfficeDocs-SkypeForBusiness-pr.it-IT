---
title: Distribuire il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675988"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Distribuire il gestore delle statistiche per Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni su come distribuire Statistics Manager per Skype for Business Server.

 Statistics Manager per Skype for Business Server è uno strumento potente che consente di visualizzare Skype for Business Server dati sull'integrità e sulle prestazioni in tempo reale. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare immediatamente i risultati nel sito Web di Statistics Manager.

Prima di provare a installare Statistics Manager, assicurarsi di avere familiarità con i requisiti software, di rete e hardware. Per altre informazioni, vedere [Pianificare Gestione statistiche per Skype for Business Server](plan.md).

> [!NOTE]
> Se si esegue l'aggiornamento da una versione precedente di Gestione statistiche, vedere [Gestione statistiche di aggiornamento per Skype for Business Server](upgrade.md).

> [!NOTE]
> Il sito Web di Statistics Manager è stato testato e funziona correttamente in Internet Explorer 11+, Edge 20.10240+ e Chrome 46+ (versione evergreen corrente).

È possibile scaricare Statistics Manager all'indirizzo [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).

In questa sezione sono contenute le seguenti sezioni:

- [Distribuire Statistics Manager](deploy.md#BKMK_Deploy)

- [Risolvere i problemi di distribuzione](deploy.md#BKMK_Troubleshoot)

- [Creare un certificato autofirma-](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>Distribuire Statistics Manager
<a name="BKMK_Deploy"> </a>

Per distribuire Statistics Manager, seguire questa procedura:

1. Preparare il computer host listener installando il sistema di memorizzazione nella cache in memoria Redis e assicurandosi di aver installato i certificati appropriati.

2. Installare il servizio Listener nel computer host.

3. Installare il sito Web nel computer host.

4. Installare un agente in ogni Skype for Business Server computer da monitorare.

5. Importare la topologia per i server da monitorare.

> [!NOTE]
> Redis, il servizio Listener e il sito Web devono essere tutti installati nello stesso computer host. Assicurarsi che nel computer host non sia installato Skype for Business Server.

### <a name="prepare-the-listener-host-machine"></a>Preparare il computer host del listener

Per preparare il computer host, è necessario installare il sistema di memorizzazione nella cache in memoria di Redis e assicurarsi che nel computer sia presente un certificato valido. Microsoft consiglia di installare la build stabile più recente di Redis 3.0. Statistics Manager versione 2.0 è stato testato con Redis 3.2.100.

1. Scaricare Redis dal sito seguente: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).

    I programmi di installazione non firmati possono essere scaricati da [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    I file binari firmati sono disponibili tramite i più diffusi gestori di pacchetti: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).

   - Eseguire il file msi specificato e seguire le istruzioni.

   - Non selezionare la casella per aggiungere una regola del firewall.

2. Il servizio Listener richiede un certificato. Microsoft consiglia vivamente di avere un certificato firmato da un'autorità di certificazione attendibile.

    Se si vuole usare un certificato autofirma, ad esempio a scopo di test in un lab, vedere [Creare un certificato autofirma](deploy.md#BKMK_SelfCert).

    L'agente usa la verifica dell'identificazione personale del certificato (anziché la verifica della catena). Non eseguirà la convalida completa del certificato perché è possibile usare certificati autofirmati.

### <a name="install-the-listener-service"></a>Installare il servizio Listener

Installare il servizio Listener nel computer host eseguendo il StatsManPerfAgentListener.msi e specificando quanto segue:

1. Esaminare il Contratto di licenza e, se si accetta, selezionare **Accetto le condizioni nel contratto di licenza** e quindi fare clic su **Avanti**.

2. Nella pagina successiva specificare le informazioni seguenti:

   - **Password del servizio:** Questa password viene usata dagli agenti remoti per eseguire l'autenticazione nel servizio listener.

   - **Porta del servizio:** Questo numero di porta HTTPS viene usato dal listener per comunicare con gli agenti. Durante l'installazione, questa porta sarà consentita tramite il firewall locale, verrà creato un ACL URL e verrà associato un certificato SSL a questa porta. Il valore predefinito è 8443.

   - **Identificazione personale certificato:** Questo certificato viene usato dal listener per crittografare il protocollo HTTPS. Il servizio di rete deve avere accesso in lettura alla chiave privata.

     Fare clic sul pulsante **Seleziona...** per scegliere l'identificazione personale.

     È possibile trovare l'identificazione personale del certificato usando Gestione certificati o il comando di PowerShell seguente:

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **Installare Dir:** Questa directory è la posizione in cui verranno installati i file binari. È possibile modificarlo rispetto all'impostazione predefinita usando il pulsante **Sfoglia** .

   - **AppData Dir:** Questa directory è la posizione in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarlo rispetto all'impostazione predefinita. Non verrà eliminato durante la disinstallazione.

3. Fare clic su **Installa**.

Per convalidare l'installazione, seguire questa procedura:

1. Aprire un browser e passare a `https://localhost:<service-port>/healthcheck/`

    Per impostazione predefinita, la porta del servizio è 8443 (a meno che non sia stata specificata un'altra porta).

2. Per assicurarsi che il listener sia installato correttamente, cercare quanto segue:

   - Se viene visualizzata la pagina controllo integrità, l'installazione del listener ha avuto esito positivo.

   - Se KnownServerCount è 1 o superiore, viene stabilita la connessione a Redis.

   - Dopo aver atteso alcuni minuti e dopo aver installato almeno un agente, verificare che il contatore ValuesWritten stia incrementando.

### <a name="install-the-website"></a>Installare il sito Web

Installare il sito Web nel computer host eseguendo il StatsManWebSite.msi (incluso con [Skype for Business Server, Real-Time Statistics Manager (64 bit):](https://www.microsoft.com/download/details.aspx?id=57518)Install the Website on the host machine by running the StatsManWebSite.msi (included with Skype for Business Server, Real-Time Statistics Manager (64 bit)):

1. Esaminare il Contratto di licenza e, se si accetta, selezionare **Accetto le condizioni nel contratto di licenza** e quindi fare clic su **Avanti**.

2. Nella pagina successiva specificare le informazioni seguenti:

   - **Porta del servizio:** Questa porta TCP è la posizione in cui il sito Web sarà in ascolto. È possibile modificarlo in un secondo momento usando l'associazione di gestione IIS. Durante l'installazione, questa porta sarà consentita tramite il firewall locale.

   - **Installare Dir:** Questa directory è la posizione in cui verranno installati i file binari. È possibile modificarlo rispetto all'impostazione predefinita usando il pulsante **Sfoglia** .

   - **AppData Dir:** Questa directory è la posizione in cui verranno archiviati la cartella Logs e altri dati. È possibile modificarlo rispetto all'impostazione predefinita. Non verrà eliminato durante la disinstallazione.

3. Fare clic su **Installa**.

Per visualizzare il sito Web, aprire un browser e passare a: `http://<localhost:webport/>`.

Per visualizzare solo le informazioni sull'integrità, aprire un browser e passare a: `http://localhost:<webport>/healthcheck/`.

Per impostazione predefinita, il numero di porta Web è 8080. È possibile modificare l'associazione di porte del sito Web usando gestione IIS.

Il programma di installazione Web aggiunge un gruppo di sicurezza locale, denominato StatsManWebSiteUsers. È possibile aggiungere account a questo gruppo di sicurezza per concedere l'accesso al sito Web.

### <a name="install-the-agents"></a>Installare gli agenti

Installare un agente in ogni Skype for Business Server che si desidera monitorare eseguendo il StatsManPerfAgent.msi:

1. Esaminare il Contratto di licenza e, se si accetta, selezionare **Accetto le condizioni nel contratto di licenza** e quindi fare clic su **Avanti**.

2. Nella pagina successiva specificare le informazioni seguenti:

   - **Password del servizio:** Questa password viene usata dall'agente remoto per l'autenticazione al servizio listener.

   - **URI del servizio:** Questo URL è il percorso in cui si trova il listener. Usare il `https://name:port` formato .

     È possibile usare un nome NETBIOS o un fqdn. È possibile usare il nome specificato anche come **nome alternativo soggetto** o **soggetto** del certificato nel servizio listener, ma non si tratta di un requisito.

   - **Identificazione personale del servizio:** Questo SS: il certificato viene usato dal listener. L'agente userà questa identificazione personale per eseguire l'autenticazione nel listener. Non eseguirà la convalida completa del certificato perché è possibile usare certificati autofirmati.

   - **Installare Dir:** Questa directory è la posizione in cui verranno installati i file binari. È possibile modificarlo rispetto all'impostazione predefinita usando il pulsante **Sfoglia** .

   - **AppData Dir:** In questa directory verranno archiviati la cartella Logs e il file password.txt crittografato. È possibile modificarlo dall'impostazione predefinita. Non verrà eliminato durante la disinstallazione.

3. Fare clic su **Installa**.

Se si installa un agente in numerosi computer, è probabile che si voglia eseguire questa operazione in modalità automatica. Ad esempio:

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importare la topologia
<a name="BKMK_ImportTopology"> </a>

Dopo l'installazione e l'esecuzione di Statistics Manager, è necessario importare la topologia Skype for Business Server in modo che Gestione statistiche conosca il sito, il pool e il ruolo di ogni server. Per importare la topologia Skype for Business Server, si userà il cmdlet [Get-CsPool](/powershell/module/skype/get-cspool) per recuperare informazioni su ogni pool in uso nell'organizzazione, quindi importare queste informazioni in Gestione statistiche.

Per importare la topologia Skype for Business Server, seguire questa procedura:

1. In un host con i cmdlet di PowerShell Skype for Business Server:

    a. Eseguire il comando qui riportato:

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

3. Per verificare quali server vengono aggiunti e aggiornati, eseguire il comando seguente:

   ```console
   .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Il comando seguente consente di visualizzare tutte le opzioni:

```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed
```

Per visualizzare le informazioni sul server attualmente importate, eseguire lo script seguente:

```powershell
.\Get-StatsManServerInfo.ps1
```

Se si desidera monitorare i server che non si trovano nella topologia Skype for Business Server, ad esempio un Exchange Server, è possibile eseguire un'importazione a server singolo nell'host che esegue il listener. Per eseguire un'importazione a server singolo, seguire questa procedura:

1. Passare alla directory in cui è installato il listener. Il valore predefinito è:

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Eseguire il comando qui riportato:

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Risolvere i problemi di distribuzione
<a name="BKMK_Troubleshoot"> </a>

Se l'avvio di un agente non riesce, verificare la presenza dei problemi seguenti:

- L'agente è registrato in Statistics Manager?

   1. Assicurarsi di aver seguito le istruzioni per l'importazione della topologia. Vedere [Importare la topologia](deploy.md#BKMK_ImportTopology).

   2. Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi di un cluster AlwaysOn SQL, sarà necessario aggiungere manualmente l'agente seguendo le istruzioni riportate in [Importa la topologia](deploy.md#BKMK_ImportTopology).

- L'agente può contattare il listener?

   1. Assicurarsi che il servizio Listener sia in esecuzione.

      Se non è in esecuzione, verificare che Redis sia in esecuzione e quindi provare a riavviare il listener.

   2. Assicurarsi che la porta sia aperta al servizio Listener e che il computer Agent possa comunicare con la porta.

- Per assicurarsi che Gestione statistiche stia raccogliendo dati, è possibile controllare il file CSV come indicato di seguito.

    Il comando seguente recupera i nomi di archiviazione dei contatori:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Il comando successivo recupera i valori per i contatori specificati:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Per informazioni su tutti gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione, vedere [Risolvere i problemi di Gestione statistiche per Skype for Business Server](troubleshoot.md).

## <a name="create-a-self-signed-certificate"></a>Creare un certificato autofirma-
<a name="BKMK_SelfCert"> </a>

Microsoft consiglia vivamente di usare un certificato firmato da un'autorità di certificazione attendibile. Tuttavia, se si vuole usare un certificato autofirma a scopo di test, seguire questa procedura:

1. Da una console di PowerShell mentre si è connessi come amministratore, eseguire il comando seguente:

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Digitare  `certlm.msc`. Verrà aperto Gestione certificati per il computer locale.

3. Passare a **Personale** e quindi aprire **Certificati**.

4. Fare clic con il pulsante destro del mouse su **StatsManListener- \> Tutte le attività- \>Gestisci chiavi private...**

5. Fare clic su **Aggiungi**.

6. Nella casella **Immettere i nomi degli oggetti da selezionare** digitare il testo seguente: Servizio di rete

7. Fare clic su **OK**.

8. In **Controllo completo** deselezionare la casella di controllo **Consenti** . (È necessario solo l'accesso in lettura).

9. Fare clic su **OK**.

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_SelfCert"> </a>

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)

- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)

- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
