---
title: Distribuire il dashboard qualità delle chiamate per Skype for Business Server
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
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Riepilogo: informazioni sul processo di distribuzione per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: 88f484091b68379d390b921235f78ff9a7a1dd08
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751705"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Distribuire il dashboard qualità delle chiamate per Skype for Business Server
 
**Riepilogo:** Informazioni sul processo di distribuzione per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
## <a name="deployment-overview"></a>Panoramica della distribuzione

Call Quality Dashboard (CQD) è costituito da tre componenti principali:
  
- **Archive Database**, in cui i dati QoE (Quality of Experience) vengono replicati e archiviati.
    
- **Cubo**, in cui i dati del database Archive QoE vengono aggregati per un accesso ottimizzato e rapido.
    
- **Portal**, in cui gli utenti possono eseguire query e visualizzare facilmente i dati QoE.
    
![Componenti CQD.](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Il processo di installazione dell'archivio QoE prevede la creazione del database di archiviazione QoE, la distribuzione di una stored procedure di SQL Server che sposterà i dati dal database delle metriche QoE di origine nel database di archiviazione QoE e la configurazione del processo agente di SQL Server per l'esecuzione della stored procedure a intervalli regolari. 
  
La distribuzione del cubo ottiene informazioni dall'utente in cui si trova l'archivio QoE, distribuisce il cubo e configura un processo agente di SQL Server normale che aggiorna il cubo a intervalli regolari.
  
L'installazione del portale crea un database repository in cui viene archiviato il mapping degli utenti CQD ai report/query di ogni utente. Viene quindi impostata un'applicazione Web IIS, ovvero il dashboard in cui gli utenti possono visualizzare un set predefinito di report, nonché personalizzare e creare query personalizzate per visualizzare i dati del cubo. L'installazione del portale crea due applicazioni Web aggiuntive che espongono le API per gli utenti per accedere al repository e al cubo a livello di programmazione. Queste API vengono usate anche internamente dal dashboard.
  

|**Fase**|**Procedura**|**Ruoli e appartenenza a gruppi**|**Documentazione**|
|:-----|:-----|:-----|:-----|
|Installare l'hardware e il software prerequisiti.  <br/> |Decidi la configurazione CQD e scegli un SQL Server da cui eseguire l'installazione.  <br/> |Utente del dominio membro del gruppo Administrators locale  <br/> |"Requisiti di preinstallazione" nella documentazione relativa alla distribuzione.  <br/> |
|Installare CQD.  <br/> |Eseguire il file MSI seguendo il documento di distribuzione.  <br/> |Per eseguire l'installazione, l'account di installazione deve essere un utente di dominio membro del gruppo administrators locale e che abbia accesso in lettura al database delle metriche QoE nel Monitoring Server.  <br/> |Sezioni "Account e passaggi di distribuzione" nella documentazione relativa alla distribuzione.  <br/> |
|Concedere l'accesso utente.  <br/> |Per gestire l'autorizzazione degli utenti per il portale, è consigliabile usare l'autorizzazione URL, introdotta in IIS 7.0. Per ulteriori informazioni, vedere [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Utente del dominio membro del gruppo Administrators locale  <br/> |Sezione Managing User Access for the Portal nella documentazione relativa alla distribuzione.  <br/> |
|Facoltativo: fornire informazioni sul mapping di subnet.  <br/> |Popolare le tabelle di mapping di rete e di compilazione nel database di archiviazione QoE.  <br/> |Account con accesso in scrittura al database di archiviazione QoE.  <br/> |Sezione "Fornitura di informazioni sulla subnet" nella documentazione dell'utente.  <br/> |
   


La distribuzione del dashboard qualità delle chiamate implica la configurazione dell'infrastruttura e l'installazione del software. La procedura seguente descrive il processo.
  
## <a name="deployment-steps"></a>Passaggi di distribuzione

1. Copiare il CallQualityDashboard.msi nel computer in cui deve essere installato il componente del database di archiviazione di CQD (questo è il computer in cui è SQL Server installato). 
    
2. Eseguire il file MSI (Windows verrà richiesto di eseguire con privilegi di amministratore, eseguire questa operazione). 
    
3. Accettare l'EULA.
    
4. Selezionare la cartella di destinazione in cui si trovano i file relativi ai componenti del dashboard qualità chiamata o accettare il percorso predefinito.
    
5. Selezionare tutte le funzionalità.
    
6. Nella pagina Configurazione archivio QoE fornire le informazioni seguenti:
    
   - **QoE Metrics SQL Server: SQL Server** instance name for where the QoE Metrics DB is located (this will be the data source).
    
   - **QoE Archive SQL Server Name:** Campo di sola lettura e fisso al nome di dominio completo del computer locale. Il database di archiviazione può essere installato solo nel computer locale.
    
   - **QoE Archive SQL Server Instance:** Nome dell SQL Server di istanza locale per il quale deve essere creato il database di archiviazione. Per utilizzare un'SQL Server predefinita, lasciare vuoto questo campo. Per utilizzare un'SQL Server denominata, specificare il nome dell'istanza (ad esempio, il nome dopo " \" ).
    
   - **Database di archiviazione QoE:** Per impostazione predefinita, questa opzione è impostata su "Crea nuovo database". Poiché l'aggiornamento del database di archiviazione non è supportato, l'unica circostanza in cui è possibile utilizzare l'opzione "Usa database esistente" è se il database Archive esistente ha lo stesso schema della build da installare.
    
   - **Directory file di database:** Percorso in cui devono essere posizionati i file di database (con estensione mdf e ldf) per il database di archiviazione. Dovrebbe essere in un'unità (HDD2 nella configurazione hardware consigliata) separata dal sistema operativo. Si noti che, poiché i nomi dei file sono corretti nell'installazione, per evitare potenziali conflitti, è consigliabile utilizzare una directory vuota senza file.
    
   - **Usa più partizioni:** Il valore predefinito è "Multiple partition", che richiede l'edizione business intelligence o Enterprise edizione di SQL Server. Per Edizione Standard, selezionare l'opzione "Partizione singola". Tenere presente che le prestazioni di elaborazione del cubo possono essere influenzate se viene utilizzata una singola partizione.
    
     > [!NOTE]
     > La selezione dell'opzione Usa più partizioni non può essere modificata al termine dell'installazione. Per modificarla, la funzionalità Cubo deve essere prima disinstallata e quindi reinstallata utilizzando l'opzione "Cambia" nel Pannello di controllo. 
  
   - **Directory dei file di partizione:** Percorso in cui devono essere posizionate le partizioni per il database di archiviazione QoE. Dovrebbe essere in un'unità (HDD3 nella configurazione hardware consigliata) separata dall'unità del sistema operativo e SQL file di registro del database. Si noti che, poiché i nomi dei file sono corretti nell'installazione, per evitare potenziali conflitti, è consigliabile utilizzare una directory vuota senza file.
    
   - **SQL utente processo agente - Nome utente &amp; Password:** nome e password dell'account del servizio di dominio (mascherati) che verranno utilizzati per eseguire il passaggio "QoE Archive Data" del processo agente di SQL Server (che eseguirà la stored procedure per recuperare i dati dal database delle metriche QoE nel DATABASE di archiviazione, quindi questo account deve disporre dell'accesso in lettura al database delle metriche QoE, come indicato nella sezione Account. Questo account deve inoltre disporre di un account di accesso nell'SQL Server QoE Archive).
    
     > [!NOTE]
     > L'account con cui viene eseguita l'istanza di SQL Server, ad esempio NT SERVICE\MSSQLSERVER, deve disporre dell'accesso/autorizzazione alle directory indicate in precedenza per l'esito positivo dell'installazione. Per informazioni dettagliate, vedere [Configure File System Permissions for motore di database Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. Facendo clic su Avanti, il programma di installazione eseguirà i controlli prerequisiti e comunichi se si verificano problemi. Quando vengono superi tutti i controlli dei prerequisiti, il programma di installazione passerà alla pagina Configurazione cubo. 
    
    > [!NOTE]
    > Se il programma di installazione visualizza un messaggio di avviso che indica che il servizio agente di SQL Server per l'istanza di SQL Server di archiviazione QoE non è attualmente in esecuzione, l'installazione può procedere, ma dopo l'installazione assicurarsi che il servizio agente SQL sia in esecuzione e impostare il tipo di avvio su Automatico in modo che venga eseguito il processo pianificato. 
  
8. Nella pagina Configurazione cubo fornire le informazioni seguenti:
    
   - **QoE Archive SQL Server Name:** Campo di sola lettura e fisso al nome di dominio completo del computer locale. Il cubo può essere installato solo dal computer che dispone del database Archive QoE (nota. Il cubo stesso può essere installato in un computer remoto. Vedi sotto)
    
   - **QoE Archive SQL Server Instance: SQL Server** instance name for where the QoE Archive DB is located. Per specificare un'istanza SQL Server predefinita, lasciare vuoto questo campo. Per specificare un'SQL Server denominata, immettere il nome dell'istanza (ad esempio, il nome dopo " \" ). Se per l'installazione è stato selezionato il componente di archiviazione QoE, questo campo verrà precompilato con il valore specificato nella pagina Configurazione archivio QoE.
    
   - **Cube Analysis Server: SQL Server'istanza** di Analysis Services per la quale deve essere creato il cubo. Può trattarsi di un computer diverso, ma l'utente che installa deve essere membro degli amministratori del server dell'istanza di Analysis Services di SQL Server di destinazione.
    
     > [!NOTE]
     >  Per ulteriori informazioni sulla configurazione delle autorizzazioni di amministratore del server Analysis Services, vedere [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **Usa più partizioni:** Il valore predefinito è "Multiple partition", che richiede l'edizione business intelligence o Enterprise edizione di SQL Server. Per Edizione Standard, selezionare l'opzione "Partizione singola". Tenere presente che le prestazioni di elaborazione dei cubi possono essere influenzate se viene utilizzata la partizione singola .
    
     > [!NOTE]
     >  La selezione dell'opzione Usa più partizioni non può essere modificata al termine dell'installazione. Per modificarla, la funzionalità Cubo deve essere prima disinstallata e quindi reinstallata utilizzando l'opzione "Cambia" nel Pannello di controllo.
  
   - **Cube User - User Name &amp; Password: nome** e password dell'account del servizio di dominio (mascherati) che attiveranno l'elaborazione del cubo. Se per l'installazione è stato selezionato il componente archivio QoE, questo campo verrà precompilato con il valore specificato nella pagina Configurazione archivio per l'utente processo agente di SQL, ma è consigliabile specificare un account di servizio di dominio diverso in modo che il programma di installazione possa concederne il privilegio meno necessario.
    
9. Quando si fa clic su Avanti, verrà eseguito un altro round di convalida e verrà segnalato qualsiasi problema. Al termine della convalida, il programma di installazione verrà visualizzato nella pagina Configurazione portale. 
    
10. Nella pagina Configurazione portale fornire le informazioni seguenti:
    
    - **QoE Archive SQL Server: SQL Server** nome dell'istanza per cui si trova il database di archiviazione QoE. Si noti che, a differenza della pagina Configurazione archivio QoE e della pagina Configurazione cubo, il nome del computer non è fisso e deve essere specificato. Se per l'installazione è stato selezionato il componente di archiviazione QoE, questo campo verrà precompilato con il valore specificato nella pagina Configurazione archivio QoE.
    
    - **Cube Analysis Server: SQL Server** di istanza di Analysis Services per la posizione del cubo. Se è stato selezionato il componente Cubo per l'installazione, questo campo verrà precompilato con il valore specificato nella pagina Configurazione cubo.
    
    - **Repository SQL Server: SQL Server** nome dell'istanza in cui deve essere creato il database repository. Se il nome dell'istanza di SQL Server per cui si trova il database di archiviazione QoE è stato fornito in precedenza nell'installazione (in altri componenti), questo campo verrà precompilato con il nome dell'istanza del database di archiviazione QoE SQL Server. Può trattarsi di qualsiasi SQL Server istanza.
    
    - **Database repository:** Per impostazione predefinita, l'opzione è impostata su "Crea nuovo database". Poiché l'aggiornamento del database repository non è supportato, l'unica circostanza in cui è possibile utilizzare l'opzione "Usa database esistente" è se il database repository esistente ha lo stesso schema della build da installare.
    
    - **Utente pool di app IIS - Nome utente &amp; Password:** account con cui deve essere eseguito il pool di applicazioni IIS. I campi Nome utente e Password saranno disattivati se sono selezionati account di sistema incorporati. Questi campi verranno abilitati solo se nella casella di riepilogo a discesa è selezionato "Altro", in modo che l'utente possa immettere le informazioni sull'account del servizio di dominio.
    
11. Quando si fa clic su Avanti, verrà eseguita la convalida finale per assicurarsi che le istanze di SQL Server siano accessibili utilizzando le credenziali fornite e che IIS sia disponibile nel computer. Al termine della convalida, il programma di installazione procederà con la configurazione. 
    
Al termine del programma di installazione, molto probabilmente il processo SQL Server Agent sarà in corso, eseguendo il caricamento iniziale dei dati QoE e l'elaborazione del cubo. A seconda della quantità di dati in QoE, il portale non avrà ancora i dati disponibili per la visualizzazione. Per verificare lo stato del caricamento dei dati e dell'elaborazione del cubo, passare a  `http://<machinename>/CQD/#/Health` . 
> [!NOTE]
> Si noti che l'URL per il controllo dello stato dell'elaborazione del cubo di download fa distinzione tra maiuscole e minuscole. Se si immette "integrità", l'URL non funzionerà. Devi immettere "Health" alla fine dell'URL con la maiuscola H. 
  
Se è abilitata la modalità di debug, verranno visualizzati messaggi di registro dettagliati. Per abilitare la modalità di debug, passare **a %SYSTEMDRIVE%\Programmi\Skype For Business 2015 CQD\QoEDataService\web.config** e aggiornare la riga seguente in modo che il valore sia impostato su **True**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La pagina principale del portale è accessibile tramite  `http://<machinename>/CQD` . 
## <a name="managing-user-access-for-the-portal"></a>Gestione dell'accesso utente per il portale

Per gestire l'autorizzazione degli utenti per il portale, è consigliabile usare l'autorizzazione URL, introdotta in IIS 7.0. Per ulteriori informazioni sulla sicurezza di IIS, vedere [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Qualsiasi sito Web o applicazione Web eredita l'autorizzazione URL predefinita configurata per l'intero IIS, che in genere è "Consenti tutti gli utenti". Se l'accesso al portale deve essere più restrittivo, gli amministratori possono concedere l'accesso solo al gruppo specifico di utenti modificando le "regole di autorizzazione".
  
![Distribuire qualità delle chiamate - Regole di autorizzazione in IIS.](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> L'icona Regole di autorizzazione non deve essere confusa con "Autorizzazione .NET" nella sezione ASP.NET, che è un meccanismo di autorizzazione diverso. 
  
Gli amministratori devono prima rimuovere la regola ereditata "Consenti tutti gli utenti". In questo modo si impedisce agli utenti non autorizzati di accedere al portale.
  
![Distribuire CQD.](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Successivamente, gli amministratori devono aggiungere nuove regole consenti e concedere a utenti specifici l'autorizzazione per accedere al portale. È consigliabile creare un gruppo locale denominato "CQDPortalUsers" per gestire gli utenti.
  
![Distribuire il dashboard qualità delle chiamate.](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
I dettagli di configurazione vengono archiviati web.config nella directory fisica del portale.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Il passaggio successivo consiste nel configurare il dashboard del CQD. Dopo che gli utenti sono stati autenticati da IIS, devono disporre delle autorizzazioni per i file per la directory CQD per accedere al contenuto del portale Web. È possibile modificare gli elenchi di controllo di accesso tramite la scheda sicurezza delle proprietà della directory CQD per aggiungere singoli utenti o gruppi. Tuttavia, l'approccio consigliato consiste nel lasciare invariate le autorizzazioni per i file. Modificare invece l'impostazione iis per utilizzare il processo di lavoro IIS per accedere alla directory CQD indipendentemente dall'utente autenticato. 
  
> [!IMPORTANT]
> È importante modificare questa impostazione solo per l'applicazione CQD e non per le due applicazioni API: QoEDataService e QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configurazione dell'accesso ai file per CQD (Dashboard)

1. Apri l'editor di configurazione per CQD.
    
     ![Distribuire il dashboard qualità delle chiamate.](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. In Sezione scegliere **system.webServer/serverRuntime**.
    
     ![Distribuire il dashboard qualità delle chiamate.](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Modificare authenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Distribuire il dashboard qualità delle chiamate - Editor di configurazione.](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Fare **clic** su Applica sul lato destro della pagina.
    
## <a name="known-issues"></a>Problemi noti

### <a name="the-cqd-shows-no-data-after-deployment"></a>Il CQD non mostra dati dopo la distribuzione

È possibile che venga visualizzato il seguente errore:

*Impossibile eseguire la query durante l'esecuzione nel cubo. Utilizzare l'editor di query per modificare la query e risolvere eventuali problemi. Assicurarsi inoltre che il cubo sia accessibile.*

Ciò significa che il cubo deve essere elaborato in SQL Server Analysis Services prima di essere utilizzato in CQD. Per risolvere il problema, eseguire la procedura seguente:

1. Aprire SQL Management Studio e selezionare **Analysis Services**.

2. Espandere **l'oggetto QoECube,** selezionare **Metrica QoE,** fare clic con il pulsante destro del mouse e quindi scegliere **Sfoglia.** 

    Se viene restituito un browser vuoto, il cubo non è stato ancora proceduto.

3. Fai clic con il pulsante destro del mouse su **QoE Metric** angain e scegli **Process**.

4. Al termine dell'elaborazione, fare di nuovo clic con il pulsante destro del mouse sull'oggetto e scegliere **Sfoglia** per confermare che nella pagina del browser ora sono visualizzati i dati. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Gli utenti hanno problemi di accesso perché il programma di installazione non riesce a creare le impostazioni corrette in IIS

In rari casi, il programma di installazione non riesce a creare le impostazioni corrette in IIS. La modifica manuale è necessaria per consentire agli utenti di accedere al CQD. Se gli utenti hanno problemi di accesso, attenersi alla seguente procedura:
  
1. Aprire Gestione IIS e passare a Sito Web predefinito.
    
     ![Distribuire il dashboard qualità delle chiamate.](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Fare clic su "Autenticazione". Se le impostazioni "Autenticazione anonima", "Rappresentazione ASP.NET", "Autenticazione form" e "Autenticazione Windows" non corrispondono alle impostazioni illustrate di seguito, modificarle manualmente in modo che corrispondano alle impostazioni seguenti. Tutti gli altri meccanismi di autenticazione devono essere disabilitati.
    
     ![Distribuire il dashboard qualità delle chiamate.](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Per "Windows autenticazione", fai clic su Impostazioni avanzata sul lato destro.
    
     ![Distribuire il dashboard qualità delle chiamate.](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Impostare "Protezione estesa" su Accetta e selezionare la casella "Abilita autenticazione in modalità kernel".
    
     ![Distribuire il dashboard qualità delle chiamate.](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Ripetere i passaggi precedenti per ognuna delle voci "CQD", "QoEDataService" e "QoERepositoryService" sotto "Default Web Site".
    
Per i binding delle porte HTTP e HTTPS il programma di installazione creerà binding di porta sui numeri di porta predefiniti (porta 80 per HTTP e porta 443 per HTTPS). Se nel computer è presente un altro sito Web che utilizza questi binding, si verifica un conflitto e non è possibile prevedere il comportamento di IIS. Il modo migliore per evitare questo problema è assicurarsi che nessun altro sito Web sia mappato alle porte 80 e 443 prima di installare CQD. 
  
Per abilitare SSL/TLS in IIS e forzare gli utenti a connettersi tramite HTTPS sicuro anziché HTTP:
  
1. Configurare Secure Sockets Layer in IIS, vedere [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)). Al termine, sostituire  `http` con `https` .
    
2. Per istruzioni sull'abilitazione di TLS nelle connessioni SQL Server, vedere Come abilitare la crittografia SSL per un'istanza di [SQL Server tramite Microsoft Management Console.](https://support.microsoft.com/kb/316898/)
    
## <a name="cube-sync-fails"></a>Sincronizzazione cubo non riuscita

QoEMetrics può contenere alcuni record non validi in base agli orologi dell'utente finale. Se l'inclinazione temporale è maggiore di 60 anni, l'importazione del cubo avrà esito negativo.
  
 Controlla Min e Max StartTime/EndTime usando le selezioni seguenti. Cercare ed eliminare record in un futuro lontano e lontano, possono essere ignorati e interromperanno i processi di sincronizzazione.
  
- Seleziona MIN(StartTime) FROM CqdPartitionedStreamView
    
- Seleziona MAX(StartTime) FROM CqdPartitionedStreamView
    
- Seleziona MIN(EndTime) FROM CqdPartitionedStreamView
    
- Seleziona MAX(EndTime) FROM CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Attività post-installazione

### <a name="importing-buildings-and-networks"></a>Importazione di edifici e reti

Dopo l'installazione di CQD, eseguire le attività di configurazione seguenti:
  
1. Definire i tipi di edificio (scelta consigliata)
    
2. Definire i tipi di proprietà dell'edificio (scelta consigliata)
    
3. Definire i tipi di rete (scelta consigliata)
    
4. Importare edifici (scelta consigliata)
    
5. Importare subnet (scelta consigliata)
    
### <a name="define-building-types"></a>Definire i tipi di compilazione

I tipi di edificio vengono utilizzati per descrivere le diverse definizioni o tipi di edifici all'interno dell'organizzazione. 
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Esempi
  
- Headquarters
    
- Connessione Office
    
- Joint-venture location
    
  **Sintassi SQL esempio**
  
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
  
### <a name="define-building-ownership-types"></a>Definire i tipi di proprietà dell'edificio

I tipi di proprietà vengono utilizzati per distinguere le risorse di proprietà e le risorse noleggiate.
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Esempi
  
- Contoso Leased non-RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso di proprietà
    
- Filiale noleggiata
    
  **Sintassi SQL esempio**
  
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

I tipi di rete vengono utilizzati per descrivere diversi tipi di reti all'interno dell'organizzazione. In questo modo è possibile filtrare o filtrare tipi di rete specifici.
  
> [!NOTE]
> È consigliabile definire nomi di rete, ma è facoltativo. Se si decide di non definire i nomi di rete, verificare che per ogni voce CqdNetwork il valore BuildingId sia 0. 
  
Esempi
  
- VPN
    
- LAB
    
  **Sintassi SQL esempio**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

I parametri NetworkNameID e NetworkName sono obbligatori, il parametro NetworkType è facoltativo ma consigliato.
  
### <a name="import-buildings"></a>Importare edifici

L'importazione di edifici offre la possibilità di ottenere informazioni dettagliate specifiche sull'edificio (chiamate scarse per ogni edificio su WiFi/Cablato e così via). 
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato. 
  
Prima di importare un nuovo edificio, è necessario che sia già stata identificata una chiave predefinita. A tale scopo, eseguire il comando "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL per identificare il valore corrente e aggiungere 1 al risultato.
  
 **Sintassi SQL esempio**
  
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

I parametri BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId sono obbligatori, gli altri sono facoltativi.
  
### <a name="import-subnets"></a>Importare subnet

L'importazione di edifici offre la possibilità di ottenere informazioni dettagliate specifiche sull'edificio (chiamate scarse per ogni edificio su WiFi/Cablato e così via). 
  
> [!NOTE]
> Questo passaggio è facoltativo, ma consigliato.
  
Importare subnet e mapparle agli edifici importati nell'ultimo passaggio. Se si è deciso di non popolare NetworkName, assicurarsi che ogni voce in questa tabella utilizzi un NetworkNameID di 0. Per ulteriori informazioni sulla SQL e sui parametri per il dashboard qualità delle chiamate, vedere [Use Call Quality Dashboard for Skype for Business Server](./use.md).
  
 **Sintassi SQL esempio**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

I parametri Network e UpdatedDate sono obbligatori, gli altri parametri sono facoltativi.
  
### <a name="optional-bssid"></a>Facoltativo: BSSID

Il popolamento delle informazioni BSSID offre una correlazione del flusso WiFi aggiuntiva in base al controller o alla radio. Si tratta di un'operazione che si aggiunge al filtro in base alla creazione o alla subnet. 
  
 **Sintassi SQL esempio**
  
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

|**Come illustrato in CQD**|**Tabella CQDBssid**|**Input di esempio**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (è necessario utilizzare il formato fformat delimitato)  <br/> |
|Controller  <br/> |Building  <br/> |Aruba AP 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Elaborazione dei dati importati

Per impostazione predefinita, dopo l'importazione dei dati di compilazione/rete, i dati verranno applicati solo ai record generati dopo quel momento. 
  
Per contrassegnare tutti i record precedenti con questi nuovi dati, sarà necessario eseguire la stored procedure CqdUpdateBuilding come illustrato di seguito: 
  
Assegnagli la data del primo record (identifica che usando il comando Select MIN(StartTime) FROM CqdPartitionedStreamView SQL ), un valore EndDate di domani, quindi NULL per gli ultimi due valori.
  
Dopo aver associato i dati ai dati del flusso, il cubo SSIS deve rielaborare tutti i record. Ciò vale anche per l'aggiunta in blocco di dati BSSID/ISP. Verificare che sia selezionata l'opzione "Processo completo".
