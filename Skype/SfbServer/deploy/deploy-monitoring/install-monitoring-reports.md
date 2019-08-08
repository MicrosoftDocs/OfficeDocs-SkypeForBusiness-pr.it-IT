---
title: Installare report di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Riepilogo: informazioni su come installare un servizio che genererà report di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 765c7a13b965b8701de6bc70782a9d7a8963a429
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239982"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installare report di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare un servizio che genererà report di monitoraggio in Skype for Business Server.
  
I report di monitoraggio di Skype for Business Server contengono una vasta gamma di informazioni sulla qualità e la quantità delle sessioni di comunicazione che si svolgono nell'organizzazione. 
  
## <a name="install-monitoring-reports"></a>Installare report di monitoraggio

I report di monitoraggio non vengono installati automaticamente durante l'installazione di Skype for Business Server; è invece necessario installare i report di monitoraggio separatamente e solo dopo l'installazione di Skype for Business Server nel computer.
  
> [!NOTE]
> È consigliabile installare i report di monitoraggio nello stesso computer in cui è installato il database di monitoraggio. In questo modo si semplifica il processo di assegnazione delle autorizzazioni per l'accesso ai report: l'installazione di report di monitoraggio nel computer che ospita l'archivio di monitoraggio significa che non è necessario configurare le autorizzazioni che consentono a un database di interagire in un computer con Reporting Services in uso in un secondo computer. 
  
I report di monitoraggio di Skype for Business Server includono più di 30 report progettati per ottenere informazioni dettagliate sulle conferenze, le sessioni di messaggistica istantanea peer-to-peer, le registrazioni degli utenti, l'applicazione Response Group e molto altro ancora. Per la versione 2013, i report di monitoraggio di Skype for Business Server includono una serie di miglioramenti:
  
- **Nuovi report sulla qualità vocale**. Questi nuovi report includono il [report di confronto qualità multimediale in Skype for Business Server](../../manage/health-and-monitoring/comparison.md), che confronta la qualità tra i diversi tipi di chiamate, ad esempio tra chiamate cablate e chiamate wireless. e il [report tempo di partecipazione alla conferenza in Skype for Business Server](../../manage/health-and-monitoring/join-time-report.md), che fornisce informazioni sull'intervallo di tempo necessario per consentire agli utenti di partecipare a una conferenza. 
    
- **Report migliorati per l'analisi e la risoluzione dei problemi delle sessioni di condivisione di video e applicazioni.** il [report di riepilogo qualità multimediale in Skype for Business Server](../../manage/health-and-monitoring/summary.md) consente di analizzare le chiamate di condivisione di video e applicazioni, mentre il [report prestazioni server in Skype for business](../../manage/health-and-monitoring/server-performance.md) server descrive in dettaglio le prestazioni dei server che la generano chiamate. Le metriche per la condivisione di video e applicazioni sono ora segnalate anche dal [report Dettagli sessione peer-to-peer di Skype for Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) e dal [report Dettagli conferenza in Skype for Business Server](../../manage/health-and-monitoring/detail-report.md).
    
- **Prestazioni migliorate del report**. Questo include la risposta più rapida e il tempo di recupero dei dati, nonché la navigazione più veloce e più semplice tra i report.
    
Per altre informazioni sui singoli report, vedere la documentazione di monitoraggio dei report.
  
> [!NOTE]
> C'è un altro report-sottoreport di dettagli chiamata QoE-incluso in Skype for Business Server. Tuttavia, questo report è principalmente per uso interno e non può essere accessibile direttamente. 
  
Esistono due modi per installare i report di monitoraggio di Skype for Business Server: è possibile usare la distribuzione guidata di Skype for Business Server oppure uno script di Windows PowerShell incluso nei file di installazione di Skype for Business Server. Indipendentemente dal metodo usato per installare i report, occorre prima di tutto verificare che:
  
- Avere il diritto di aggiungere un ruolo di database a un account utente nel database di monitoraggio.
    
- Tenere premuto il ruolo Gestione contenuto in SQL Server Reporting Services. Questo ruolo offre il diritto di distribuire report in SQL Server Reporting Services.
    
Per installare i report di monitoraggio tramite la distribuzione guidata, eseguire la procedura seguente:
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi fare clic su **Skype for Business Server Deployment Wizard**.
    
2. Nella distribuzione guidata fare clic su **Distribuisci report di monitoraggio** per avviare la procedura guidata Distribuisci monitoraggio report.
    
3. Nella pagina **Specifica database** di monitoraggio della creazione guidata report di monitoraggio verificare che il nome di dominio completo del computer che ospita l'archivio di monitoraggio venga visualizzato nell'elenco a discesa del **database di monitoraggio** . Se sono presenti più archivi di monitoraggio, sarà necessario selezionare il server appropriato nell'elenco a discesa. Verificare che l'istanza di SQL Server corretta venga visualizzata nella casella **istanza di SQL Server Reporting Services (SSRS)** , ad esempio **ATL-SQL-001.litwareinc.com/ARCHINST**, e quindi fare clic su **Avanti**.
    
