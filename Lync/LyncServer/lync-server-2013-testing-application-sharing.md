---
title: 'Lync Server 2013: test della condivisione delle applicazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="b7fc9-102">Test della condivisione delle applicazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7fc9-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7fc9-103">_**Argomento Ultima modifica:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b7fc9-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7fc9-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="b7fc9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b7fc9-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="b7fc9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fc9-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="b7fc9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b7fc9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7fc9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fc9-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="b7fc9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b7fc9-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b7fc9-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="b7fc9-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b7fc9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b7fc9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7fc9-112">Description</span></span>

<span data-ttu-id="b7fc9-113">Il cmdlet **Test-CsASConference** verifica che una coppia di utenti di test possa partecipare a una conferenza online che include la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="b7fc9-114">A questo scopo, il cmdlet registra i due utenti con Lync Server 2013 e quindi usa uno degli account utente per creare una nuova conferenza che includa la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="b7fc9-115">Il cmdlet verifica quindi che il secondo utente sia in grado di partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b7fc9-116">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="b7fc9-116">Running the test</span></span>

<span data-ttu-id="b7fc9-117">Il comando mostrato nell'esempio 1 Verifica che una conferenza di condivisione delle applicazioni possa essere eseguita nel pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b7fc9-118">Questo comando presuppone che sia stata configurata una coppia di utenti di test per il pool specificato.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="b7fc9-119">Se non esistono utenti di test di questo tipo, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b7fc9-120">L'esempio 2 verifica la capacità del servizio di avvio join di partecipare a una conferenza di condivisione delle applicazioni nel pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b7fc9-121">Tieni presente che questo comando verifica solo il servizio stesso; non è necessario alcun dispositivo mobile per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="b7fc9-122">I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di\\utenti (litwareinc\\Pilar e litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di eseguire una conferenza di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="b7fc9-123">A questo scopo, il primo comando nell'esempio usa il cmdlet Get-Credential per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="b7fc9-124">Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziale risultante viene quindi archiviato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="b7fc9-125">Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="b7fc9-126">Con gli oggetti credenziale in mano, il terzo comando determina se questi due utenti possono accedere a Lync Server 2013 e condurre una conferenza di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="b7fc9-127">Per eseguire questa attività, viene chiamato il cmdlet **Test-CsASConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (l'oggetto Windows PowerShell che contiene le credenziali per l'altro utente di test).</span><span class="sxs-lookup"><span data-stu-id="b7fc9-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b7fc9-128">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="b7fc9-128">Determining success or failure</span></span>

<span data-ttu-id="b7fc9-129">Se la condivisione delle applicazioni è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="b7fc9-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b7fc9-130">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7fc9-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7fc9-131">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="b7fc9-131">Result : Success</span></span>

<span data-ttu-id="b7fc9-132">Latenza: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="b7fc9-132">Latency : 00:00:01</span></span>

<span data-ttu-id="b7fc9-133">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="b7fc9-133">Error Message :</span></span>

<span data-ttu-id="b7fc9-134">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="b7fc9-134">Diagnosis :</span></span>

<span data-ttu-id="b7fc9-135">Se gli utenti specificati non possono condividere le applicazioni, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="b7fc9-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b7fc9-136">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7fc9-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7fc9-137">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="b7fc9-137">Result : Failure</span></span>

<span data-ttu-id="b7fc9-138">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b7fc9-138">Latency : 00:00:00</span></span>

<span data-ttu-id="b7fc9-139">Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa</span><span class="sxs-lookup"><span data-stu-id="b7fc9-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b7fc9-140">non ha risposto correttamente dopo un periodo di tempo o</span><span class="sxs-lookup"><span data-stu-id="b7fc9-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b7fc9-141">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="b7fc9-141">established connection failed because connected host has</span></span>

<span data-ttu-id="b7fc9-142">Impossibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b7fc9-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b7fc9-143">Eccezione interna: tentativo di connessione non riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="b7fc9-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b7fc9-144">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="b7fc9-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b7fc9-145">l'ora o la connessione stabilita non è riuscita perché l'host connesso</span><span class="sxs-lookup"><span data-stu-id="b7fc9-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b7fc9-146">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b7fc9-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b7fc9-147">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="b7fc9-147">Diagnosis :</span></span>

<span data-ttu-id="b7fc9-148">Ad esempio, l'output precedente include la nota "la parte connessa non risponde in modo corretto" che in genere indica un problema con il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b7fc9-149">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="b7fc9-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="b7fc9-150">Ecco alcuni motivi comuni per cui **Test-CsASConference** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="b7fc9-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="b7fc9-151">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b7fc9-152">Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b7fc9-153">Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b7fc9-154">Questo comando non riuscirà se agli utenti di test è stato assegnato un criterio di conferenza che impedisce l'uso della condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="b7fc9-155">Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="b7fc9-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7fc9-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7fc9-156">See Also</span></span>


[<span data-ttu-id="b7fc9-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="b7fc9-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="b7fc9-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="b7fc9-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

