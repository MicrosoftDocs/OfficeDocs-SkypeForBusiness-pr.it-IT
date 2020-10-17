---
title: 'Lync Server 2013: verifica della condivisione nelle conferenze'
description: 'Lync Server 2013: verifica della condivisione nelle conferenze.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e569a97d102664b64c201af9b60061813df69ef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556242"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="39794-103">Verifica della condivisione nelle conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39794-103">Testing sharing in conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39794-104">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="39794-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39794-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="39794-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="39794-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="39794-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39794-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="39794-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="39794-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39794-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39794-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39794-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="39794-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="39794-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="39794-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsDataConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="39794-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="39794-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="39794-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="39794-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39794-113">Description</span></span>

<span data-ttu-id="39794-114">In Lync Server 2013, una conferenza dati è una conferenza in cui vengono utilizzate attività di collaborazione come la lavagna o le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="39794-114">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="39794-115">Il cmdlet **test-CsDataConference** consente di verificare che una coppia di utenti sia in grado di partecipare a una conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="39794-115">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="39794-116">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="39794-116">Running the test</span></span>

<span data-ttu-id="39794-p103">Il comando riportato nell'esempio 1 verifica che sia possibile tenere una conferenza dati nel pool atl-cs-001.litwareinc.com. Nel comando si presuppone che sia stata configurata una coppia di utenti di test per il pool specificato. Se non esistono utenti di test, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="39794-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="39794-120">I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di utenti (litwareinc \\ Pilar e litwareinc \\ kenmyer) di accedere a Lync Server 2013 e quindi di condurre una conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="39794-120">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="39794-121">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="39794-121">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="39794-122">Poiché il nome di accesso, litwareinc \\ Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Pilar Ackerman. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="39794-122">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="39794-123">Il secondo comando effettua la stessa operazione, questa volta restituendo un oggetto credenziali per l'account Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="39794-123">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="39794-124">Con gli oggetti Credential disponibili, il terzo comando determina se i due utenti possono accedere o meno a Lync Server 2013 e condurre una conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="39794-124">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="39794-125">Per eseguire questa attività, viene chiamato il cmdlet **test-CsDataConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrazione); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (oggetto Windows PowerShell contenente le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (oggetto Windows PowerShell contenente le credenziali per l'altro utente di test).</span><span class="sxs-lookup"><span data-stu-id="39794-125">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="39794-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="39794-126">Determining success or failure</span></span>

<span data-ttu-id="39794-127">Se i servizi di conferenza dati sono configurati correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="39794-127">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="39794-128">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39794-128">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39794-129">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="39794-129">Result : Success</span></span>

<span data-ttu-id="39794-130">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="39794-130">Latency : 00:00:00</span></span>

<span data-ttu-id="39794-131">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="39794-131">Error Message :</span></span>

<span data-ttu-id="39794-132">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="39794-132">Diagnosis :</span></span>

<span data-ttu-id="39794-133">Se gli utenti specificati non possono utilizzare la condivisione dei dati, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="39794-133">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="39794-134">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39794-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39794-135">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="39794-135">Result : Failure</span></span>

<span data-ttu-id="39794-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="39794-136">Latency : 00:00:00</span></span>

<span data-ttu-id="39794-137">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="39794-137">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="39794-138">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="39794-138">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="39794-139">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="39794-139">established connection failed because connected host has</span></span>

<span data-ttu-id="39794-140">Impossibile rispondere \[ 2001:4898: E8: f39e: 5c9a: AD83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="39794-140">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="39794-141">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="39794-141">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="39794-142">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="39794-142">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="39794-143">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="39794-143">time, or established connection failed because connected host</span></span>

<span data-ttu-id="39794-144">non è stato in grado di rispondere</span><span class="sxs-lookup"><span data-stu-id="39794-144">has failed to respond</span></span>

<span data-ttu-id="39794-145">\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944: \] 5061</span><span class="sxs-lookup"><span data-stu-id="39794-145">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="39794-146">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="39794-146">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="39794-147">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="39794-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="39794-148">Di seguito sono riportate alcune ragioni comuni per cui **test-CsDataConference** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="39794-148">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="39794-149">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="39794-149">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="39794-150">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="39794-150">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="39794-151">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="39794-151">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="39794-152">La possibilità di condurre una conferenza dati dipende dai criteri di conferenza che sono stati assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsDataConference** , che è il "mittente").</span><span class="sxs-lookup"><span data-stu-id="39794-152">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="39794-153">Se all'organizzatore non è consentito includere attività di collaborazione nella propria riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsDataConference** avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="39794-153">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="39794-154">Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="39794-154">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

