---
title: 'Lync Server 2013: test della connessione utente alla messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cf7189df06549a3008fd86b9395617c6aea3e98
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="f6eb2-102">Test della connessione utente alla messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6eb2-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6eb2-103">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="f6eb2-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6eb2-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="f6eb2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f6eb2-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="f6eb2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6eb2-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="f6eb2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f6eb2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6eb2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6eb2-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="f6eb2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f6eb2-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f6eb2-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="f6eb2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="f6eb2-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f6eb2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6eb2-112">Description</span></span>

<span data-ttu-id="f6eb2-113">Il cmdlet **test-CsExUMConnectivity** verifica che l'utente specificato sia in grado di connettersi al servizio di messaggistica unificata di Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="f6eb2-114">Si noti che questo cmdlet verifica solo che sia possibile effettuare una connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="f6eb2-115">Il servizio non viene testato.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-115">It does not test the service itself.</span></span> <span data-ttu-id="f6eb2-116">Per verificare il servizio di messaggistica unificata (eseguendo un cmdlet di transazione sintetica che lascia un messaggio in segreteria telefonica nella cassetta postale di un utente), utilizzare il cmdlet Test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f6eb2-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="f6eb2-117">Running the test</span></span>

<span data-ttu-id="f6eb2-118">Nell'esempio seguente viene verificata la connettività di messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f6eb2-119">Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f6eb2-120">Se necessario, il comando determinerà se il primo utente di test può connettersi alla messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="f6eb2-121">Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="f6eb2-122">I comandi riportati nell'esempio seguente testano la connettività di messaggistica unificata di Exchange per\\l'utente litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="f6eb2-123">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell\\per l'utente litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="f6eb2-124">Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **test-CsExUMConnectivity** possa eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="f6eb2-125">Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se l'utente può connettersi alla messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f6eb2-126">Il comando riportato nell'esempio seguente è una variante del comando appena mostrato.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="f6eb2-127">In questo caso, il parametro OutLoggerVariable è incluso per generare un registro dettagliato di ogni passaggio effettuato dal **test-CsExUMConnectivity** cmdletand l'esito positivo o negativo di ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="f6eb2-128">A tale scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore del parametro ExumText; che determina l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="f6eb2-129">Nel comando finale dell'esempio viene utilizzato il metodo ToXML () per convertire le informazioni del registro in formato XML.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="f6eb2-130">I dati XML vengono quindi scritti in un file denominato C:\\logs\\ExumTest. XML utilizzando il cmdlet out-file.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f6eb2-131">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="f6eb2-131">Determining success or failure</span></span>

<span data-ttu-id="f6eb2-132">Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="f6eb2-133">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f6eb2-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f6eb2-134">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="f6eb2-134">Result : Success</span></span>

<span data-ttu-id="f6eb2-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f6eb2-135">Latency : 00:00:00</span></span>

<span data-ttu-id="f6eb2-136">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-136">Error Message :</span></span>

<span data-ttu-id="f6eb2-137">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="f6eb2-137">Diagnosis :</span></span>

<span data-ttu-id="f6eb2-138">Se l'utente specificato non è in grado di ricevere notifiche, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f6eb2-139">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f6eb2-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f6eb2-140">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="f6eb2-140">Result : Failure</span></span>

<span data-ttu-id="f6eb2-141">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f6eb2-141">Latency : 00:00:00</span></span>

<span data-ttu-id="f6eb2-142">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="f6eb2-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="f6eb2-143">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="f6eb2-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="f6eb2-144">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="f6eb2-144">established connection failed because connected host has</span></span>

<span data-ttu-id="f6eb2-145">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="f6eb2-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="f6eb2-146">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="f6eb2-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="f6eb2-147">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="f6eb2-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="f6eb2-148">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="f6eb2-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="f6eb2-149">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="f6eb2-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="f6eb2-150">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="f6eb2-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f6eb2-151">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="f6eb2-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="f6eb2-152">Di seguito sono riportate alcune ragioni comuni per cui **test-CsExUMConnectivity** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="f6eb2-153">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f6eb2-154">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f6eb2-155">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f6eb2-156">Questo comando avrà esito negativo se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="f6eb2-157">Questo comando avrà esito negativo se il server di Exchange non è raggiungibile tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6eb2-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6eb2-158">See Also</span></span>


[<span data-ttu-id="f6eb2-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="f6eb2-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

