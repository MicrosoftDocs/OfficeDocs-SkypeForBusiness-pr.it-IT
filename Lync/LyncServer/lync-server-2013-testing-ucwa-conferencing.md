---
title: 'Lync Server 2013: testing di conferenza UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="ff0a6-102">Test di conferenza UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff0a6-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff0a6-103">_**Argomento Ultima modifica:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="ff0a6-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff0a6-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ff0a6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ff0a6-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="ff0a6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff0a6-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="ff0a6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ff0a6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff0a6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff0a6-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ff0a6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ff0a6-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ff0a6-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsUcwaConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="ff0a6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="ff0a6-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ff0a6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ff0a6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff0a6-112">Description</span></span>

<span data-ttu-id="ff0a6-113">Il cmdlet **test-CsUcwaConference** verifica che una coppia di utenti di test possa pianificare, partecipare e quindi eseguire una conferenza online con l'API Web Unified Communications (UCWA).</span><span class="sxs-lookup"><span data-stu-id="ff0a6-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="ff0a6-114">A questo scopo, il cmdlet usa il servizio ticket web di Lync Server per autenticare i due utenti di test e registrarli con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="ff0a6-115">Il cmdlet avvia quindi una conferenza con le credenziali dell'Organizzatore e invita il partecipante a partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="ff0a6-116">Dopo l'aggiunta della riunione, il cmdlet **test-CsUcwaConference** verifica che gli utenti possano eseguire operazioni come il messaggio istantaneo di Exchange e i pool di conduzione, quindi disconnette la conferenza e Annulla la registrazione dei due utenti di test.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="ff0a6-117">La conferenza pianificata verrà eliminata anche al termine del test.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="ff0a6-118">Il cmdlet **test-CsUcwaConference** può essere usato anche per determinare se gli utenti anonimi possono partecipare a conferenze online.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="ff0a6-119">Tieni presente che il cmdlet **test-CsUcwaConference** non deve essere eseguito in un pool di Microsoft Lync Server 2010, a meno che non sia stato installato UCWA nel pool.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="ff0a6-120">Se UCWA non è stato installato, la chiamata al cmdlet **test-CsUcwaConference** non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ff0a6-121">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ff0a6-121">Running the test</span></span>

<span data-ttu-id="ff0a6-122">Il comando mostrato nell'esempio 1 Verifica che una coppia di utenti di test possa partecipare a una conferenza UCWA nel pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ff0a6-123">Tieni presente che questo comando non riesce se non hai predefinito una coppia di utenti di test di configurazione per il monitoraggio dell'integrità per atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ff0a6-124">I comandi mostrati nell'esempio 2 verificano la possibilità di una coppia di utenti\\(litwareinc Pilar\\e litwareinc kenmyer) di partecipare a una conferenza di UCWA.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="ff0a6-125">A questo scopo, il primo comando nell'esempio usa il cmdlet Get-Credential per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="ff0a6-126">Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziali risultante viene quindi archiviato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="ff0a6-127">Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="ff0a6-128">Con i due oggetti credenziale disponibili, il terzo comando nell'esempio determina se i due utenti possono partecipare a una conferenza di UCWA.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="ff0a6-129">Per eseguire questa attività, viene chiamato il cmdlet **test-CsUcwaConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); OrganizerSipAddress (l'indirizzo SIP per l'organizzatore della riunione); OrganizerCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ParticipantSipAddress (l'indirizzo SIP per l'altro utente di test); e ParticipantCredential (l'oggetto interfaccia della riga di comando di Windows PowerShell che contiene le credenziali per l'altro utente).</span><span class="sxs-lookup"><span data-stu-id="ff0a6-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ff0a6-130">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ff0a6-130">Determining success or failure</span></span>

<span data-ttu-id="ff0a6-131">Se i servizi di conferenza sono configurati correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="ff0a6-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ff0a6-132">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ff0a6-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ff0a6-133">URI di destinazione: https://LyncTest-SE. LyncTest. SelfHost. Corp.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="ff0a6-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="ff0a6-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="ff0a6-135">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="ff0a6-135">Result : Success</span></span>

<span data-ttu-id="ff0a6-136">Latenza: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="ff0a6-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="ff0a6-137">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="ff0a6-137">Error Message :</span></span>

<span data-ttu-id="ff0a6-138">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ff0a6-138">Diagnosis :</span></span>

<span data-ttu-id="ff0a6-139">Se gli utenti specificati non possono usare i servizi di conferenza, il risultato verrà visualizzato come **errore**e le informazioni aggiuntive verranno registrate nelle proprietà errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="ff0a6-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ff0a6-140">AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo</span><span class="sxs-lookup"><span data-stu-id="ff0a6-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="ff0a6-141">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ff0a6-141">domain name (FQDN).</span></span> <span data-ttu-id="ff0a6-142">Uso del numero di porta registrar predefinito.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-142">Using default Registrar port number.</span></span> <span data-ttu-id="ff0a6-143">Eccezione</span><span class="sxs-lookup"><span data-stu-id="ff0a6-143">Exception:</span></span>

<span data-ttu-id="ff0a6-144">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="ff0a6-145">a</span><span class="sxs-lookup"><span data-stu-id="ff0a6-145">at</span></span>

<span data-ttu-id="ff0a6-146">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="ff0a6-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="ff0a6-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="ff0a6-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="ff0a6-148">Test-CsUcwaConference: non è stato assegnato un utente di test</span><span class="sxs-lookup"><span data-stu-id="ff0a6-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="ff0a6-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="ff0a6-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="ff0a6-150">Verificare la configurazione degli utenti di test.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-150">Verify test user configuration.</span></span>

<span data-ttu-id="ff0a6-151">At line: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="ff0a6-151">At line:1 char:1</span></span>

<span data-ttu-id="ff0a6-152">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="ff0a6-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="ff0a6-153">\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="ff0a6-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="ff0a6-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="ff0a6-154">, InvalidOperationException</span></span>

<span data-ttu-id="ff0a6-155">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. Rtc. Management. synth</span><span class="sxs-lookup"><span data-stu-id="ff0a6-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="ff0a6-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="ff0a6-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ff0a6-157">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="ff0a6-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="ff0a6-158">Ecco alcuni motivi comuni per cui **test-CsUcwaConference** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ff0a6-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="ff0a6-159">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ff0a6-160">Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ff0a6-161">Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ff0a6-162">La possibilità di eseguire una conferenza dipende dai criteri di conferenza assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsUcwaConference** , ovvero il "mittente").</span><span class="sxs-lookup"><span data-stu-id="ff0a6-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="ff0a6-163">Se l'organizzatore non è autorizzato ad includere attività di collaborazione nella riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsUcwaConference** non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="ff0a6-164">Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="ff0a6-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff0a6-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff0a6-165">See Also</span></span>


[<span data-ttu-id="ff0a6-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="ff0a6-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="ff0a6-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="ff0a6-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="ff0a6-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="ff0a6-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

