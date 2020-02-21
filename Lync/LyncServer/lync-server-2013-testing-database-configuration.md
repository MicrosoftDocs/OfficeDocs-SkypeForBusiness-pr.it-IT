---
title: 'Lync Server 2013: verifica della configurazione del database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69dea9e2b75125740729f658e1c370838bb5d8bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="5f615-102">Verifica della configurazione del database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f615-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f615-103">_**Ultimo argomento modificato:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="5f615-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f615-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="5f615-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5f615-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="5f615-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f615-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="5f615-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5f615-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f615-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f615-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="5f615-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5f615-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins ed è necessario disporre di privilegi di amministratore su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f615-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="5f615-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="5f615-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="5f615-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5f615-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5f615-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f615-112">Description</span></span>

<span data-ttu-id="5f615-113">Il cmdlet **Test-CsDatabase** consente di verificare la connettività a uno o più database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f615-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="5f615-114">Quando viene eseguito, il cmdlet **Test-CsDatabase** legge la topologia di Lync Server, tenta di connettersi a database rilevanti e quindi segnala nuovamente l'esito positivo o negativo di ogni tentativo.</span><span class="sxs-lookup"><span data-stu-id="5f615-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="5f615-115">Se è possibile effettuare una connessione, il cmdlet riporterà inoltre informazioni quali il nome del database, la versione di SQL Server e il percorso di eventuali database mirror installati.</span><span class="sxs-lookup"><span data-stu-id="5f615-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5f615-116">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="5f615-116">Running the test</span></span>

<span data-ttu-id="5f615-117">Il comando riportato nell'esempio 1 verifica la configurazione del database di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5f615-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="5f615-118">Nell'esempio 2 vengono verificati tutti i database di Lync Server installati nel computer atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5f615-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="5f615-p103">Nell'esempio 3 la verifica viene eseguita solo per il database di archiviazione installato nel computer atl-sql-001.litwareinc.com. Si noti che viene incluso il parametro SqlInstanceName per specificare l'istanza di SQL Server (Archinst) in cui si trova il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5f615-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="5f615-121">Il comando riportato nell'esempio 4 verifica i database installati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="5f615-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5f615-122">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="5f615-122">Determining success or failure</span></span>

<span data-ttu-id="5f615-123">Se la connettività del database è configurata correttamente, si riceverà un output simile al seguente, con la proprietà succeed contrassegnata come **true**:</span><span class="sxs-lookup"><span data-stu-id="5f615-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="5f615-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f615-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="5f615-125">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="5f615-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5f615-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="5f615-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5f615-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="5f615-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5f615-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="5f615-128">DatabaseName : xds</span></span>

<span data-ttu-id="5f615-129">DataSource</span><span class="sxs-lookup"><span data-stu-id="5f615-129">DataSource :</span></span>

<span data-ttu-id="5f615-130">SqlServerVersion</span><span class="sxs-lookup"><span data-stu-id="5f615-130">SQLServerVersion :</span></span>

<span data-ttu-id="5f615-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="5f615-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="5f615-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="5f615-132">InstalledVersion :</span></span>

<span data-ttu-id="5f615-133">Esito positivo: true</span><span class="sxs-lookup"><span data-stu-id="5f615-133">Succeed : True</span></span>

<span data-ttu-id="5f615-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f615-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="5f615-135">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="5f615-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5f615-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="5f615-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5f615-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="5f615-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5f615-138">DatabaseName: LIS</span><span class="sxs-lookup"><span data-stu-id="5f615-138">DatabaseName : lis</span></span>

<span data-ttu-id="5f615-139">DataSource</span><span class="sxs-lookup"><span data-stu-id="5f615-139">DataSource :</span></span>

<span data-ttu-id="5f615-140">SqlServerVersion</span><span class="sxs-lookup"><span data-stu-id="5f615-140">SQLServerVersion :</span></span>

<span data-ttu-id="5f615-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="5f615-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="5f615-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="5f615-142">InstalledVersion :</span></span>

<span data-ttu-id="5f615-143">Esito positivo: true</span><span class="sxs-lookup"><span data-stu-id="5f615-143">Succeed : True</span></span>

<span data-ttu-id="5f615-144">Se il database è configurato correttamente, ma è ancora disponibile, il campo esito positivo verrà visualizzato come **falso**e verranno forniti avvisi e informazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="5f615-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="5f615-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f615-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="5f615-146">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="5f615-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5f615-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="5f615-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5f615-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="5f615-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5f615-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="5f615-149">DatabaseName : xds</span></span>

<span data-ttu-id="5f615-150">DataSource</span><span class="sxs-lookup"><span data-stu-id="5f615-150">DataSource :</span></span>

<span data-ttu-id="5f615-151">SqlServerVersion</span><span class="sxs-lookup"><span data-stu-id="5f615-151">SQLServerVersion :</span></span>

<span data-ttu-id="5f615-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="5f615-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="5f615-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="5f615-153">InstalledVersion :</span></span>

<span data-ttu-id="5f615-154">Esito positivo: false</span><span class="sxs-lookup"><span data-stu-id="5f615-154">Succeed : False</span></span>

<span data-ttu-id="5f615-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f615-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f615-156">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="5f615-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5f615-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="5f615-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5f615-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="5f615-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5f615-159">DatabaseName: LIS</span><span class="sxs-lookup"><span data-stu-id="5f615-159">DatabaseName : lis</span></span>

<span data-ttu-id="5f615-160">DataSource</span><span class="sxs-lookup"><span data-stu-id="5f615-160">DataSource :</span></span>

<span data-ttu-id="5f615-161">SqlServerVersion</span><span class="sxs-lookup"><span data-stu-id="5f615-161">SQLServerVersion :</span></span>

<span data-ttu-id="5f615-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="5f615-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="5f615-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="5f615-163">InstalledVersion :</span></span>

<span data-ttu-id="5f615-164">Esito positivo: false</span><span class="sxs-lookup"><span data-stu-id="5f615-164">Succeed : False</span></span>

<span data-ttu-id="5f615-165">AVVISO: Test-CsDatabase ha rilevato errori.</span><span class="sxs-lookup"><span data-stu-id="5f615-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="5f615-166">Consultare il file di registro per un</span><span class="sxs-lookup"><span data-stu-id="5f615-166">Consult the log file for a</span></span>

<span data-ttu-id="5f615-167">analisi dettagliata e per assicurarsi che tutti gli errori (2) e gli avvisi (0) siano indirizzati</span><span class="sxs-lookup"><span data-stu-id="5f615-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="5f615-168">prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5f615-168">before continuing.</span></span>

<span data-ttu-id="5f615-169">AVVISO: i risultati dettagliati sono disponibili all'indirizzo</span><span class="sxs-lookup"><span data-stu-id="5f615-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="5f615-170">"C:\\utenti\\che\\eseguono\\il\\testing AppData Local temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="5f615-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="5f615-171">04d593cce8e6. html ".</span><span class="sxs-lookup"><span data-stu-id="5f615-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5f615-172">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="5f615-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="5f615-173">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsDatabase** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="5f615-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="5f615-174">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="5f615-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5f615-175">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5f615-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5f615-176">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5f615-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5f615-177">Questo comando avrà esito negativo se il database non è stato configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="5f615-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f615-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f615-178">See Also</span></span>


[<span data-ttu-id="5f615-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="5f615-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="5f615-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="5f615-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="5f615-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="5f615-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

