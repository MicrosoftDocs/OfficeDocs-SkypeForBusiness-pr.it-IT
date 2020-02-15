---
title: 'Lync Server 2013: verifica della condivisione di applicazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2797a116bddb73543a27553faa55650b9ad16e8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="e8c88-102">Verifica della condivisione di applicazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8c88-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8c88-103">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="e8c88-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8c88-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="e8c88-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e8c88-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="e8c88-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8c88-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="e8c88-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e8c88-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8c88-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8c88-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="e8c88-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e8c88-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e8c88-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e8c88-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="e8c88-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="e8c88-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e8c88-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e8c88-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8c88-112">Description</span></span>

<span data-ttu-id="e8c88-113">Il cmdlet **Test-CsASConference** verifica che una coppia di utenti di test sia in grado di partecipare a una conferenza online che include la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c88-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="e8c88-114">A tale scopo, il cmdlet registra i due utenti con Lync Server 2013 e quindi utilizza uno degli account utente per creare una nuova conferenza che includa la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c88-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="e8c88-115">Il cmdlet verifica quindi che il secondo utente sia in grado di partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="e8c88-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e8c88-116">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="e8c88-116">Running the test</span></span>

<span data-ttu-id="e8c88-p103">Il comando riportato nell'esempio 1 verifica che sia possibile tenere una conferenza di condivisione applicazioni nel pool atl-cs-001.litwareinc.com. Nel comando si presuppone che sia stata configurata una coppia di utenti di test per il pool specificato. Se non esistono utenti di test, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e8c88-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e8c88-p104">Nell'esempio 2 viene verificato che il servizio Join Launcher possa partecipare a una conferenza di condivisione applicazioni nel pool atl-cs-001.litwareinc.com. Questo comando verifica solo il servizio. Non è necessario alcun dispositivo mobile per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="e8c88-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="e8c88-122">I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di\\utenti (litwareinc\\Pilar e litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di condurre una conferenza di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c88-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="e8c88-123">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet Get-Credential per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="e8c88-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="e8c88-124">Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Pilar Ackerman. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="e8c88-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="e8c88-125">Il secondo comando effettua la stessa operazione, questa volta restituendo un oggetto credenziali per l'account Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e8c88-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="e8c88-126">Con gli oggetti Credential disponibili, il terzo comando determina se i due utenti possono accedere o meno a Lync Server 2013 e condurre una conferenza di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c88-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="e8c88-127">Per eseguire questa attività, viene chiamato il cmdlet **Test-CsASConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrazione); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (oggetto Windows PowerShell contenente le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (oggetto Windows PowerShell contenente le credenziali per l'altro utente di test).</span><span class="sxs-lookup"><span data-stu-id="e8c88-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e8c88-128">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="e8c88-128">Determining success or failure</span></span>

<span data-ttu-id="e8c88-129">Se la condivisione di applicazioni è configurata correttamente, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="e8c88-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e8c88-130">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8c88-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e8c88-131">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="e8c88-131">Result : Success</span></span>

<span data-ttu-id="e8c88-132">Latenza: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="e8c88-132">Latency : 00:00:01</span></span>

<span data-ttu-id="e8c88-133">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="e8c88-133">Error Message :</span></span>

<span data-ttu-id="e8c88-134">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="e8c88-134">Diagnosis :</span></span>

<span data-ttu-id="e8c88-135">Se gli utenti specificati non sono in grado di condividere le applicazioni, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="e8c88-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e8c88-136">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8c88-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e8c88-137">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="e8c88-137">Result : Failure</span></span>

<span data-ttu-id="e8c88-138">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e8c88-138">Latency : 00:00:00</span></span>

<span data-ttu-id="e8c88-139">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="e8c88-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="e8c88-140">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="e8c88-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="e8c88-141">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="e8c88-141">established connection failed because connected host has</span></span>

<span data-ttu-id="e8c88-142">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="e8c88-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="e8c88-143">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="e8c88-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="e8c88-144">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="e8c88-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="e8c88-145">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="e8c88-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="e8c88-146">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="e8c88-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="e8c88-147">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="e8c88-147">Diagnosis :</span></span>

<span data-ttu-id="e8c88-148">Ad esempio, l'output precedente include la nota "la parte connessa non ha risposto correttamente" che indica in genere un problema con il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e8c88-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e8c88-149">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="e8c88-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="e8c88-150">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsASConference** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="e8c88-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="e8c88-151">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="e8c88-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e8c88-152">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e8c88-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e8c88-153">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e8c88-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e8c88-154">Questo comando avrà esito negativo se agli utenti di test sono stati assegnati criteri di conferenza che impediscono l'utilizzo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c88-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="e8c88-155">Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="e8c88-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8c88-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8c88-156">See Also</span></span>


[<span data-ttu-id="e8c88-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="e8c88-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="e8c88-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="e8c88-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

