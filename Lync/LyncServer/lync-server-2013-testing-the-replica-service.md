---
title: 'Lync Server 2013: test del servizio di replica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ad585ab12d874b7689aab6442ac913a06c8792f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="16698-102">Test del servizio di replica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16698-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16698-103">_**Ultimo argomento modificato:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="16698-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16698-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="16698-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="16698-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="16698-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16698-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="16698-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="16698-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16698-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16698-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="16698-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="16698-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="16698-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="16698-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="16698-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="16698-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="16698-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="16698-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16698-112">Description</span></span>

<span data-ttu-id="16698-113">Il cmdlet **Test-CsReplica** verifica che il servizio di replica di Lync Server 2013 sia in esecuzione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="16698-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="16698-114">Il cmdlet **Test-CsReplica** consente di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="16698-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="16698-115">controllo dello stato dell'agente di replica e dei servizi dell'agente di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="16698-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="16698-116">Verifica che le porte necessarie siano state aperte in Windows Firewall</span><span class="sxs-lookup"><span data-stu-id="16698-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="16698-117">Verificare che esistano i gruppi di sicurezza di Active Directory e del computer locale necessari.</span><span class="sxs-lookup"><span data-stu-id="16698-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="16698-118">Si noti che questo cmdlet deve essere eseguito localmente.</span><span class="sxs-lookup"><span data-stu-id="16698-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="16698-119">In altri casi, deve essere eseguito nello stesso computer in cui è in esecuzione il servizio di replica.</span><span class="sxs-lookup"><span data-stu-id="16698-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="16698-120">Non sono disponibili opzioni per l'esecuzione del cmdlet **Test-CsReplica** su un server remoto.</span><span class="sxs-lookup"><span data-stu-id="16698-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="16698-121">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="16698-121">Running the test</span></span>

<span data-ttu-id="16698-122">Il comando riportato nell'esempio 1 verifica il servizio di replica di Lync Server 2013 nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="16698-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="16698-123">In questo esempio viene utilizzato il parametro Verbose per garantire che le informazioni sul test, tra cui l'eventuale esito negativo o esito positivo del test e la posizione del report generato dal test, vengano visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="16698-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="16698-124">L'esempio 2 è una variazione del comando illustrato nell'esempio 1.</span><span class="sxs-lookup"><span data-stu-id="16698-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="16698-125">In questo caso, il parametro report è incluso per specificare un percorso e un nome di cartella per il report generato dal test.</span><span class="sxs-lookup"><span data-stu-id="16698-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="16698-126">Se non si specifica un percorso, al report verrà assegnato un nome generato automaticamente simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="16698-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="16698-127">C:\\Users\\Administrator.\\litwareinc\\AppData\\Local\\temp\\1 test-CS-replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html</span><span class="sxs-lookup"><span data-stu-id="16698-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="16698-128">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="16698-128">Determining success or failure</span></span>

<span data-ttu-id="16698-129">Inserire qui il corpo della sezione.</span><span class="sxs-lookup"><span data-stu-id="16698-129">Insert section body here.</span></span>

