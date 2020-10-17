---
title: 'Lync Server 2013: installazione di Lync Server 2013 Monitoring Reports'
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
ms.openlocfilehash: ad28507f5b0da1758c2e29b9907bd017f922f692
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498543"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="dc139-102">Installazione dei rapporti di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc139-102">Installing Lync Server 2013 Monitoring Reports</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc139-103">_**Ultimo argomento modificato:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="dc139-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="dc139-104">I report di monitoraggio di Microsoft Lync Server 2013 offrono una vasta gamma di informazioni sulla qualità e la quantità delle sessioni di comunicazione che si verificano nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc139-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="dc139-105">Tuttavia, i rapporti di monitoraggio non vengono installati automaticamente quando si installa Lync Server 2013; al contrario, è necessario installare i rapporti di monitoraggio separatamente e solo dopo l'installazione di Lync Server nel computer.</span><span class="sxs-lookup"><span data-stu-id="dc139-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc139-p102">È consigliabile installare i rapporti di monitoraggio sullo stesso computer sul quale è installato il database di monitoraggio, al fine di semplificare il processo di assegnazione delle autorizzazioni di accesso ai rapporti. Se si installano i rapporti di monitoraggio sul computer che ospita l'archivio di monitoraggio, non si avrà bisogno di configurare le autorizzazioni che permettono a un database sul computer di interagire con i servizi di reporting eseguiti su un secondo computer.</span><span class="sxs-lookup"><span data-stu-id="dc139-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="dc139-108">I report di monitoraggio di Lync Server includono oltre 30 rapporti studiati per fornire informazioni dettagliate sulle conferenze, le sessioni di messaggistica istantanea peer-to-peer, le registrazioni degli utenti, l'applicazione Response Group e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dc139-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="dc139-109">Per la versione 2013, i rapporti di monitoraggio di Lync Server includono una serie di miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="dc139-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="dc139-110">**Nuovo rapporti di qualità delle chiamate**.</span><span class="sxs-lookup"><span data-stu-id="dc139-110">**New voice quality reports**.</span></span> <span data-ttu-id="dc139-111">Questi nuovi rapporti includono il [rapporto di confronto qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), che confronta la qualità tra i diversi tipi di chiamate, ad esempio tra chiamate cablate e chiamate wireless. e il [rapporto tempo di partecipazione alla conferenza in Lync Server 2013, in](lync-server-2013-conference-join-time-report.md)cui vengono fornite informazioni relative alla quantità di tempo necessaria per consentire agli utenti di partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="dc139-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="dc139-112">**Rapporti migliorati per l'analisi e la risoluzione dei problemi delle sessioni video e di condivisione applicazioni.**</span><span class="sxs-lookup"><span data-stu-id="dc139-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="dc139-113">Il [rapporto riepilogativo sulla qualità multimediale in Lync server 2013](lync-server-2013-media-quality-summary-report.md) consente di analizzare le chiamate di condivisione di applicazioni e video, mentre il [rapporto prestazioni server in Lync Server 2013 descrive in](lync-server-2013-server-performance-report.md) dettaglio le prestazioni dei server che generano tali chiamate.</span><span class="sxs-lookup"><span data-stu-id="dc139-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="dc139-114">Le metriche per la condivisione di applicazioni e video sono ora segnalate anche dal [rapporto Dettagli sessione peer-to-peer in Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) e il [rapporto Dettagli conferenza in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="dc139-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="dc139-p106">**Prestazioni dei rapporti migliorate**. Il miglioramento include tempi di risposta e recupero dei dati più veloci, nonché uno spostamento più semplice e veloce all'interno dei rapporti.</span><span class="sxs-lookup"><span data-stu-id="dc139-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="dc139-117">Nella documentazione relativa ai rapporti di monitoraggio è possibile trovare maggiori informazioni sui singoli rapporti.</span><span class="sxs-lookup"><span data-stu-id="dc139-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc139-118">È presente un altro nuovo report – sottoreport dettagli chiamata QoE – incluso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc139-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="dc139-119">Questo rapporto è inteso per un uso interno, e non per un accesso diretto.</span><span class="sxs-lookup"><span data-stu-id="dc139-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="dc139-120">Esistono due modi per installare i rapporti di monitoraggio di Lync Server: è possibile utilizzare la distribuzione guidata di Lync Server oppure è possibile utilizzare uno script di Windows PowerShell incluso nei file di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc139-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="dc139-121">Indipendentemente dal metodo di installazione selezionato, è necessario assicurarsi di:</span><span class="sxs-lookup"><span data-stu-id="dc139-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="dc139-122">Possedere i diritti necessari per l'aggiunta di un ruolo del database a un account utente del database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dc139-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="dc139-p109">Detenere il ruolo di gestione del contenuto per SQL Server Reporting Services, che consente di distribuire rapporti a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dc139-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="dc139-125">Per installare i rapporti di monitoraggio attraverso la Distribuzione guidata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc139-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="dc139-126">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **distribuzione guidata di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dc139-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="dc139-127">Nella Distribuzione guidata fare clic su **Distribuisci rapporti di monitoraggio** per avviare la Distribuzione guidata dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dc139-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="dc139-p110">Nella pagina **Specifica database di monitoraggio** della Distribuzione guidata dei rapporti di monitoraggio, assicurarsi che il nome di dominio completo del computer che ospita l'archivio di monitoraggio compaia nell'elenco a discesa **Database di monitoraggio**. (Se si hanno più archivi di monitoraggio, è necessario selezionare il server appropriato dall'elenco a discesa.) Verificare che nella casella **Istanza di SQL Server Reporting Services (SSRS)** compaia l'istanza di SQL Server Reporting Services (SSRS) appropriata, ad esempio **atl-sql-001.litwareinc.com/archinst**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dc139-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="dc139-130">Nella casella **nome utente** della pagina **specificare le credenziali** Digitare il nome di dominio e il nome utente dell'account da utilizzare per l'accesso ai rapporti di monitoraggio (ad esempio, **litwareinc \\ kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="dc139-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="dc139-131">Se non si utilizza questo formato ( \\ nome utente di dominio), si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="dc139-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="dc139-132">Digitare la password dell'account utente nella casella **Password** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dc139-132">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="dc139-133">Tenere presente che per questo account non sono necessari diritti speciali.</span><span class="sxs-lookup"><span data-stu-id="dc139-133">Note that no special rights are required for this account.</span></span> <span data-ttu-id="dc139-134">All'account verranno concesse automaticamente le autorizzazioni necessarie per l'accesso e il database al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="dc139-134">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="dc139-p113">Nella casella Gruppo utenti della pagina **Specifica gruppo di sola lettura**, inserire il nome di un gruppo di sicurezza al quale sarà garantito l'accesso di sola lettura a SQL Server Reporting Services. Ad esempio, per fornisce un tipo di accesso amministratore di sola lettura ai rapporti, inserire **RTCUniversalReadOnlyAdmins** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dc139-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="dc139-138">Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="dc139-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="dc139-139">È inoltre possibile installare i report di monitoraggio da Lync Server Management Shell eseguendo lo script DeployReports.ps1; Questo script di Windows PowerShell può essere trovato nel supporto di installazione di Lync Server \\ nella \\ cartella Setup ReportingSetup</span><span class="sxs-lookup"><span data-stu-id="dc139-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="dc139-140">Per installare i rapporti di monitoraggio utilizzando DeployReports.ps1, digitare un comando simile al seguente nel prompt di Management Shell:</span><span class="sxs-lookup"><span data-stu-id="dc139-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="dc139-141">Nella seguente tabella sono illustrati i parametri utilizzati nel comando precedente:</span><span class="sxs-lookup"><span data-stu-id="dc139-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc139-142">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="dc139-142">Parameter Name</span></span></th>
<th><span data-ttu-id="dc139-143">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="dc139-143">Required</span></span></th>
<th><span data-ttu-id="dc139-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc139-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc139-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="dc139-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="dc139-146">Sì</span><span class="sxs-lookup"><span data-stu-id="dc139-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc139-147">Account utente (nel formato dominio\nome utente) utilizzato per l'accesso all'archivio di monitoraggio; ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dc139-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="dc139-148">Affinché lo script venga eseguito correttamente, l'account deve avere le autorizzazioni per SQL Server e SQL Server Reporting Services specificate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dc139-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc139-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="dc139-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="dc139-150">Sì</span><span class="sxs-lookup"><span data-stu-id="dc139-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc139-151">Password dell'account utente utilizzato per l'accesso all'archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dc139-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc139-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="dc139-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="dc139-153">No</span><span class="sxs-lookup"><span data-stu-id="dc139-153">No</span></span></p></td>
<td><p><span data-ttu-id="dc139-154">Dominio o gruppo di sicurezza locale ai cui membri è fornito l'accesso di sola lettura ai rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dc139-154">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="dc139-155">Lo script avrà esito negativo se il gruppo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="dc139-155">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="dc139-156">Se in seguito si decide di annullare queste autorizzazioni, o di concederle ad altri utenti o gruppi, è possibile farlo attraverso SQL Service Reporting Services Report Manager.</span><span class="sxs-lookup"><span data-stu-id="dc139-156">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc139-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="dc139-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="dc139-158">No</span><span class="sxs-lookup"><span data-stu-id="dc139-158">No</span></span></p></td>
<td><p><span data-ttu-id="dc139-p116">Istanza di SQL Server che ospita il Reporting Service. L'istanza di Reporting deve essere specificata attraverso il nome di dominio completo del Report Server, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dc139-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="dc139-161">Se il parametro non è incluso nello script, assumerà che il Reporting service è ospitato dalla medesima istanza SQL Server che ospita il database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dc139-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc139-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="dc139-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="dc139-163">No</span><span class="sxs-lookup"><span data-stu-id="dc139-163">No</span></span></p></td>
<td><p><span data-ttu-id="dc139-p117">Identità del servizio per i database di monitoraggio. Attraverso il seguente comando è possibile restituire le identità dei database di monitoraggio:</span><span class="sxs-lookup"><span data-stu-id="dc139-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc139-166">Dopo l'installazione dei rapporti di monitoraggio, è necessario utilizzare il cmdlet Set-CsReportingConfiguration per configurare l'URL utilizzato per accedere ai rapporti.</span><span class="sxs-lookup"><span data-stu-id="dc139-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="dc139-167">Questa attività può essere eseguita da Lync Server Management Shell eseguendo il comando di Windows PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="dc139-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="dc139-168">È consigliabile, ma non obbligatorio, utilizzare il protocollo HTTPS quando si configura l'URL dei rapporti:</span><span class="sxs-lookup"><span data-stu-id="dc139-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="dc139-p119">Nel comando precedente, la proprietà ReportingUrl deve essere impostata sull'URL Report Manager utilizzato da SQL Server 2008 R2 Reporting Services. L'URL può essere determinato eseguendo la seguente procedura sul computer in cui è installato SQL Server Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="dc139-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="dc139-171">Fare clic sul pulsante Start, scegliere Tutti i programmi, fare clic su Microsoft SQL Server 2008 R2, quindi su Strumenti di configurazione e su Gestione configurazione Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dc139-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="dc139-p120">Nella finestra di dialogo Connessione configurazione Reporting Services, assicurarsi che il nome del computer per i Reporting Services compaia nella casella Nome server. Selezionare l'istanza SQL Server dall'elenco a discesa Istanza Server Report, quindi fare clic su Connetti.</span><span class="sxs-lookup"><span data-stu-id="dc139-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="dc139-p121">In Gestione configurazione Reporting Services, fare clic su URL Report Manager. Nel riquadro dovrebbero comparire uno o più URL, che possono essere utilizzati come URL di Reporting URL, sebbene è consigliabile ancora una volta di utilizzare il protocollo HTTPS per la proprietà ReportingUrl.</span><span class="sxs-lookup"><span data-stu-id="dc139-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="dc139-177">Se è stato configurato un database mirror per il database di monitoraggio, è necessario anche associare i rapporti di monitoraggio al database mirror.</span><span class="sxs-lookup"><span data-stu-id="dc139-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="dc139-178">Per informazioni dettagliate, vedere l'articolo che [associa i report di monitoraggio a un database mirror in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .</span><span class="sxs-lookup"><span data-stu-id="dc139-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

