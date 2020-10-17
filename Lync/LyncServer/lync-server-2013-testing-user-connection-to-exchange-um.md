---
title: 'Lync Server 2013: test della connessione utente alla messaggistica unificata di Exchange'
description: 'Lync Server 2013: test della connessione utente alla messaggistica unificata di Exchange.'
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
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556068"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="bba95-103">Test della connessione utente alla messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bba95-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bba95-104">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="bba95-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bba95-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="bba95-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bba95-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="bba95-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bba95-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="bba95-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bba95-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bba95-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bba95-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="bba95-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bba95-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bba95-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bba95-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="bba95-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="bba95-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bba95-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bba95-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bba95-113">Description</span></span>

<span data-ttu-id="bba95-114">Il cmdlet **test-CsExUMConnectivity** verifica che l'utente specificato sia in grado di connettersi al servizio di messaggistica unificata di Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bba95-114">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="bba95-115">Si noti che questo cmdlet verifica solo che sia possibile effettuare una connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="bba95-115">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="bba95-116">Il servizio non viene testato.</span><span class="sxs-lookup"><span data-stu-id="bba95-116">It does not test the service itself.</span></span> <span data-ttu-id="bba95-117">Per verificare il servizio di messaggistica unificata (eseguendo un cmdlet di transazione sintetica che lascia un messaggio in segreteria telefonica nella cassetta postale di un utente), utilizzare il cmdlet Test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="bba95-117">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bba95-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="bba95-118">Running the test</span></span>

<span data-ttu-id="bba95-119">Nell'esempio seguente viene verificata la connettività di messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bba95-119">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bba95-120">Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bba95-120">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bba95-121">Se necessario, il comando determinerà se il primo utente di test può connettersi alla messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="bba95-121">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="bba95-122">Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="bba95-122">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="bba95-123">I comandi riportati nell'esempio seguente testano la connettività di messaggistica unificata di Exchange per l'utente litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="bba95-123">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="bba95-124">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell per l'utente litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="bba95-124">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="bba95-125">Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **test-CsExUMConnectivity** possa eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="bba95-125">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="bba95-126">Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc \\ kenmyer per determinare se l'utente può connettersi alla messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bba95-126">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="bba95-127">Il comando riportato nell'esempio seguente è una variante del comando appena mostrato.</span><span class="sxs-lookup"><span data-stu-id="bba95-127">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="bba95-128">In questo caso, il parametro OutLoggerVariable è incluso per generare un registro dettagliato di ogni passaggio effettuato dal **test-CsExUMConnectivity** cmdletand l'esito positivo o negativo di ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="bba95-128">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="bba95-129">A tale scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore del parametro ExumText; che determina l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="bba95-129">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="bba95-130">Nel comando finale dell'esempio viene utilizzato il metodo ToXML () per convertire le informazioni del registro in formato XML.</span><span class="sxs-lookup"><span data-stu-id="bba95-130">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="bba95-131">I dati XML vengono quindi scritti in un file denominato C: \\ LogsExumTest.xml tramite \\ il cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="bba95-131">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bba95-132">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="bba95-132">Determining success or failure</span></span>

<span data-ttu-id="bba95-133">Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="bba95-133">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="bba95-134">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bba95-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bba95-135">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="bba95-135">Result : Success</span></span>

<span data-ttu-id="bba95-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bba95-136">Latency : 00:00:00</span></span>

<span data-ttu-id="bba95-137">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="bba95-137">Error Message :</span></span>

<span data-ttu-id="bba95-138">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="bba95-138">Diagnosis :</span></span>

<span data-ttu-id="bba95-139">Se l'utente specificato non è in grado di ricevere notifiche, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="bba95-139">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bba95-140">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bba95-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bba95-141">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="bba95-141">Result : Failure</span></span>

<span data-ttu-id="bba95-142">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bba95-142">Latency : 00:00:00</span></span>

<span data-ttu-id="bba95-143">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="bba95-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="bba95-144">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="bba95-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="bba95-145">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="bba95-145">established connection failed because connected host has</span></span>

<span data-ttu-id="bba95-146">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="bba95-146">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="bba95-147">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="bba95-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="bba95-148">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="bba95-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="bba95-149">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="bba95-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="bba95-150">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="bba95-150">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="bba95-151">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="bba95-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bba95-152">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="bba95-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="bba95-153">Di seguito sono riportate alcune ragioni comuni per cui **test-CsExUMConnectivity** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="bba95-153">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="bba95-154">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="bba95-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="bba95-155">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="bba95-155">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="bba95-156">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bba95-156">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="bba95-157">Questo comando avrà esito negativo se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="bba95-157">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="bba95-158">Questo comando avrà esito negativo se il server di Exchange non è raggiungibile tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="bba95-158">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bba95-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bba95-159">See Also</span></span>


[<span data-ttu-id="bba95-160">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="bba95-160">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

