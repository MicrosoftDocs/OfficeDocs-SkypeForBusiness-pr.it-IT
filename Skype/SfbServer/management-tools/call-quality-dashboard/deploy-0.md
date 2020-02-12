---
title: Distribuire dashboard qualità chiamata per Skype for Business Server
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
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Riepilogo: informazioni sul processo di distribuzione per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: 3ab7ea5130b33578169505969ee8f43a73a2ac32
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888835"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Distribuire dashboard qualità chiamata per Skype for Business Server
 
**Riepilogo:** Informazioni sul processo di distribuzione di Call Quality dashboard. Call Quality dashboard è uno strumento per Skype for Business Server.
  
## <a name="deployment-overview"></a>Panoramica della distribuzione

Call Quality Dashboard (Call Quality Dashboard) è costituito da tre componenti principali:
  
- **Database di archiviazione**in cui vengono replicati e archiviati i dati di qualità dell'esperienza (QoE).
    
- **Cubo**, in cui i dati del database di archiviazione QoE vengono aggregati per l'accesso rapido e ottimizzato.
    
- **Portal**, in cui gli utenti possono facilmente eseguire query e visualizzare i dati QoE.
    
![Componenti Call Quality dashboard](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Il processo di configurazione per l'archivio QoE include la creazione del database di archiviazione QoE, la distribuzione di una stored procedure di SQL Server che sposterà i dati dal database di metriche QoE di origine nel database di archiviazione QoE e la configurazione del processo di SQL Server Agent per l'esecuzione della stored procedura a intervalli regolari. 
  
La distribuzione del cubo consente di ottenere informazioni dall'utente in cui si trova l'archivio QoE, distribuisce il cubo e configura un processo di SQL Server Agent regolare che aggiornerà il cubo a intervalli regolari.
  
L'installazione del portale crea un database del repository che archivia il mapping degli utenti di Call Quality Dashboard ai report e alle query di ogni utente. Configura quindi un'applicazione Web IIS che è il dashboard in cui gli utenti possono visualizzare un set predefinito di report, nonché personalizzare e creare query personalizzate per visualizzare i dati dal cubo. L'installazione del portale crea due altre applicazioni Web che espongono le API per consentire agli utenti di accedere a livello di codice al repository e al cubo. Queste API vengono usate anche internamente dal dashboard.
  

|**Fase**|**Passaggi**|**Ruoli e appartenenza ai gruppi**|**Documentazione**|
|:-----|:-----|:-----|:-----|
|Installare hardware e software prerequisiti.  <br/> |Decidere la configurazione di Call Quality dashboard e scegliere un server SQL da cui eseguire l'installazione.  <br/> |Utente del dominio che è un membro del gruppo Administrators locale.  <br/> |Sezione "requisiti di pre-installazione" nella documentazione relativa alla distribuzione.  <br/> |
|Installare Call Quality dashboard.  <br/> |Eseguire il file MSI dopo il documento di distribuzione.  <br/> |Per eseguire la configurazione, l'account di installazione deve essere un utente di dominio membro del gruppo Administrators locale e avere accesso in lettura al database delle metriche QoE nel server di monitoraggio.  <br/> |Sezioni "account e passaggi di distribuzione" nella documentazione relativa alla distribuzione.  <br/> |
|Concedere l'accesso degli utenti.  <br/> |Per la gestione dell'autorizzazione dell'utente al portale, è consigliabile usare l'autorizzazione URL, introdotta in IIS 7,0. Per altre informazioni, vedere [concetti relativi all'autorizzazione URL di IIS 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Utente del dominio che è un membro del gruppo Administrators locale.  <br/> |Gestione dell'accesso degli utenti per la sezione Portal nella documentazione relativa alla distribuzione.  <br/> |
|Facoltativo: fornisci informazioni sul mapping della subnet.  <br/> |Popolare le tabelle di mapping di rete e creazione nel database di archivio QoE.  <br/> |Un account con accesso in scrittura al database di archiviazione QoE.  <br/> |Sezione "fornitura di informazioni sulla subnet" nella documentazione dell'utente.  <br/> |
   


La distribuzione di Call Quality dashboard include la configurazione dell'infrastruttura e l'installazione del software. La procedura seguente illustra il processo.
  
## <a name="deployment-steps"></a>Passaggi di distribuzione

1. Copiare il file CallQualityDashboard. msi nel computer in cui è installato il componente database di archiviazione di Call Quality dashboard, ovvero il computer in cui è installato SQL Server. 
    
2. Eseguire il file MSI (Windows richiederà l'esecuzione con privilegi di amministratore). 
    
3. Accettare l'EULA.
    
4. Selezionare la cartella di destinazione in cui verranno individuati i file relativi ai componenti del dashboard qualità chiamata o accetteranno la posizione predefinita.
    
5. Selezionare tutte le caratteristiche.
    
6. Nella pagina Configurazione archivio QoE specificare le informazioni seguenti:
    
   - **Metriche QoE SQL Server:** Nome istanza di SQL Server per la posizione in cui si trova il DB metriche QoE (questa sarà l'origine dati).
    
   - **Nome dell'archivio QoE di SQL Server:** Si tratta di un campo di sola lettura e viene fissato al nome di dominio completo del computer locale. Archivio DB può essere installato solo nel computer locale.
    
   - **Istanza di SQL Server QoE Archive:** Nome di istanza di SQL Server locale in cui deve essere creato l'archivio DB di archiviazione. Per usare un'istanza di SQL Server predefinita, lascia vuoto questo campo. Per usare un'istanza di SQL Server denominata, specificare il nome dell'istanza, ad esempio il nome dopo\"".
    
   - **Database archivio QoE:** Per impostazione predefinita, questa opzione è impostata su "Crea nuovo database". Dato che l'aggiornamento dell'archivio DB non è supportato, l'unica circostanza in cui può essere usata l'opzione "Usa database esistente" è se il database di archivio esistente ha lo stesso schema della build da installare.
    
   - **Directory di file di database:** Percorso in cui devono essere posizionati i file di database (con estensione MDF e ldf) per l'archivio DB. Questo dovrebbe essere su un'unità (HDD2 nella configurazione hardware consigliata) separata dal sistema operativo. Tieni presente che, dato che i nomi dei file sono corretti nell'installazione, per evitare potenziali conflitti, è consigliabile usare una directory vuota senza file.
    
   - **Usare più partizioni:** L'impostazione predefinita è impostata su "più partizioni", che richiede Business Intelligence Edition o Enterprise Edition di SQL Server. Per Standard Edition selezionare l'opzione "singola partizione". Tieni presente che le prestazioni di elaborazione del cubo potrebbero avere un impatto se si usa una singola partizione.
    
     > [!NOTE]
     > L'opzione selezione per l'uso di più partizioni non può essere modificata dopo il completamento dell'installazione. Per modificarla, la caratteristica cubo deve essere prima disinstallata e quindi reinstallata usando l'opzione "cambia" nel pannello di controllo. 
  
   - **Directory di file di partizione:** Percorso in cui devono essere posizionate le partizioni per il database di archiviazione QoE. Questa operazione dovrebbe essere su un'unità (HDD3 nella configurazione hardware consigliata) separata dall'unità OS e dai file di log del database SQL. Tieni presente che, dato che i nomi dei file sono corretti nell'installazione, per evitare potenziali conflitti, è consigliabile usare una directory vuota senza file.
    
   - **Processo agente SQL-password nome &amp; utente:** Nome dell'account del servizio di dominio e password (in maschera) che verranno usati per eseguire il passaggio "dati di archivio QoE" del processo di SQL Server Agent (che eseguirà la stored procedure per recuperare i dati da DB metriche QoE in archivio DB, quindi questo account deve avere accesso in lettura al DB metriche QoE, come indicato nella sezione account. Questo account deve anche avere un account di accesso nell'istanza di SQL Server di archiviazione QoE.
    
     > [!NOTE]
     > L'account in cui è in esecuzione l'istanza di SQL Server, ad esempio NT SERVICE\MSSQLSERVER, deve avere accesso/autorizzazione alle directory indicate in precedenza per avere successo nell'installazione. Per informazioni dettagliate, vedere [configurare le autorizzazioni di file System per l'accesso a motore di database](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. Dopo aver fatto clic su Avanti, il programma di installazione eseguirà i controlli pre-requisiti e riferirà se si verificano problemi. Quando vengono superati tutti i controlli prerequisiti, il programma di installazione passa alla pagina di configurazione del cubo. 
    
    > [!NOTE]
    > Se il programma di installazione mostra un messaggio di avviso che il servizio SQL Server Agent per l'istanza di SQL Server di archiviazione QoE non è attualmente in esecuzione, l'installazione può procedere, ma dopo l'installazione verificare che il servizio agente SQL sia in esecuzione e impostare il tipo di avvio su Automatico in modo che il processo programmato venga eseguito. 
  
8. Nella pagina Configurazione cubo specificare le informazioni seguenti:
    
   - **Nome dell'archivio QoE di SQL Server:** Si tratta di un campo di sola lettura e viene fissato al nome di dominio completo del computer locale. Il cubo può essere installato solo dal computer in cui è presente il database di archiviazione QoE (nota. Il cubo stesso può essere installato in un computer remoto. Vedere di seguito)
    
   - **Istanza di SQL Server QoE Archive:** Nome istanza di SQL Server per la posizione in cui si trova l'archivio QoE DB. Per specificare un'istanza di SQL Server predefinita, lascia vuoto questo campo. Per specificare un'istanza di SQL Server denominata, immettere il nome dell'istanza, ad esempio il nome dopo\"". Se è stato selezionato il componente archivio QoE per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina di configurazione dell'archivio QoE.
    
   - **Server analisi cubo:** Nome dell'istanza del servizio di SQL Server Analysis per la posizione in cui deve essere creato il cubo. Può trattarsi di un computer diverso, ma l'utente che esegue l'installazione deve essere un membro degli amministratori del server dell'istanza di SQL Server Analysis Service di destinazione.
    
     > [!NOTE]
     >  Per altre informazioni sulla configurazione delle autorizzazioni di amministratore del server di Analysis Services, vedere [concedere le autorizzazioni di amministratore del server (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)
  
   - **Usare più partizioni:** L'impostazione predefinita è impostata su "più partizioni", che richiede Business Intelligence Edition o Enterprise Edition di SQL Server. Per Standard Edition selezionare l'opzione "singola partizione". Tieni presente che le prestazioni di elaborazione del cubo potrebbero avere un impatto se si usa una singola partizione.
    
     > [!NOTE]
     >  L'opzione selezione per l'uso di più partizioni non può essere modificata dopo il completamento dell'installazione. Per modificarla, la caratteristica cubo deve essere prima disinstallata e quindi reinstallata usando l'opzione "cambia" nel pannello di controllo.
  
   - **Cubo user-password nome &amp; utente:** Nome dell'account del servizio di dominio e password (mascherato) che attiverà l'elaborazione del cubo. Se il componente archivio QoE è stato selezionato per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina di configurazione dell'archivio per l'utente del processo dell'agente SQL, ma è consigliabile specificare un account del servizio di dominio diverso in modo che il programma di installazione possa concedere l' privilegio minimo richiesto.
    
9. Quando si fa clic su Avanti, verrà eseguito un altro ciclo di convalida e verrà segnalato un problema. Dopo aver completato correttamente la convalida, il programma di installazione passerà alla pagina di configurazione del portale. 
    
10. Nella pagina Configurazione portale, fornisci le informazioni seguenti:
    
    - **Archivio QoE SQL Server:** Nome istanza di SQL Server per la posizione in cui si trova il database di archiviazione QoE. Si noti che, diversamente dalla pagina di configurazione dell'archivio QoE e dalla pagina di configurazione del cubo, il nome del computer non è corretto e deve essere fornito. Se è stato selezionato il componente archivio QoE per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina di configurazione dell'archivio QoE.
    
    - **Server analisi cubo:** Nome dell'istanza del servizio di SQL Server Analysis per il punto in cui si trova il cubo. Se il componente cubo è stato selezionato per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina di configurazione del cubo.
    
    - **Repository SQL Server:** Nome dell'istanza di SQL Server in cui deve essere creato il database del repository. Se il nome dell'istanza di SQL Server per cui si trova il database di archiviazione QoE è stato fornito in precedenza nella configurazione (in altri componenti), questo campo verrà prepopolato con il nome dell'istanza di SQL Server di archiviazione QoE DB. Può essere un'istanza di SQL Server.
    
    - **Database repository:** Per impostazione predefinita, l'opzione è impostata su "Crea nuovo database". Dato che l'aggiornamento del repository DB non è supportato, l'unica circostanza in cui può essere usata l'opzione "Usa database esistente" è se il DB del repository esistente ha lo stesso schema della build da installare.
    
    - **Utente del pool di app IIS- &amp; password nome utente:** Account in cui deve essere eseguito il pool di applicazioni IIS. I campi nome utente e password verranno visualizzati in grigio se sono selezionati account di sistema predefiniti. Questi campi verranno abilitati solo se è selezionata l'opzione "altro" nella casella a discesa in modo che l'utente possa immettere le informazioni sull'account del servizio del dominio.
    
11. Quando si fa clic su Avanti, verrà eseguita l'ultima fase di convalida per verificare che le istanze di SQL Server siano accessibili tramite le credenziali fornite e che IIS sia disponibile nel computer. Dopo aver completato correttamente la convalida, il programma di installazione procederà con la configurazione. 
    
Al termine del programma di installazione, probabilmente il processo di SQL Server Agent sarà in corso, eseguendo il caricamento iniziale dei dati QoE e dell'elaborazione del cubo. A seconda della quantità di dati in QoE, il portale non avrà ancora i dati disponibili per la visualizzazione. Per verificare lo stato del caricamento dei dati e dell'elaborazione dei cubi, Vai `http://<machinename>/CQD/#/Health`a. 
> [!NOTE]
> Tieni presente che l'URL per verificare lo stato dell'elaborazione del cubo di download fa distinzione tra maiuscole e minuscole. Se si immette "integrità" l'URL non funzionerà. È necessario immettere "integrità" alla fine dell'URL con una maiuscola H. 
  
I messaggi di log dettagliati verranno visualizzati se è abilitata la modalità debug. Per abilitare la modalità debug, passa a **%SystemDrive%\Program Skype for Business 2015 CQD\QoEDataService\web.config**e aggiorna la riga seguente in modo che il valore sia impostato su **true**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La pagina principale del portale è accessibile `http://<machinename>/CQD`tramite. 
## <a name="managing-user-access-for-the-portal"></a>Gestione dell'accesso degli utenti per il portale

Per la gestione dell'autorizzazione dell'utente al portale, è consigliabile usare l'autorizzazione URL, introdotta in IIS 7,0. Per altre informazioni sulla sicurezza di IIS, vedere informazioni sull' [autorizzazione dell'URL di iis 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Qualsiasi sito Web o applicazione Web eredita l'autorizzazione URL predefinita configurata per l'intero IIS, che in genere è "Consenti a tutti gli utenti". Se l'accesso al portale deve essere più restrittivo, gli amministratori possono concedere l'accesso solo al gruppo specifico di utenti modificando le "regole di autorizzazione".
  
![Distribuire la qualità delle chiamate-regole di autorizzazione in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> L'icona regole di autorizzazione non deve essere confusa con l'"autorizzazione .NET" nella sezione ASP.NET, che è un meccanismo di autorizzazione diverso. 
  
Gli amministratori devono prima rimuovere la regola ereditata "Consenti a tutti gli utenti". Ciò impedisce agli utenti non autorizzati di accedere al portale.
  
![Distribuire Call Quality dashboard](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Gli amministratori devono quindi aggiungere nuove regole Allow e concedere agli utenti specifici l'autorizzazione per accedere al portale. È consigliabile creare un gruppo locale denominato "CQDPortalUsers" per gestire gli utenti.
  
![Distribuire il dashboard Qualità della chiamata](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
I dettagli della configurazione sono archiviati nel file Web. config situato nella directory fisica del portale.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Il passaggio successivo consiste nel configurare il dashboard della call Quality dashboard. Dopo che gli utenti sono stati autenticati da IIS, dovranno avere le autorizzazioni per i file nella directory Call Quality dashboard per accedere al contenuto del portale Web. È possibile modificare gli ACL tramite la scheda sicurezza delle proprietà della directory Call Quality dashboard per aggiungere singoli utenti o gruppi; Tuttavia, l'approccio consigliato consiste nel non toccare le autorizzazioni per i file. Modificare invece l'impostazione di IIS in modo da usare il processo di lavoro di IIS per accedere alla directory Call Quality dashboard indipendentemente dall'autenticazione dell'utente. 
  
> [!IMPORTANT]
> È importante modificare solo questa impostazione per l'applicazione Call Quality dashboard e non per le due applicazioni API: QoEDataService e QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configurazione dell'accesso ai file per Call Quality Dashboard (Dashboard)

1. Aprire l'editor di configurazione per Call Quality dashboard.
    
     ![Distribuire il dashboard Qualità della chiamata](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. In sezione scegliere **System. webserver/ServerRunTime**.
    
     ![Distribuire il dashboard Qualità della chiamata](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Cambiare authenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Distribuire dashboard qualità chiamata-editor di configurazione](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Fare clic su **applica** sul lato destro della pagina.
    
## <a name="known-issues"></a>Problemi noti

### <a name="the-cqd-shows-no-data-after-deployment"></a>Il Call Quality Dashboard non Visualizza dati dopo la distribuzione

Potrebbe essere visualizzato un messaggio di errore analogo al seguente:

*Non è stato possibile eseguire la query durante l'esecuzione del cubo. Usare l'editor di query per modificare la query e risolvere eventuali problemi. Verificare inoltre che il cubo sia accessibile.*

Questo significa che il cubo deve essere elaborato in SQL Server Analysis Services prima di essere usato in Call Quality dashboard. È possibile risolvere il problema seguendo questa procedura:

1. Aprire SQL Management Studio e selezionare **Analysis Services**.

2. Espandere l'oggetto **QoECube** , selezionare **QoE Metric**, fare clic con il pulsante destro del mouse e scegliere **Sfoglia**. 

    Se questo restituisce un browser vuoto, il cubo non è ancora stato proceduto.

3. Fare clic con il pulsante destro del mouse su **QoE Metric** e scegliere **processo**.

4. Al termine dell'elaborazione, fare di nuovo clic con il pulsante destro del mouse sull'oggetto e scegliere **Sfoglia** per verificare che la pagina del browser mostri ora i dati. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Gli utenti hanno problemi di accesso perché il programma di installazione non riesce a creare le impostazioni corrette in IIS

In rari casi, il programma di installazione non riesce a creare le impostazioni corrette in IIS. È necessaria la modifica manuale per consentire agli utenti di accedere a Call Quality dashboard. Se gli utenti hanno problemi di accesso, seguire questa procedura:
  
1. Aprire Gestione IIS e passare al sito Web predefinito.
    
     ![Distribuire il dashboard Qualità della chiamata](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Fare clic su "autenticazione". Se l'"autenticazione anonima", "rappresentazione ASP.NET", "autenticazione modulo" e "autenticazione di Windows" non corrispondono alle impostazioni visualizzate di seguito, modificarle manualmente in modo che corrispondano alle impostazioni seguenti. Tutti gli altri meccanismi di autenticazione devono essere disabilitati.
    
     ![Distribuire il dashboard Qualità della chiamata](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Per "autenticazione di Windows", fare clic su Impostazioni avanzate sul lato destro.
    
     ![Distribuire il dashboard Qualità della chiamata](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Imposta "protezione estesa" per accettare e selezionare la casella "Abilita autenticazione in modalità kernel".
    
     ![Distribuire il dashboard Qualità della chiamata](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Ripetere i passaggi precedenti per ognuna delle voci "Call Quality Dashboard", "QoEDataService" e "QoERepositoryService" sotto "sito Web predefinito".
    
Per i binding della porta HTTP e HTTPS, il programma di installazione creerà i binding delle porte per i numeri di porta predefiniti (porta 80 per HTTP e la porta 443 per HTTPS). Se nel computer è presente un altro sito Web che usa questi binding, si verificherà un conflitto e non sarà possibile prevedere il comportamento di IIS. Il modo migliore per evitare questo problema è assicurarsi che nessun altro sito Web sia mappato alle porte 80 e 443 prima di installare Call Quality dashboard. 
  
Per abilitare SSL/TLS in IIS e imporre agli utenti di connettersi tramite HTTPS sicuro anziché HTTP:
  
1. Configurare Secure Sockets Layer in IIS, vedere [configurazione di Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx). Una volta terminato, `http` Sostituisci con `https`.
    
2. Per istruzioni sull'abilitazione di TLS nelle connessioni di SQL Server, vedere [come abilitare la crittografia SSL per un'istanza di SQL Server tramite Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>Errore di sincronizzazione del cubo

QoEMetrics può contenere alcuni record non validi basati sugli orologi degli utenti finali. Se l'inclinazione temporale è maggiore di 60 anni, l'importazione del cubo avrà esito negativo.
  
 Selezionare le opzioni min e Max StartTime/EndTime usando le selezioni seguenti. Cercare ed eliminare record in un futuro molto lontano e molto lontano, possono essere ignorati e suddividere i processi di sincronizzazione.
  
- Selezionare MIN (StartTime) da CqdPartitionedStreamView
    
- Selezionare MAX (StartTime) da CqdPartitionedStreamView
    
- Selezionare MIN (EndTime) da CqdPartitionedStreamView
    
- Selezionare MAX (EndTime) da CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Attività di post-installazione

### <a name="importing-buildings-and-networks"></a>Importazione di edifici e reti

Dopo l'installazione di Call Quality dashboard, eseguire le attività di configurazione seguenti:
  
1. Definire i tipi di edificio (scelta consigliata)
    
2. Definire i tipi di proprietà degli edifici (scelta consigliata)
    
3. Definire i tipi di rete (altamente consigliato)
    
4. Importare edifici (scelta consigliata)
    
5. Importare subnet (scelta consigliata)
    
### <a name="define-building-types"></a>Definire i tipi di edificio

I tipi di edificio vengono usati per descrivere le diverse definizioni o i tipi di edifici all'interno dell'organizzazione. 
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Esempi
  
- Sede
    
- Office remoto
    
- Posizione joint-venture
    
  **Sintassi SQL di esempio**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

I parametri BuildingTypeId e BuildingTypeDesc sono obbligatori.
  
### <a name="define-building-ownership-types"></a>Definire i tipi di proprietà degli edifici

I tipi di proprietà vengono usati per distinguere le risorse di proprietà e quelle affittate.
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Esempi
  
- Contoso leased non RE&amp;F
    
- Contoso leased RE&amp;F
    
- Proprietà di contoso
    
- Filiale affittata
    
  **Sintassi SQL di esempio**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

I parametri OwnershipTypeId e OwnershipTypeDesc sono obbligatori. 
  
### <a name="define-network-names"></a>Definire i nomi di rete

I tipi di rete vengono usati per descrivere diversi tipi di reti all'interno dell'organizzazione. In questo modo puoi filtrare i tipi di rete specifici (o filtrare).
  
> [!NOTE]
> È vivamente consigliabile definire i nomi di rete, ma è facoltativo. Se si decide di non definire i nomi di rete, verificare che ogni voce CqdNetwork abbia un BuildingId di 0. 
  
Esempi
  
- VPN
    
- LABORATORIO
    
  **Sintassi SQL di esempio**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

I parametri NetworkNameID e NetworkName sono obbligatori, il parametro NetworkType è facoltativo, ma consigliato.
  
### <a name="import-buildings"></a>Importare edifici

L'importazione di edifici offre la possibilità di creare approfondimenti specifici (chiamate scadenti per ogni edificio su WiFi/Wired e così via). 
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Prima di importare una nuova struttura, è necessario avere già un BuildingKey predefinito identificato. A tale scopo, eseguire il comando SQL "SELECT MAX (BuildingKey) FROM CqdBuilding" per identificare il valore corrente e aggiungere 1 al risultato.
  
 **Sintassi SQL di esempio**
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

I parametri BuildingKey, Buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId sono obbligatori, mentre gli altri parametri sono facoltativi.
  
### <a name="import-subnets"></a>Importare subnet

L'importazione di edifici offre la possibilità di creare approfondimenti specifici (chiamate scadenti per ogni edificio su WiFi/Wired e così via). 
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Importare subnet e mapparle agli edifici importati nell'ultimo passaggio. Se si è deciso di non popolare NetworkName, verificare che ogni voce in questa tabella usi un NetworkNameID di 0.
  
 **Sintassi SQL di esempio**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

I parametri Network e UpdatedDate sono obbligatori, mentre gli altri parametri sono facoltativi.
  
### <a name="optional-bssid"></a>Facoltativo: BSSID

La compilazione di informazioni BSSID offre una correlazione di flusso WiFi aggiuntiva tramite controller o radio. Questa operazione è in aggiunta al filtro per edificio o subnet. 
  
 **Sintassi SQL di esempio**
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**Dettagli CqdBssidTable**

|**Come illustrato in Call Quality dashboard**|**Tabella CQDBssid**|**Input di esempio**|
|:-----|:-----|:-----|
|AP NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (è necessario usare il utilizzare delimitato)  <br/> |
|Controller  <br/> |Predefiniti  <br/> |Aruba AP 7  <br/> |
|Dispositivo  <br/> |ESS  <br/> |Controller1  <br/> |
|Opzione  <br/> |PHY  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Elaborazione dei dati importati

Per impostazione predefinita, dopo aver importato i dati della creazione/rete, l'applicazione si applica solo ai record generati dopo tale momento. 
  
Per contrassegnare tutti i record precedenti con questi nuovi dati, sarà necessario eseguire la stored procedure CqdUpdateBuilding, come illustrato di seguito: 
  
Assegna alla data del primo record (identifica che usando il comando SELECT MIN (StartTime) FROM CqdPartitionedStreamView SQL), una EndDate di domani e quindi NULL per gli ultimi due valori.
  
Quando i dati sono associati ai dati del flusso, il cubo SSIS deve rielaborare tutti i record. Questa operazione si applica anche quando si aggiungono dati BSSID/ISP in blocco. Verificare che "processo completo" sia selezionato.
  

