---
title: Installare i rapporti di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Riepilogo: informazioni su come installare un servizio che genererà i rapporti di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 10a98bea4af3511c50a0b2b814f8b44911f3742f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802256"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installare i rapporti di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare un servizio che genererà i rapporti di monitoraggio in Skype for Business Server.
  
I report di monitoraggio di Skype for Business Server offrono una vasta gamma di informazioni sulla qualità e la quantità delle sessioni di comunicazione che si verificano nella propria organizzazione. 
  
## <a name="install-monitoring-reports"></a>Installare report di monitoraggio

I rapporti di monitoraggio non vengono installati automaticamente quando si installa Skype for Business Server; al contrario, è necessario installare i rapporti di monitoraggio separatamente e solo dopo l'installazione di Skype for Business Server nel computer.
  
> [!NOTE]
> È consigliabile installare i rapporti di monitoraggio sullo stesso computer sul quale è installato il database di monitoraggio, al fine di semplificare il processo di assegnazione delle autorizzazioni di accesso ai rapporti. Se si installano i rapporti di monitoraggio sul computer che ospita l'archivio di monitoraggio, non si avrà bisogno di configurare le autorizzazioni che permettono a un database sul computer di interagire con i servizi di reporting eseguiti su un secondo computer. 
  
I report di monitoraggio di Skype for Business Server includono oltre 30 rapporti studiati per fornire informazioni dettagliate sulle conferenze, le sessioni di messaggistica istantanea peer-to-peer, le registrazioni degli utenti, l'applicazione Response Group e molto altro ancora. Per la versione 2013, i report di monitoraggio di Skype for Business Server includono una serie di miglioramenti:
  
- **Nuovo rapporti di qualità delle chiamate**. Questi nuovi rapporti includono il [rapporto di confronto qualità multimediale in Skype for Business Server](../../manage/health-and-monitoring/comparison.md), che confronta la qualità tra i diversi tipi di chiamate (ad esempio, tra le chiamate cablate e le chiamate wireless); e il [rapporto tempo di partecipazione alla conferenza in Skype for Business Server, in](../../manage/health-and-monitoring/join-time-report.md)cui vengono fornite informazioni relative alla quantità di tempo necessaria per consentire agli utenti di partecipare a una conferenza. 
    
- **Rapporti migliorati per l'analisi e la risoluzione dei problemi delle sessioni video e di condivisione applicazioni.** il [rapporto riepilogativo sulla qualità multimediale in Skype for Business Server](../../manage/health-and-monitoring/summary.md) consente di analizzare le chiamate di condivisione di applicazioni e video, mentre il [rapporto prestazioni server in Skype for Business Server descrive in](../../manage/health-and-monitoring/server-performance.md) dettaglio le prestazioni dei server che generano tali chiamate. Le metriche per la condivisione di applicazioni e video sono state segnalate anche dal [rapporto Dettagli sessione peer-to-peer in Skype for Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) e nel [rapporto Dettagli conferenza in Skype for Business Server](../../manage/health-and-monitoring/detail-report.md).
    
- **Prestazioni dei rapporti migliorate**. Il miglioramento include tempi di risposta e recupero dei dati più veloci, nonché uno spostamento più semplice e veloce all'interno dei rapporti.
    
Nella documentazione relativa ai rapporti di monitoraggio è possibile trovare maggiori informazioni sui singoli rapporti.
  
> [!NOTE]
> È presente un altro sottorapporto dettagli chiamata QoE del rapporto-incluso in Skype for Business Server. Questo rapporto è inteso per un uso interno, e non per un accesso diretto. 
  
Esistono due modi per installare i rapporti di monitoraggio di Skype for Business Server: è possibile utilizzare la distribuzione guidata di Skype for Business Server oppure è possibile utilizzare uno script di Windows PowerShell incluso nei file di installazione di Skype for Business Server. Indipendentemente dal metodo di installazione selezionato, è necessario assicurarsi di:
  
- Possedere i diritti necessari per l'aggiunta di un ruolo del database a un account utente del database di monitoraggio.
    
- Detenere il ruolo di gestione del contenuto per SQL Server Reporting Services, che consente di distribuire rapporti a SQL Server Reporting Services.
    
Per installare i rapporti di monitoraggio attraverso la Distribuzione guidata, eseguire le operazioni seguenti:
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server** e quindi fare clic su **Skype for Business Server Deployment Wizard**.
    
2. Nella Distribuzione guidata fare clic su **Distribuisci rapporti di monitoraggio** per avviare la Distribuzione guidata dei rapporti di monitoraggio.
    
