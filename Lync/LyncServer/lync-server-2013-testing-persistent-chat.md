---
title: 'Lync Server 2013: testing chat persistente'
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
ms.openlocfilehash: ee9869d5e7a5e3a48451478de334ee656543f6f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="18325-102">Test della chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18325-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18325-103">_**Ultimo argomento modificato:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="18325-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18325-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="18325-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="18325-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="18325-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18325-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="18325-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="18325-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18325-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18325-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="18325-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="18325-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="18325-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="18325-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="18325-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="18325-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="18325-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="18325-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18325-112">Description</span></span>

<span data-ttu-id="18325-113">Il cmdlet **test-CsPersistentChatMessage** verifica che una coppia di utenti di test sia in grado di scambiare messaggi utilizzando il servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="18325-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="18325-114">A tale scopo, il cmdlet registra i due utenti su Lync Server 2013, connette gli utenti a una chat room persistente, scambia una coppia di messaggi, quindi esce dalla chat room e disconnette i due utenti.</span><span class="sxs-lookup"><span data-stu-id="18325-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="18325-115">Si noti che le chiamate a questo cmdlet avranno esito negativo se non sono state create chat room o se ai due account utente di test non viene assegnato un criterio di Persistent Chat che consente di accedere al servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="18325-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="18325-116">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="18325-116">Running the test</span></span>

<span data-ttu-id="18325-117">Nei comandi riportati nell'esempio seguente viene verificata la capacità di una coppia di utenti (\\litwareinc Pilar e\\litwareinc kenmyer) di accedere a Lync Server 2013 e quindi di scambiare i messaggi utilizzando il servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="18325-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="18325-118">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="18325-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="18325-119">Poiché il nome di accesso, litwareinc\\Pilar, è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account di Pilar Ackerman. L'oggetto credentials risultante viene quindi memorizzato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="18325-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="18325-120">Il secondo comando effettua la stessa operazione, questa volta restituendo un oggetto credenziali per l'account Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="18325-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="18325-121">Con gli oggetti Credential disponibili, il terzo comando determina se i due utenti possono accedere a Lync Server 2013 e scambiare messaggi utilizzando la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="18325-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="18325-122">Per eseguire questa attività, il cmdlet **test-CsPersistentChatMessage** viene chiamato utilizzando i seguenti parametri: TargetFqdn (il nome di dominio completo del pool di registrazione). SenderSipAddress (l'indirizzo SIP per il primo utente di test); SenderCredential (oggetto Windows PowerShell che contiene le credenziali per lo stesso utente); ReceiverSipAddress (l'indirizzo SIP per l'altro utente di test); e ReceiverCredential (l'oggetto di Windows PowerShell contenente le credenziali per l'altro utente di test).</span><span class="sxs-lookup"><span data-stu-id="18325-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="18325-123">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="18325-123">Determining success or failure</span></span>

<span data-ttu-id="18325-124">Se l'utente specificato ha un criterio di percorso valido, riceverà un output simile al seguente, con la proprietà Result contrassegnata come **Success**:</span><span class="sxs-lookup"><span data-stu-id="18325-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="18325-125">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="18325-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="18325-126">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="18325-126">Result : Success</span></span>

<span data-ttu-id="18325-127">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="18325-127">Latency : 00:00:00</span></span>

<span data-ttu-id="18325-128">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="18325-128">Error Message :</span></span>

<span data-ttu-id="18325-129">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="18325-129">Diagnosis :</span></span>

<span data-ttu-id="18325-130">Se gli utenti specificati non sono in grado di scambiare messaggi utilizzando il servizio chat persistente, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="18325-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="18325-131">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="18325-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="18325-132">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="18325-132">domain name (FQDN).</span></span> <span data-ttu-id="18325-133">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="18325-133">Using default Registrar port number.</span></span> <span data-ttu-id="18325-134">Eccezione</span><span class="sxs-lookup"><span data-stu-id="18325-134">Exception:</span></span>

<span data-ttu-id="18325-135">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="18325-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="18325-136">a</span><span class="sxs-lookup"><span data-stu-id="18325-136">at</span></span>

<span data-ttu-id="18325-137">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="18325-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="18325-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="18325-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="18325-139">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="18325-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="18325-140">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="18325-140">Result : Failure</span></span>

<span data-ttu-id="18325-141">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="18325-141">Latency : 00:00:00</span></span>

<span data-ttu-id="18325-142">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="18325-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="18325-143">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="18325-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="18325-144">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="18325-144">established connection failed because connected host has</span></span>

<span data-ttu-id="18325-145">Impossibile rispondere \[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="18325-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="18325-146">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="18325-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="18325-147">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="18325-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="18325-148">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="18325-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="18325-149">non è stato in grado di rispondere</span><span class="sxs-lookup"><span data-stu-id="18325-149">has failed to respond</span></span>

<span data-ttu-id="18325-150">\[2001:4898: E8: f39e: 5c9a: AD83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="18325-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="18325-151">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="18325-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="18325-152">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="18325-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="18325-153">Di seguito sono riportate alcune ragioni comuni per cui **test-CsPersistentChatMessage** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="18325-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="18325-154">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="18325-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="18325-155">Gli account di prova necessari potrebbero non esistere o essere stati creati correttamente.</span><span class="sxs-lookup"><span data-stu-id="18325-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="18325-156">Potrebbe essere stato un problema di rete che causava un ritardo imprevisto che ha superato il test.</span><span class="sxs-lookup"><span data-stu-id="18325-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18325-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18325-157">See Also</span></span>


[<span data-ttu-id="18325-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="18325-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="18325-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="18325-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="18325-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="18325-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

