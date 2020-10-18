---
title: 'Lync Server 2013: installazione di Lync Server 2013 Monitoring Reports'
description: 'Lync Server 2013: installazione di Lync Server 2013 Monitoring Reports.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573932"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a>Installazione dei rapporti di monitoraggio di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-02-27_

I report di monitoraggio di Microsoft Lync Server 2013 offrono una vasta gamma di informazioni sulla qualità e la quantità delle sessioni di comunicazione che si verificano nella propria organizzazione. Tuttavia, i rapporti di monitoraggio non vengono installati automaticamente quando si installa Lync Server 2013; al contrario, è necessario installare i rapporti di monitoraggio separatamente e solo dopo l'installazione di Lync Server nel computer.

<div>


> [!NOTE]  
> È consigliabile installare i rapporti di monitoraggio sullo stesso computer sul quale è installato il database di monitoraggio, al fine di semplificare il processo di assegnazione delle autorizzazioni di accesso ai rapporti. Se si installano i rapporti di monitoraggio sul computer che ospita l'archivio di monitoraggio, non si avrà bisogno di configurare le autorizzazioni che permettono a un database sul computer di interagire con i servizi di reporting eseguiti su un secondo computer.



</div>

I report di monitoraggio di Lync Server includono oltre 30 rapporti studiati per fornire informazioni dettagliate sulle conferenze, le sessioni di messaggistica istantanea peer-to-peer, le registrazioni degli utenti, l'applicazione Response Group e molto altro ancora. Per la versione 2013, i rapporti di monitoraggio di Lync Server includono una serie di miglioramenti:

  - **Nuovo rapporti di qualità delle chiamate**. Questi nuovi rapporti includono il [rapporto di confronto qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), che confronta la qualità tra i diversi tipi di chiamate, ad esempio tra chiamate cablate e chiamate wireless. e il [rapporto tempo di partecipazione alla conferenza in Lync Server 2013, in](lync-server-2013-conference-join-time-report.md)cui vengono fornite informazioni relative alla quantità di tempo necessaria per consentire agli utenti di partecipare a una conferenza.

  - **Rapporti migliorati per l'analisi e la risoluzione dei problemi delle sessioni video e di condivisione applicazioni.** Il [rapporto riepilogativo sulla qualità multimediale in Lync server 2013](lync-server-2013-media-quality-summary-report.md) consente di analizzare le chiamate di condivisione di applicazioni e video, mentre il [rapporto prestazioni server in Lync Server 2013 descrive in](lync-server-2013-server-performance-report.md) dettaglio le prestazioni dei server che generano tali chiamate. Le metriche per la condivisione di applicazioni e video sono ora segnalate anche dal [rapporto Dettagli sessione peer-to-peer in Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) e il [rapporto Dettagli conferenza in Lync Server 2013](lync-server-2013-conference-detail-report.md).

  - **Prestazioni dei rapporti migliorate**. Il miglioramento include tempi di risposta e recupero dei dati più veloci, nonché uno spostamento più semplice e veloce all'interno dei rapporti.

Nella documentazione relativa ai rapporti di monitoraggio è possibile trovare maggiori informazioni sui singoli rapporti.

<div>


> [!NOTE]  
> È presente un altro nuovo report – sottoreport dettagli chiamata QoE – incluso in Lync Server 2013. Questo rapporto è inteso per un uso interno, e non per un accesso diretto.



</div>

Esistono due modi per installare i rapporti di monitoraggio di Lync Server: è possibile utilizzare la distribuzione guidata di Lync Server oppure è possibile utilizzare uno script di Windows PowerShell incluso nei file di installazione di Lync Server 2013. Indipendentemente dal metodo di installazione selezionato, è necessario assicurarsi di:

  - Possedere i diritti necessari per l'aggiunta di un ruolo del database a un account utente del database di monitoraggio.

  - Detenere il ruolo di gestione del contenuto per SQL Server Reporting Services, che consente di distribuire rapporti a SQL Server Reporting Services.

Per installare i rapporti di monitoraggio attraverso la Distribuzione guidata, eseguire le operazioni seguenti:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **distribuzione guidata di Lync Server**.

2.  Nella Distribuzione guidata fare clic su **Distribuisci rapporti di monitoraggio** per avviare la Distribuzione guidata dei rapporti di monitoraggio.