3. Nella pagina **Specifica database di monitoraggio** della Distribuzione guidata dei rapporti di monitoraggio, assicurarsi che il nome di dominio completo del computer che ospita l'archivio di monitoraggio compaia nell'elenco a discesa **Database di monitoraggio**. (Se si hanno più archivi di monitoraggio, è necessario selezionare il server appropriato dall'elenco a discesa.) Verificare che nella casella **Istanza di SQL Server Reporting Services (SSRS)** compaia l'istanza di SQL Server Reporting Services (SSRS) appropriata, ad esempio **atl-sql-001.litwareinc.com/archinst**, quindi fare clic su **Avanti**.
    
4. Nella casella **Nome utente** della pagina **Specifica credenziali**, digitare il nome di dominio e il nome utente dell'account che si desidera utilizzare per l'accesso ai rapporti di monitoraggio (ad esempio, **litwareinc\kenmyer**). Se non si utilizza questo formato (dominio\nome utente), si verificherà un errore.
    
    Digitare la password dell'account utente nella casella **Password** e fare clic su **Avanti**. Tenere presente che per questo account non sono necessari diritti speciali. All'account verranno concesse automaticamente le autorizzazioni necessarie per l'accesso e il database al termine dell'installazione.
    
5. Nella casella Gruppo utenti della pagina **Specifica gruppo di sola lettura**, inserire il nome di un gruppo di sicurezza al quale sarà garantito l'accesso di sola lettura a SQL Server Reporting Services. Ad esempio, per fornisce un tipo di accesso amministratore di sola lettura ai rapporti, inserire **RTCUniversalReadOnlyAdmins** e fare clic su **Avanti**.
    
6. Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.
    
È inoltre possibile installare i rapporti di monitoraggio da Skype for Business Server Management Shell eseguendo lo script DeployReports.ps1; Questo script di Windows PowerShell può essere trovato nella \<install location\> cartella \Skype for Business Server 2015 \ Deployment\Setup Per installare i rapporti di monitoraggio utilizzando DeployReports.ps1, digitare un comando simile al seguente nel prompt di Management Shell:
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Nella seguente tabella sono illustrati i parametri utilizzati nel comando precedente:
  
|**Nome del parametro**|**Obbligatorio**|**Descrizione**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Sì  <br/> |Account utente (nel formato dominio\nome utente) utilizzato per l'accesso all'archivio di monitoraggio; ad esempio:  <br/> ```-storedUserName "litwareinc\kenmyer"``` Questo account deve disporre delle autorizzazioni di SQL Server e SQL Server Reporting Services precedentemente specificate oppure lo script avrà esito negativo.  <br/> |
|storedPassword  <br/> |Sì  <br/> |Password dell'account utente utilizzato per l'accesso all'archivio di monitoraggio.  <br/> |
|readOnlyGroupName  <br/> |No  <br/> |Dominio o gruppo di sicurezza locale ai cui membri è fornito l'accesso di sola lettura ai rapporti di monitoraggio. Lo script avrà esito negativo se il gruppo specificato non esiste. Se in seguito si decide di annullare queste autorizzazioni, o di concederle ad altri utenti o gruppi, è possibile farlo attraverso SQL Service Reporting Services Report Manager.  <br/> |
|reportSqlServerInstance  <br/> |No  <br/> |Istanza di SQL Server che ospita il Reporting Service. L'istanza di Reporting deve essere specificata attraverso il nome di dominio completo del Report Server, ad esempio:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com``` Se questo parametro non è incluso, lo script presuppone che i servizi di Reporting siano ospitati dalla stessa istanza di SQL Server che ospita il database di monitoraggio.  <br/> |
|monitoringDatabaseId  <br/> |No  <br/> |Identità del servizio per i database di monitoraggio. Attraverso il seguente comando è possibile restituire le identità dei database di monitoraggio:<br/> ```Get-CsService -MonitoringDatabase```|
   
Dopo aver installato i rapporti di monitoraggio, è necessario utilizzare il cmdlet New-CsReportingConfiguration per configurare l'URL utilizzato per accedere a questi rapporti. Questa attività può essere eseguita da Skype for Business Server Management Shell eseguendo il comando di Windows PowerShell seguente. È consigliabile, ma non obbligatorio, utilizzare il protocollo HTTPS quando si configura l'URL dei rapporti:
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Nel comando precedente, la proprietà ReportingUrl deve essere impostata sull'URL Report Manager utilizzato da SQL Server 2008 R2 Reporting Services. L'URL può essere determinato eseguendo la seguente procedura sul computer in cui è installato SQL Server Reporting Services:
  
1. Fare clic sul pulsante Start, scegliere Tutti i programmi, fare clic su Microsoft SQL Server 2008 R2, quindi su Strumenti di configurazione e su Gestione configurazione Reporting Services.
    
2. Nella finestra di dialogo Connessione configurazione Reporting Services, assicurarsi che il nome del computer per i Reporting Services compaia nella casella Nome server. Selezionare l'istanza SQL Server dall'elenco a discesa Istanza Server Report, quindi fare clic su Connetti.
    
3. In Gestione configurazione Reporting Services, fare clic su URL Report Manager. Nel riquadro dovrebbero comparire uno o più URL, che possono essere utilizzati come URL di Reporting URL, sebbene è consigliabile ancora una volta di utilizzare il protocollo HTTPS per la proprietà ReportingUrl.
    
Se è stato configurato un database mirror per il database di monitoraggio, è necessario anche associare i rapporti di monitoraggio al database mirror. Per informazioni dettagliate, vedere l'articolo [associare i rapporti di monitoraggio con un database mirror in Skype for Business Server](monitoring-reports-with-a-mirror-database.md) .
  

