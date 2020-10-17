---
title: 'Lync Server 2013: test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange'
description: 'Lync Server 2013: test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange.'
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
ms.openlocfilehash: b887b5b0df02a5864e0a39f2b62893d20105a86a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552612"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="fb55e-103">Test della connessione utente alla segreteria telefonica di messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb55e-103">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb55e-104">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="fb55e-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb55e-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="fb55e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fb55e-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="fb55e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb55e-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="fb55e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fb55e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb55e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb55e-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="fb55e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fb55e-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fb55e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fb55e-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="fb55e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="fb55e-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fb55e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fb55e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb55e-113">Description</span></span>

<span data-ttu-id="fb55e-114">Il cmdlet **test-CsExUMVoiceMail** consente agli amministratori di verificare che un utente possa accedere al servizio di messaggistica unificata di Microsoft Exchange Server 2013 e utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="fb55e-114">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="fb55e-115">A tale scopo, il cmdlet si connette al servizio Messaggistica unificata di Exchange e lascia un messaggio in segreteria telefonica nella cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="fb55e-115">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="fb55e-116">Il messaggio può essere fornito dal sistema o essere contenuto in un file WAV personalizzato registrato personalmente.</span><span class="sxs-lookup"><span data-stu-id="fb55e-116">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fb55e-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="fb55e-117">Running the test</span></span>

<span data-ttu-id="fb55e-118">Nell'esempio seguente viene verificata la connettività della segreteria telefonica della messaggistica unificata di Exchange per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fb55e-118">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fb55e-119">Questo comando funzionerà solo se gli utenti di test sono stati definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fb55e-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fb55e-120">Se necessario, il comando determinerà se il primo utente di test può utilizzare la segreteria telefonica di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="fb55e-120">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="fb55e-121">Se gli utenti di test non sono stati configurati per il pool, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fb55e-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="fb55e-122">I comandi mostrati nell'esempio seguente verificano la connettività della segreteria telefonica di messaggistica unificata di Exchange per l'utente litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="fb55e-122">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="fb55e-123">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell per l'utente litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="fb55e-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="fb55e-124">Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **test-CsExUMVoiceMail** possa eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="fb55e-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="fb55e-125">Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc \\ kenmyer per determinare se l'utente può connettersi alla segreteria telefonica di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fb55e-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="fb55e-126">Il comando riportato nell'esempio seguente è una variante del comando mostrato nell'esempio 1. in questo caso, il parametro OutLoggerVariable è incluso per generare un registro dettagliato di ogni passaggio effettuato dal **test-CsExUMVoiceMail** cmdletand l'esito positivo o negativo di ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="fb55e-126">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="fb55e-127">A tale scopo, il parametro OutLoggerVariable viene aggiunto insieme al valore del parametro ExumText; che determina l'archiviazione di informazioni dettagliate sulla registrazione in una variabile denominata $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="fb55e-127">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="fb55e-128">Nel comando finale dell'esempio viene utilizzato il metodo ToXML () per convertire le informazioni del registro in formato XML.</span><span class="sxs-lookup"><span data-stu-id="fb55e-128">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="fb55e-129">I dati XML vengono quindi scritti in un file denominato C: \\ LogsVoicemailTest.xml tramite \\ il cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="fb55e-129">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fb55e-130">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="fb55e-130">Determining success or failure</span></span>

<span data-ttu-id="fb55e-131">Se l'integrazione di Exchange è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="fb55e-131">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="fb55e-132">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb55e-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fb55e-133">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="fb55e-133">Result : Success</span></span>

<span data-ttu-id="fb55e-134">Latenza: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="fb55e-134">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="fb55e-135">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="fb55e-135">Error Message :</span></span>

<span data-ttu-id="fb55e-136">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="fb55e-136">Diagnosis :</span></span>

<span data-ttu-id="fb55e-137">Se l'utente specificato non è in grado di connettersi alla segreteria telefonica, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="fb55e-137">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fb55e-138">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="fb55e-138">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="fb55e-139">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="fb55e-139">domain name (FQDN).</span></span> <span data-ttu-id="fb55e-140">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="fb55e-140">Using default Registrar port number.</span></span> <span data-ttu-id="fb55e-141">Eccezione</span><span class="sxs-lookup"><span data-stu-id="fb55e-141">Exception:</span></span>

<span data-ttu-id="fb55e-142">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="fb55e-142">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="fb55e-143">a</span><span class="sxs-lookup"><span data-stu-id="fb55e-143">at</span></span>

<span data-ttu-id="fb55e-144">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="fb55e-144">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="fb55e-145">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="fb55e-145">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="fb55e-146">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb55e-146">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fb55e-147">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="fb55e-147">Result : Failure</span></span>

<span data-ttu-id="fb55e-148">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fb55e-148">Latency : 00:00:00</span></span>

<span data-ttu-id="fb55e-149">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="fb55e-149">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="fb55e-150">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="fb55e-150">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="fb55e-151">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="fb55e-151">established connection failed because connected host has</span></span>

<span data-ttu-id="fb55e-152">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="fb55e-152">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="fb55e-153">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="fb55e-153">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="fb55e-154">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="fb55e-154">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="fb55e-155">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="fb55e-155">time, or established connection failed because connected host</span></span>

<span data-ttu-id="fb55e-156">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="fb55e-156">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="fb55e-157">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="fb55e-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fb55e-158">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="fb55e-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="fb55e-159">Di seguito sono riportate alcune ragioni comuni per cui **test-CsExUMVoiceMail** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="fb55e-159">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="fb55e-160">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="fb55e-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="fb55e-161">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fb55e-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="fb55e-162">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fb55e-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="fb55e-163">Questo comando avrà esito negativo se il server di Exchange non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="fb55e-163">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb55e-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb55e-164">See Also</span></span>


[<span data-ttu-id="fb55e-165">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="fb55e-165">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