4. Nella casella **nome utente** della pagina **specifica credenziali** Digitare il nome di dominio e il nome utente dell'account da usare per l'accesso ai report di monitoraggio, ad esempio **litwareinc\davidegarghentini**. Se non si usa questo formato (dominio\nome utente) si verificherà un errore.
    
    Digitare la password dell'account utente nella casella **password** e quindi fare clic su **Avanti**. Tieni presente che non sono necessari diritti speciali per questo account. All'account verranno concesse automaticamente le autorizzazioni di accesso e database necessarie al completamento della configurazione.
    
5. Nella pagina **specifica gruppo** di sola lettura immettere il nome di un gruppo di sicurezza a cui verrà concesso l'accesso in sola lettura a SQL Server Reporting Services nella casella gruppo utenti. Ad esempio, per consentire agli amministratori di sola lettura di accedere ai report, immettere **RTCUniversalReadOnlyAdmins**. Fare clic su **Avanti**.
    
6. Nella pagina **esecuzione dei comandi** fare clic su **fine**.
    
I report di monitoraggio possono essere installati anche da Skype for Business Server Management Shell eseguendo lo script DeployReports. ps1; Questo script di Windows PowerShell si trova nella cartella \<Install Location\>\Skype for Business Server 2015 \ Deployment\Setup. Per installare i report di monitoraggio tramite DeployReports. ps1, digitare un comando simile al seguente al prompt di Management Shell:
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

I parametri usati nel comando precedente sono descritti nella tabella seguente:
  
|**Nome parametro**|**Richiesto**|**Descrizione**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Sì  <br/> |Account utente (nel formato dominio\nomeutente) usato per accedere all'archivio di monitoraggio; Per esempio:  <br/> ```-storedUserName "litwareinc\kenmyer"```Questo account deve disporre delle autorizzazioni specificate in precedenza in SQL Server e SQL Server Reporting Services oppure lo script avrà esito negativo.  <br/> |
|storedPassword  <br/> |Sì  <br/> |Password per l'account utente usato per accedere all'archivio di monitoraggio.  <br/> |
|readOnlyGroupName  <br/> |No  <br/> |Dominio o gruppo di sicurezza locale ai cui membri verrà concesso l'accesso in sola lettura ai report di monitoraggio. Si noti che lo script non riesce se il gruppo specificato non esiste. Se in seguito si decide di revocare le autorizzazioni o se si decide di concedere ad altri utenti o ad altri gruppi le autorizzazioni di accesso, è possibile usare Gestione report di SQL Service Reporting Services.  <br/> |
|reportSqlServerInstance  <br/> |No  <br/> |Istanza di SQL Server che ospita il servizio di creazione di report. L'istanza di Reporting deve essere specificata usando il nome di dominio completo del server di report. Per esempio:  <br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```Se questo parametro non è incluso, lo script presuppone che Reporting Services sia ospitato dalla stessa istanza di SQL Server che ospita il database di monitoraggio.  <br/> |
|monitoringDatabaseId  <br/> |No  <br/> |Identità del servizio per il database di monitoraggio. Puoi restituire le identità per i database di monitoraggio eseguendo questo comando:  <br/> ```Get-CsService -MonitoringDatabase```|
   
Dopo aver installato i report di monitoraggio, è necessario usare il cmdlet New-CsReportingConfiguration per configurare l'URL usato per accedere a questi report. Questa attività può essere eseguita da Skype for Business Server Management Shell eseguendo il comando di Windows PowerShell seguente. Si noti che è consigliabile, ma non necessario, che si usi il protocollo HTTPS quando si configura l'URL della segnalazione:
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Nel comando precedente la proprietà ReportingUrl deve essere impostata sull'URL di gestione report utilizzata da SQL Server 2008 R2 Reporting Services. Per determinare l'URL di gestione report, è possibile completare i passaggi seguenti nel computer in cui è stato installato SQL Server Reporting Services:
  
1. Fare clic sul pulsante Start, scegliere tutti i programmi, Microsoft SQL Server 2008 R2, fare clic su strumenti di configurazione e quindi su Gestione configurazione di Reporting Services.
    
2. Nella finestra di dialogo connessione configurazione Reporting Services verificare che il nome del computer Reporting Services sia visualizzato nella casella nome server. Selezionare l'istanza di SQL Server dall'elenco a discesa istanza del server di report e quindi fare clic su Connetti.
    
3. In Gestione configurazione di Reporting Services fare clic su URL Gestione report. Uno o più URL devono essere visualizzati nel riquadro URL Gestione report. Uno di questi URL può essere usato come URL di report, anche se, di nuovo, è consigliabile che ReportingUrl usi il protocollo HTTPS.
    
Se è stato configurato un database mirror per il database di monitoraggio, è anche necessario associare i report di monitoraggio al database mirror. Per informazioni dettagliate, vedere l'articolo [associare i report di monitoraggio a un database mirror in Skype for Business Server](monitoring-reports-with-a-mirror-database.md) .
  