<span data-ttu-id="16698-130">VERBOse: creazione di un nuovo file di registro\\"\\C\\:\\utenti\\che\\testano la temperatura locale Test-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="16698-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="16698-131">VERBOse: creazione di un nuovo file di registro\\"\\C\\:\\utenti\\che\\testano la temperatura locale Test-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="16698-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="16698-132">VERBOse: l'elaborazione "Test-CsReplica" è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="16698-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="16698-133">VERBOse: i risultati dettagliati sono disponibili in "C\\:\\Users testing\\AppData\\Local\\temp\\Test-CsReplica-3cb066b3-DD23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="16698-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="16698-134">VERBOse: creazione di un nuovo file di registro</span><span class="sxs-lookup"><span data-stu-id="16698-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="16698-135">"C:\\utenti\\che\\eseguono\\il\\testing di AppData Local temp\\2\\Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="16698-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="16698-136">d3bd0e4a083. xml ".</span><span class="sxs-lookup"><span data-stu-id="16698-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="16698-137">VERBOse: creazione di un nuovo file di registro</span><span class="sxs-lookup"><span data-stu-id="16698-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="16698-138">"C:\\utenti\\che\\eseguono\\il\\testing di AppData Local temp\\2\\Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="16698-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="16698-139">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="16698-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="16698-140">AVVISO: Test-CsReplica non riuscito.</span><span class="sxs-lookup"><span data-stu-id="16698-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="16698-141">AVVISO: i risultati dettagliati sono disponibili all'indirizzo</span><span class="sxs-lookup"><span data-stu-id="16698-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="16698-142">"C:\\utenti\\che\\eseguono\\il\\testing di AppData Local temp\\2\\Test-CsReplica-29fddb35-f56e-4E3C-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="16698-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="16698-143">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="16698-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="16698-144">Test-CsReplica: esecuzione del comando non riuscita: non è stato richiesto l'accesso al registro di sistema</span><span class="sxs-lookup"><span data-stu-id="16698-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="16698-145">consentiti.</span><span class="sxs-lookup"><span data-stu-id="16698-145">allowed.</span></span>

<span data-ttu-id="16698-146">At line: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="16698-146">At line:1 char:1</span></span>

<span data-ttu-id="16698-147">\+Test-CsReplica-verbose</span><span class="sxs-lookup"><span data-stu-id="16698-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="16698-148">\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], sicurezza</span><span class="sxs-lookup"><span data-stu-id="16698-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="16698-149">Eccezione</span><span class="sxs-lookup"><span data-stu-id="16698-149">Exception</span></span>

<span data-ttu-id="16698-150">\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. Rtc. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="16698-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="16698-151">mento. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="16698-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="16698-152">PS C:\\test\\degli utenti\></span><span class="sxs-lookup"><span data-stu-id="16698-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="16698-153">PS C:\\utenti\\che\> testano test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="16698-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="16698-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="16698-154">icrosoft.com"</span></span>

<span data-ttu-id="16698-155">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="16698-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="16698-156">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="16698-156">domain name (FQDN).</span></span> <span data-ttu-id="16698-157">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="16698-157">Using default Registrar port number.</span></span> <span data-ttu-id="16698-158">Eccezione</span><span class="sxs-lookup"><span data-stu-id="16698-158">Exception:</span></span>

<span data-ttu-id="16698-159">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="16698-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="16698-160">a</span><span class="sxs-lookup"><span data-stu-id="16698-160">at</span></span>

<span data-ttu-id="16698-161">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="16698-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="16698-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="16698-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="16698-163">Test-CsUcwaConference: non è stato assegnato un utente di test</span><span class="sxs-lookup"><span data-stu-id="16698-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="16698-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="16698-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="16698-165">Verificare la configurazione dell'utente di test.</span><span class="sxs-lookup"><span data-stu-id="16698-165">Verify test user configuration.</span></span>

<span data-ttu-id="16698-166">At line: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="16698-166">At line:1 char:1</span></span>

<span data-ttu-id="16698-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="16698-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="16698-168">\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="16698-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="16698-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="16698-169">, InvalidOperationException</span></span>

<span data-ttu-id="16698-170">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. Rtc. Management. synth</span><span class="sxs-lookup"><span data-stu-id="16698-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="16698-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="16698-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="16698-172">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="16698-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="16698-173">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsReplica** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="16698-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="16698-174">Potrebbe verificarsi un problema maggiore con l'agente di replica e i servizi agente di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="16698-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="16698-175">Le porte necessarie potrebbero non essere aperte nel firewall di Windows</span><span class="sxs-lookup"><span data-stu-id="16698-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="16698-176">Potrebbero non esistere i gruppi di sicurezza di Active Directory e del computer locale necessari</span><span class="sxs-lookup"><span data-stu-id="16698-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

