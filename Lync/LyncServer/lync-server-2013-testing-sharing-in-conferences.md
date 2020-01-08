---
title: 'Lync Server 2013: test della condivisione in conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="ccaa2-102">Test della condivisione in conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccaa2-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccaa2-103">_**Argomento Ultima modifica:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ccaa2-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccaa2-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ccaa2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ccaa2-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="ccaa2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccaa2-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="ccaa2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ccaa2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccaa2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccaa2-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ccaa2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ccaa2-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ccaa2-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsDataConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="ccaa2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="ccaa2-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccaa2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ccaa2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccaa2-112">Description</span></span>

<span data-ttu-id="ccaa2-113">In Lync Server 2013 una conferenza dati è una conferenza in cui vengono usate attività di collaborazione come la lavagna o le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="ccaa2-114">Il cmdlet **test-CsDataConference** consente di verificare che una coppia di utenti sia in grado di partecipare a una conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ccaa2-115">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ccaa2-115">Running the test</span></span>

<span data-ttu-id="ccaa2-116">Il comando mostrato nell'esempio 1 Verifica che una conferenza dati possa essere eseguita nel pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ccaa2-117">Questo comando presuppone che sia stata configurata una coppia di utenti di test per il pool specificato.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="ccaa2-118">Se non esistono utenti di test di questo tipo, il comando avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="ccaa2-119">I comandi mostrati nell'esempio 2 consentono di verificare la capacità di una coppia di\\utenti (litwareinc\\Pilar e litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di eseguire una conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="ccaa2-120">A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="ccaa2-121">Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziale risultante viene quindi archiviato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="ccaa2-122">Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="ccaa2-123">Con gli oggetti credenziale in mano, il terzo comando determina se questi due utenti possono accedere a Lync Server 2013 e condurre una conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="ccaa2-124">Per eseguire questa attività, viene chiamato il cmdlet **test-CsDataConference** , insieme ai parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (l'oggetto Windows PowerShell che contiene le credenziali per l'altro utente di test).</span><span class="sxs-lookup"><span data-stu-id="ccaa2-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ccaa2-125">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ccaa2-125">Determining success or failure</span></span>

<span data-ttu-id="ccaa2-126">Se i servizi di conferenza dati sono configurati correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="ccaa2-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ccaa2-127">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ccaa2-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ccaa2-128">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="ccaa2-128">Result : Success</span></span>

<span data-ttu-id="ccaa2-129">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ccaa2-129">Latency : 00:00:00</span></span>

<span data-ttu-id="ccaa2-130">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="ccaa2-130">Error Message :</span></span>

<span data-ttu-id="ccaa2-131">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ccaa2-131">Diagnosis :</span></span>

<span data-ttu-id="ccaa2-132">Se gli utenti specificati non possono usare la condivisione dei dati, il risultato verrà visualizzato come **errore**e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="ccaa2-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ccaa2-133">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ccaa2-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ccaa2-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="ccaa2-134">Result : Failure</span></span>

<span data-ttu-id="ccaa2-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ccaa2-135">Latency : 00:00:00</span></span>

<span data-ttu-id="ccaa2-136">Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa</span><span class="sxs-lookup"><span data-stu-id="ccaa2-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ccaa2-137">non ha risposto correttamente dopo un periodo di tempo o</span><span class="sxs-lookup"><span data-stu-id="ccaa2-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ccaa2-138">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="ccaa2-138">established connection failed because connected host has</span></span>

<span data-ttu-id="ccaa2-139">Impossibile rispondere \[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="ccaa2-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="ccaa2-140">Eccezione interna: tentativo di connessione non riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="ccaa2-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ccaa2-141">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="ccaa2-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ccaa2-142">l'ora o la connessione stabilita non è riuscita perché l'host connesso</span><span class="sxs-lookup"><span data-stu-id="ccaa2-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ccaa2-143">non è riuscito a rispondere</span><span class="sxs-lookup"><span data-stu-id="ccaa2-143">has failed to respond</span></span>

<span data-ttu-id="ccaa2-144">\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="ccaa2-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="ccaa2-145">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ccaa2-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ccaa2-146">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="ccaa2-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="ccaa2-147">Ecco alcuni motivi comuni per cui **test-CsDataConference** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ccaa2-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="ccaa2-148">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ccaa2-149">Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ccaa2-150">Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ccaa2-151">La possibilità di eseguire una conferenza dati dipende dai criteri di conferenza assegnati all'utente che ha organizzato la conferenza (nel caso del cmdlet **test-CsDataConference** , ovvero il "mittente").</span><span class="sxs-lookup"><span data-stu-id="ccaa2-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="ccaa2-152">Se l'organizzatore non è autorizzato ad includere attività di collaborazione nella riunione, ad esempio se la proprietà EnableDataCollaboration è impostata su false, il cmdlet **test-CsDataConference** non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="ccaa2-153">Questo comando avrà esito negativo se il server perimetrale non è configurato correttamente o non è stato ancora distribuito.</span><span class="sxs-lookup"><span data-stu-id="ccaa2-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