3.  Nella pagina **Specifica database di monitoraggio** della Distribuzione guidata dei rapporti di monitoraggio, assicurarsi che il nome di dominio completo del computer che ospita l'archivio di monitoraggio compaia nell'elenco a discesa **Database di monitoraggio**. (Se si hanno più archivi di monitoraggio, è necessario selezionare il server appropriato dall'elenco a discesa.) Verificare che nella casella **Istanza di SQL Server Reporting Services (SSRS)** compaia l'istanza di SQL Server Reporting Services (SSRS) appropriata, ad esempio **atl-sql-001.litwareinc.com/archinst**, quindi fare clic su **Avanti**.

4.  Nella casella **nome utente** della pagina **specificare le credenziali** Digitare il nome di dominio e il nome utente dell'account da utilizzare per l'accesso ai rapporti di monitoraggio (ad esempio, **litwareinc \\ kenmyer**). Se non si utilizza questo formato ( \\ nome utente di dominio), si verificherà un errore.
    
    Digitare la password dell'account utente nella casella **Password** e fare clic su **Avanti**. Tenere presente che per questo account non sono necessari diritti speciali. All'account verranno concesse automaticamente le autorizzazioni necessarie per l'accesso e il database al termine dell'installazione.

5.  Nella casella Gruppo utenti della pagina **Specifica gruppo di sola lettura**, inserire il nome di un gruppo di sicurezza al quale sarà garantito l'accesso di sola lettura a SQL Server Reporting Services. Ad esempio, per fornisce un tipo di accesso amministratore di sola lettura ai rapporti, inserire **RTCUniversalReadOnlyAdmins** e fare clic su **Avanti**.

6.  Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.

È inoltre possibile installare i report di monitoraggio da Lync Server Management Shell eseguendo lo script DeployReports.ps1; Questo script di Windows PowerShell può essere trovato nel supporto di installazione di Lync Server \\ nella \\ cartella Setup ReportingSetup Per installare i rapporti di monitoraggio utilizzando DeployReports.ps1, digitare un comando simile al seguente nel prompt di Management Shell:

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

Nella seguente tabella sono illustrati i parametri utilizzati nel comando precedente:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome del parametro</th>
<th>Obbligatorio</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>Sì</p></td>
<td><p>Account utente (nel formato dominio\nome utente) utilizzato per l'accesso all'archivio di monitoraggio; ad esempio:</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>Affinché lo script venga eseguito correttamente, l'account deve avere le autorizzazioni per SQL Server e SQL Server Reporting Services specificate in precedenza.</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>Sì</p></td>
<td><p>Password dell'account utente utilizzato per l'accesso all'archivio di monitoraggio.</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>No</p></td>
<td><p>Dominio o gruppo di sicurezza locale ai cui membri è fornito l'accesso di sola lettura ai rapporti di monitoraggio. Lo script avrà esito negativo se il gruppo specificato non esiste. Se in seguito si decide di annullare queste autorizzazioni, o di concederle ad altri utenti o gruppi, è possibile farlo attraverso SQL Service Reporting Services Report Manager.</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>No</p></td>
<td><p>Istanza di SQL Server che ospita il Reporting Service. L'istanza di Reporting deve essere specificata attraverso il nome di dominio completo del Report Server, ad esempio:</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>Se il parametro non è incluso nello script, assumerà che il Reporting service è ospitato dalla medesima istanza SQL Server che ospita il database di monitoraggio.</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>No</p></td>
<td><p>Identità del servizio per i database di monitoraggio. Attraverso il seguente comando è possibile restituire le identità dei database di monitoraggio:</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


Dopo l'installazione dei rapporti di monitoraggio, è necessario utilizzare il cmdlet Set-CsReportingConfiguration per configurare l'URL utilizzato per accedere ai rapporti. Questa attività può essere eseguita da Lync Server Management Shell eseguendo il comando di Windows PowerShell seguente. È consigliabile, ma non obbligatorio, utilizzare il protocollo HTTPS quando si configura l'URL dei rapporti:

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

Nel comando precedente, la proprietà ReportingUrl deve essere impostata sull'URL Report Manager utilizzato da SQL Server 2008 R2 Reporting Services. L'URL può essere determinato eseguendo la seguente procedura sul computer in cui è installato SQL Server Reporting Services:

1.  Fare clic sul pulsante Start, scegliere Tutti i programmi, fare clic su Microsoft SQL Server 2008 R2, quindi su Strumenti di configurazione e su Gestione configurazione Reporting Services.

2.  Nella finestra di dialogo Connessione configurazione Reporting Services, assicurarsi che il nome del computer per i Reporting Services compaia nella casella Nome server. Selezionare l'istanza SQL Server dall'elenco a discesa Istanza Server Report, quindi fare clic su Connetti.

3.  In Gestione configurazione Reporting Services, fare clic su URL Report Manager. Nel riquadro dovrebbero comparire uno o più URL, che possono essere utilizzati come URL di Reporting URL, sebbene è consigliabile ancora una volta di utilizzare il protocollo HTTPS per la proprietà ReportingUrl.

Se è stato configurato un database mirror per il database di monitoraggio, è necessario anche associare i rapporti di monitoraggio al database mirror. Per informazioni dettagliate, vedere l'articolo che [associa i report di monitoraggio a un database mirror in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .

</div>

<span> </span>

</div>

</div>

</div>

