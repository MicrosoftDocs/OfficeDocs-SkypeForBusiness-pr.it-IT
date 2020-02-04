---
title: 'Lync Server 2013: installare i report di monitoraggio di Lync Server 2013'
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
ms.openlocfilehash: b6b5f9832ddc10d3cea46d09aee6b047595db0f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="33dcd-102">Installazione di report di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33dcd-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33dcd-103">_**Argomento Ultima modifica:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="33dcd-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="33dcd-104">I report di monitoraggio di Microsoft Lync Server 2013 consentono di ottenere una vasta gamma di informazioni sulla qualità e la quantità delle sessioni di comunicazione che si svolgono nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="33dcd-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="33dcd-105">Tuttavia, i report di monitoraggio non vengono installati automaticamente durante l'installazione di Lync Server 2013; è invece necessario installare i report di monitoraggio separatamente e solo dopo l'installazione di Lync Server nel computer.</span><span class="sxs-lookup"><span data-stu-id="33dcd-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33dcd-106">È consigliabile installare i report di monitoraggio nello stesso computer in cui è installato il database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="33dcd-106">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed.</span></span> <span data-ttu-id="33dcd-107">In questo modo si semplifica il processo di assegnazione delle autorizzazioni per l'accesso ai report: l'installazione di report di monitoraggio nel computer che ospita l'archivio di monitoraggio significa che non è necessario configurare le autorizzazioni che consentono a un database di interagire in un computer con Reporting Services in uso in un secondo computer.</span><span class="sxs-lookup"><span data-stu-id="33dcd-107">This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="33dcd-108">I report di monitoraggio di Lync Server includono oltre 30 report progettati per ottenere informazioni dettagliate sulle conferenze, le sessioni di messaggistica istantanea peer-to-peer, le registrazioni degli utenti, l'applicazione Response Group e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="33dcd-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="33dcd-109">Per la versione 2013, i report di monitoraggio di Lync Server includono numerosi miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="33dcd-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="33dcd-110">**Nuovi report sulla qualità vocale**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-110">**New voice quality reports**.</span></span> <span data-ttu-id="33dcd-111">Questi nuovi report includono il [report di confronto qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), che confronta la qualità tra i diversi tipi di chiamate, ad esempio tra chiamate cablate e chiamate wireless. e il [report tempo di partecipazione alla conferenza in Lync Server 2013](lync-server-2013-conference-join-time-report.md), che fornisce informazioni sulla quantità di tempo necessario per consentire agli utenti di partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="33dcd-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="33dcd-112">**Report migliorati per l'analisi e la risoluzione dei problemi delle sessioni di condivisione di video e applicazioni.**</span><span class="sxs-lookup"><span data-stu-id="33dcd-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="33dcd-113">Il [report di riepilogo sulla qualità multimediale in Lync server 2013](lync-server-2013-media-quality-summary-report.md) consente di analizzare le chiamate di condivisione di video e applicazioni, mentre il [report prestazioni server in Lync Server 2013 descrive in](lync-server-2013-server-performance-report.md) dettaglio le prestazioni dei server che generano queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="33dcd-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="33dcd-114">Le metriche per la condivisione di video e applicazioni sono ora segnalate anche dal [report Dettagli sessione peer-to-peer in Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) e dal [report Dettagli conferenza in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="33dcd-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="33dcd-115">**Prestazioni migliorate del report**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-115">**Improved report performance**.</span></span> <span data-ttu-id="33dcd-116">Questo include la risposta più rapida e il tempo di recupero dei dati, nonché la navigazione più veloce e più semplice tra i report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-116">This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="33dcd-117">Per altre informazioni sui singoli report, vedere la documentazione di monitoraggio dei report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33dcd-118">È disponibile un nuovo report-sottoreport di dettagli chiamata QoE-incluso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33dcd-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="33dcd-119">Tuttavia, questo report è principalmente per uso interno e non può essere accessibile direttamente.</span><span class="sxs-lookup"><span data-stu-id="33dcd-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="33dcd-120">Esistono due modi per installare i report di monitoraggio di Lync Server: è possibile usare la distribuzione guidata di Lync Server oppure uno script di Windows PowerShell incluso nei file di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33dcd-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="33dcd-121">Indipendentemente dal metodo usato per installare i report, occorre prima di tutto verificare che:</span><span class="sxs-lookup"><span data-stu-id="33dcd-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="33dcd-122">Avere il diritto di aggiungere un ruolo di database a un account utente nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="33dcd-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="33dcd-123">Tenere premuto il ruolo Gestione contenuto in SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="33dcd-123">Hold the Content Manager role in SQL Server Reporting Services.</span></span> <span data-ttu-id="33dcd-124">Questo ruolo offre il diritto di distribuire report in SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="33dcd-124">This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="33dcd-125">Per installare i report di monitoraggio tramite la distribuzione guidata, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="33dcd-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="33dcd-126">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **distribuzione guidata Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="33dcd-127">Nella distribuzione guidata fare clic su **Distribuisci report di monitoraggio** per avviare la procedura guidata Distribuisci monitoraggio report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="33dcd-128">Nella pagina **Specifica database** di monitoraggio della creazione guidata report di monitoraggio verificare che il nome di dominio completo del computer che ospita l'archivio di monitoraggio venga visualizzato nell'elenco a discesa del **database di monitoraggio** .</span><span class="sxs-lookup"><span data-stu-id="33dcd-128">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list.</span></span> <span data-ttu-id="33dcd-129">Se sono presenti più archivi di monitoraggio, sarà necessario selezionare il server appropriato nell'elenco a discesa. Verificare che l'istanza di SQL Server corretta venga visualizzata nella casella **istanza di SQL Server Reporting Services (SSRS)** , ad esempio **ATL-SQL-001.litwareinc.com/ARCHINST**, e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-129">(If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="33dcd-130">Nella casella **nome utente** della pagina **specifica credenziali** Digitare il nome di dominio e il nome utente dell'account da usare quando si accede ai report di monitoraggio, ad esempio **\\litwareinc kenmyer**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="33dcd-131">Se non si usa questo formato (nome utente\\del dominio), si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="33dcd-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="33dcd-132">Digitare la password dell'account utente nella casella **password** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-132">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="33dcd-133">Tieni presente che non sono necessari diritti speciali per questo account.</span><span class="sxs-lookup"><span data-stu-id="33dcd-133">Note that no special rights are required for this account.</span></span> <span data-ttu-id="33dcd-134">All'account verranno concesse automaticamente le autorizzazioni di accesso e database necessarie al completamento della configurazione.</span><span class="sxs-lookup"><span data-stu-id="33dcd-134">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="33dcd-135">Nella pagina **specifica gruppo** di sola lettura immettere il nome di un gruppo di sicurezza a cui verrà concesso l'accesso in sola lettura a SQL Server Reporting Services nella casella gruppo utenti.</span><span class="sxs-lookup"><span data-stu-id="33dcd-135">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box.</span></span> <span data-ttu-id="33dcd-136">Ad esempio, per consentire agli amministratori di sola lettura di accedere ai report, immettere **RTCUniversalReadOnlyAdmins**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-136">For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**.</span></span> <span data-ttu-id="33dcd-137">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-137">Click **Next**.</span></span>

6.  <span data-ttu-id="33dcd-138">Nella pagina **esecuzione dei comandi** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="33dcd-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="33dcd-139">I report di monitoraggio possono essere installati anche da Lync Server Management Shell eseguendo lo script DeployReports. ps1; Questo script di Windows PowerShell si trova nel supporto di installazione di Lync Server nella \\cartella\\Setup ReportingSetup.</span><span class="sxs-lookup"><span data-stu-id="33dcd-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="33dcd-140">Per installare i report di monitoraggio tramite DeployReports. ps1, digitare un comando simile al seguente al prompt di Management Shell:</span><span class="sxs-lookup"><span data-stu-id="33dcd-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="33dcd-141">I parametri usati nel comando precedente sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="33dcd-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33dcd-142">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="33dcd-142">Parameter Name</span></span></th>
<th><span data-ttu-id="33dcd-143">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="33dcd-143">Required</span></span></th>
<th><span data-ttu-id="33dcd-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33dcd-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33dcd-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="33dcd-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="33dcd-146">Sì</span><span class="sxs-lookup"><span data-stu-id="33dcd-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="33dcd-147">Account utente (nel formato dominio\nomeutente) usato per accedere all'archivio di monitoraggio; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="33dcd-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="33dcd-148">Questo account deve disporre delle autorizzazioni specificate in precedenza in SQL Server e SQL Server Reporting Services oppure lo script avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="33dcd-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dcd-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="33dcd-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="33dcd-150">Sì</span><span class="sxs-lookup"><span data-stu-id="33dcd-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="33dcd-151">Password per l'account utente usato per accedere all'archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="33dcd-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dcd-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="33dcd-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="33dcd-153">No</span><span class="sxs-lookup"><span data-stu-id="33dcd-153">No</span></span></p></td>
<td><p><span data-ttu-id="33dcd-154">Dominio o gruppo di sicurezza locale ai cui membri verrà concesso l'accesso in sola lettura ai report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="33dcd-154">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="33dcd-155">Si noti che lo script non riesce se il gruppo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="33dcd-155">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="33dcd-156">Se in seguito si decide di revocare le autorizzazioni o se si decide di concedere ad altri utenti o ad altri gruppi le autorizzazioni di accesso, è possibile usare Gestione report di SQL Service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="33dcd-156">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dcd-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="33dcd-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="33dcd-158">No</span><span class="sxs-lookup"><span data-stu-id="33dcd-158">No</span></span></p></td>
<td><p><span data-ttu-id="33dcd-159">Istanza di SQL Server che ospita il servizio di creazione di report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-159">SQL Server instance that hosts the Reporting Service.</span></span> <span data-ttu-id="33dcd-160">L'istanza di Reporting deve essere specificata usando il nome di dominio completo del server di report. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="33dcd-160">The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="33dcd-161">Se questo parametro non è incluso, lo script presuppone che Reporting Services sia ospitato dalla stessa istanza di SQL Server che ospita il database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="33dcd-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dcd-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="33dcd-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="33dcd-163">No</span><span class="sxs-lookup"><span data-stu-id="33dcd-163">No</span></span></p></td>
<td><p><span data-ttu-id="33dcd-164">Identità del servizio per il database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="33dcd-164">Service Identity for the monitoring database.</span></span> <span data-ttu-id="33dcd-165">Puoi restituire le identità per i database di monitoraggio eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="33dcd-165">You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="33dcd-166">Dopo aver installato i report di monitoraggio, è necessario usare il cmdlet Set-CsReportingConfiguration per configurare l'URL usato per accedere a questi report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="33dcd-167">Questa attività può essere eseguita da Lync Server Management Shell eseguendo il comando di Windows PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="33dcd-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="33dcd-168">Si noti che è consigliabile, ma non necessario, che si usi il protocollo HTTPS quando si configura l'URL della segnalazione:</span><span class="sxs-lookup"><span data-stu-id="33dcd-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="33dcd-169">Nel comando precedente la proprietà ReportingUrl deve essere impostata sull'URL di gestione report utilizzata da SQL Server 2008 R2 Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="33dcd-169">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services.</span></span> <span data-ttu-id="33dcd-170">Per determinare l'URL di gestione report, è possibile completare i passaggi seguenti nel computer in cui è stato installato SQL Server Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="33dcd-170">You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="33dcd-171">Fare clic sul pulsante Start, scegliere tutti i programmi, Microsoft SQL Server 2008 R2, fare clic su strumenti di configurazione e quindi su Gestione configurazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="33dcd-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="33dcd-172">Nella finestra di dialogo connessione configurazione Reporting Services verificare che il nome del computer Reporting Services sia visualizzato nella casella nome server.</span><span class="sxs-lookup"><span data-stu-id="33dcd-172">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box.</span></span> <span data-ttu-id="33dcd-173">Selezionare l'istanza di SQL Server dall'elenco a discesa istanza del server di report e quindi fare clic su Connetti.</span><span class="sxs-lookup"><span data-stu-id="33dcd-173">Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="33dcd-174">In Gestione configurazione di Reporting Services fare clic su URL Gestione report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-174">In Reporting Services Configuration Manager, click Report Manager URL.</span></span> <span data-ttu-id="33dcd-175">Uno o più URL devono essere visualizzati nel riquadro URL Gestione report.</span><span class="sxs-lookup"><span data-stu-id="33dcd-175">One or more URLs should appear in the Report Manager URL pane.</span></span> <span data-ttu-id="33dcd-176">Uno di questi URL può essere usato come URL di report, anche se, di nuovo, è consigliabile che ReportingUrl usi il protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="33dcd-176">Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="33dcd-177">Se è stato configurato un database mirror per il database di monitoraggio, è anche necessario associare i report di monitoraggio al database mirror.</span><span class="sxs-lookup"><span data-stu-id="33dcd-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="33dcd-178">Per informazioni dettagliate, vedere l'articolo che [associa i report di monitoraggio a un database mirror in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .</span><span class="sxs-lookup"><span data-stu-id="33dcd-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

