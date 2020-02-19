---
title: 'Lync Server 2013: test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa3ad3f51d1342ac99d3c58be66931ba0770bf6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="645fb-102">Test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="645fb-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="645fb-103">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="645fb-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="645fb-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="645fb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="645fb-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="645fb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="645fb-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="645fb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="645fb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="645fb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="645fb-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="645fb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="645fb-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="645fb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="645fb-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="645fb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="645fb-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="645fb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="645fb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="645fb-112">Description</span></span>

<span data-ttu-id="645fb-113">Il cmdlet **test-CsExUMVoiceMail** consente agli amministratori di verificare che un utente possa accedere al servizio di messaggistica unificata di Microsoft Exchange Server 2013 e utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="645fb-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="645fb-114">A tale scopo, il cmdlet si connette al servizio Messaggistica unificata di Exchange e lascia un messaggio in segreteria telefonica nella cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="645fb-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="645fb-115">Il messaggio può essere fornito dal sistema o essere contenuto in un file WAV personalizzato registrato personalmente.</span><span class="sxs-lookup"><span data-stu-id="645fb-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="645fb-116">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="645fb-116">Running the test</span></span>

<span data-ttu-id="645fb-117">Nell'esempio seguente viene verificata la connettività della segreteria telefonica della messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="645fb-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="645fb-118">Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="645fb-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="645fb-119">Se necessario, il comando determinerà se il primo utente di test può utilizzare la segreteria telefonica di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="645fb-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="645fb-120">Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="645fb-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="645fb-121">I comandi mostrati nell'esempio seguente verificano la connettività della segreteria telefonica di messaggistica unificata\\di Exchange per l'utente litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="645fb-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="645fb-122">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell\\per l'utente litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="645fb-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="645fb-123">Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **test-CsExUMVoiceMail** possa eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="645fb-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="645fb-124">Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se l'utente può connettersi alla segreteria telefonica di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="645fb-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="645fb-125">Il comando riportato nell'esempio seguente è una variante del comando mostrato nell'esempio 1. in questo caso, il parametro OutLoggerVariable è incluso per generare un registro dettagliato di ogni passaggio effettuato dal **test-CsExUMVoiceMail** cmdletand l'esito positivo o negativo di ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="645fb-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="645fb-126">A tale scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore del parametro ExumText; che determina l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="645fb-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="645fb-127">Nel comando finale dell'esempio viene utilizzato il metodo ToXML () per convertire le informazioni del registro in formato XML.</span><span class="sxs-lookup"><span data-stu-id="645fb-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="645fb-128">I dati XML vengono quindi scritti in un file denominato C:\\logs\\VoicemailTest. XML utilizzando il cmdlet out-file.</span><span class="sxs-lookup"><span data-stu-id="645fb-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="645fb-129">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="645fb-129">Determining success or failure</span></span>

<span data-ttu-id="645fb-130">Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="645fb-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="645fb-131">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="645fb-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="645fb-132">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="645fb-132">Result : Success</span></span>

<span data-ttu-id="645fb-133">Latenza: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="645fb-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="645fb-134">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="645fb-134">Error Message :</span></span>

<span data-ttu-id="645fb-135">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="645fb-135">Diagnosis :</span></span>

<span data-ttu-id="645fb-136">Se l'utente specificato non è in grado di connettersi alla segreteria telefonica, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="645fb-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="645fb-137">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="645fb-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="645fb-138">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="645fb-138">domain name (FQDN).</span></span> <span data-ttu-id="645fb-139">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="645fb-139">Using default Registrar port number.</span></span> <span data-ttu-id="645fb-140">Eccezione</span><span class="sxs-lookup"><span data-stu-id="645fb-140">Exception:</span></span>

<span data-ttu-id="645fb-141">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="645fb-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="645fb-142">a</span><span class="sxs-lookup"><span data-stu-id="645fb-142">at</span></span>

<span data-ttu-id="645fb-143">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="645fb-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="645fb-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="645fb-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="645fb-145">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="645fb-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="645fb-146">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="645fb-146">Result : Failure</span></span>

<span data-ttu-id="645fb-147">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="645fb-147">Latency : 00:00:00</span></span>

<span data-ttu-id="645fb-148">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="645fb-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="645fb-149">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="645fb-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="645fb-150">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="645fb-150">established connection failed because connected host has</span></span>

<span data-ttu-id="645fb-151">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="645fb-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="645fb-152">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="645fb-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="645fb-153">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="645fb-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="645fb-154">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="645fb-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="645fb-155">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="645fb-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="645fb-156">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="645fb-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="645fb-157">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="645fb-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="645fb-158">Di seguito sono riportate alcune ragioni comuni per cui **test-CsExUMVoiceMail** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="645fb-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="645fb-159">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="645fb-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="645fb-160">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="645fb-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="645fb-161">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="645fb-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="645fb-162">Questo comando avrà esito negativo se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="645fb-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="645fb-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="645fb-163">See Also</span></span>


[<span data-ttu-id="645fb-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="645fb-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

