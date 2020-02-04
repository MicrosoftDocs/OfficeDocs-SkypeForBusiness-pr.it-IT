---
title: 'Lync Server 2013: test della chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="dfa4a-102">Test della chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfa4a-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa4a-103">_**Argomento Ultima modifica:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="dfa4a-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfa4a-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="dfa4a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dfa4a-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="dfa4a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa4a-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="dfa4a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dfa4a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfa4a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfa4a-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="dfa4a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dfa4a-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dfa4a-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="dfa4a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="dfa4a-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="dfa4a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dfa4a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfa4a-112">Description</span></span>

<span data-ttu-id="dfa4a-113">Il cmdlet **test-CsPersistentChatMessage** verifica che una coppia di utenti di test possa scambiare messaggi usando il servizio di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="dfa4a-114">A questo scopo, il cmdlet registra i due utenti in Lync Server 2013, connette gli utenti a una chat room persistente, scambia una coppia di messaggi, quindi chiude la chat room e disconnette i due utenti.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="dfa4a-115">Tieni presente che le chiamate a questo cmdlet avranno esito negativo se non hai creato nessuna chat room o se ai due account utente di test non viene assegnato un criterio di chat persistente che consente di accedere al servizio di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dfa4a-116">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="dfa4a-116">Running the test</span></span>

<span data-ttu-id="dfa4a-117">I comandi mostrati nell'esempio seguente consentono di verificare la capacità di una coppia di utenti\\(litwareinc Pilar\\e litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di scambiare i messaggi usando il servizio di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="dfa4a-118">A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziale di interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="dfa4a-119">Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credenziali risultante viene quindi archiviato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="dfa4a-120">Il secondo comando esegue la stessa operazione, questa volta restituendo un oggetto Credential per l'account Ken.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="dfa4a-121">Con gli oggetti credenziale disponibili, il terzo comando determina se questi due utenti possono accedere a Lync Server 2013 e scambiare messaggi usando la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="dfa4a-122">Per eseguire questa attività, il cmdlet **test-CsPersistentChatMessage** viene chiamato usando i parametri seguenti: TargetFqdn (il nome di dominio completo del pool di registrar); SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (l'oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (l'oggetto Windows PowerShell che contiene le credenziali per l'altro utente di test).</span><span class="sxs-lookup"><span data-stu-id="dfa4a-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dfa4a-123">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="dfa4a-123">Determining success or failure</span></span>

<span data-ttu-id="dfa4a-124">Se l'utente specificato ha un criterio di posizione valido, riceverai un output simile al seguente, con la proprietà Result contrassegnata come **riuscita**:</span><span class="sxs-lookup"><span data-stu-id="dfa4a-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="dfa4a-125">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dfa4a-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dfa4a-126">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="dfa4a-126">Result : Success</span></span>

<span data-ttu-id="dfa4a-127">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dfa4a-127">Latency : 00:00:00</span></span>

<span data-ttu-id="dfa4a-128">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="dfa4a-128">Error Message :</span></span>

<span data-ttu-id="dfa4a-129">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="dfa4a-129">Diagnosis :</span></span>

<span data-ttu-id="dfa4a-130">Se gli utenti specificati non possono scambiare messaggi usando il servizio chat persistente, il risultato verrà visualizzato come **errore**e verranno registrate altre informazioni nelle proprietà errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="dfa4a-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="dfa4a-131">AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo</span><span class="sxs-lookup"><span data-stu-id="dfa4a-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="dfa4a-132">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="dfa4a-132">domain name (FQDN).</span></span> <span data-ttu-id="dfa4a-133">Uso del numero di porta registrar predefinito.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-133">Using default Registrar port number.</span></span> <span data-ttu-id="dfa4a-134">Eccezione</span><span class="sxs-lookup"><span data-stu-id="dfa4a-134">Exception:</span></span>

<span data-ttu-id="dfa4a-135">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="dfa4a-136">a</span><span class="sxs-lookup"><span data-stu-id="dfa4a-136">at</span></span>

<span data-ttu-id="dfa4a-137">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="dfa4a-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="dfa4a-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="dfa4a-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="dfa4a-139">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dfa4a-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dfa4a-140">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="dfa4a-140">Result : Failure</span></span>

<span data-ttu-id="dfa4a-141">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dfa4a-141">Latency : 00:00:00</span></span>

<span data-ttu-id="dfa4a-142">Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa</span><span class="sxs-lookup"><span data-stu-id="dfa4a-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="dfa4a-143">non ha risposto correttamente dopo un periodo di tempo o</span><span class="sxs-lookup"><span data-stu-id="dfa4a-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="dfa4a-144">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="dfa4a-144">established connection failed because connected host has</span></span>

<span data-ttu-id="dfa4a-145">Impossibile rispondere \[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="dfa4a-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="dfa4a-146">Eccezione interna: tentativo di connessione non riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="dfa4a-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="dfa4a-147">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="dfa4a-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="dfa4a-148">l'ora o la connessione stabilita non è riuscita perché l'host connesso</span><span class="sxs-lookup"><span data-stu-id="dfa4a-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="dfa4a-149">non è riuscito a rispondere</span><span class="sxs-lookup"><span data-stu-id="dfa4a-149">has failed to respond</span></span>

<span data-ttu-id="dfa4a-150">\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="dfa4a-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="dfa4a-151">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="dfa4a-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dfa4a-152">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="dfa4a-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="dfa4a-153">Ecco alcuni motivi comuni per cui **test-CsPersistentChatMessage** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="dfa4a-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="dfa4a-154">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="dfa4a-155">Gli account di test necessari potrebbero non esistere o essere stati creati correttamente.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="dfa4a-156">Potrebbe essersi verificato un problema di rete che causa un ritardo imprevisto che ha superato il test.</span><span class="sxs-lookup"><span data-stu-id="dfa4a-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfa4a-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfa4a-157">See Also</span></span>


[<span data-ttu-id="dfa4a-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="dfa4a-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="dfa4a-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="dfa4a-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="dfa4a-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="dfa4a-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

