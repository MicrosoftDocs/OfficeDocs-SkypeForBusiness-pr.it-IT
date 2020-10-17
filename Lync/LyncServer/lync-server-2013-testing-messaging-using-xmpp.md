---
title: 'Lync Server 2013: test della messaggistica mediante XMPP'
description: 'Lync Server 2013: test della messaggistica mediante XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556302"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="16ca7-103">Test della messaggistica mediante XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16ca7-103">Testing messaging using XMPP in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16ca7-104">_**Ultimo argomento modificato:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="16ca7-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16ca7-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="16ca7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="16ca7-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="16ca7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16ca7-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="16ca7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="16ca7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16ca7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16ca7-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="16ca7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="16ca7-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="16ca7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="16ca7-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="16ca7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="16ca7-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="16ca7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="16ca7-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16ca7-113">Description</span></span>

<span data-ttu-id="16ca7-114">Extensible Messaging and Presence Protocol (XMPP) è un protocollo di comunicazioni standard (basato su XML) utilizzato per l'invio di messaggi su Internet.</span><span class="sxs-lookup"><span data-stu-id="16ca7-114">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="16ca7-115">XMPP è stato originariamente denominato Jabber ed è supportato da diverse applicazioni di comunicazione e messaggistica Internet, come Google Talk e chat di Facebook.</span><span class="sxs-lookup"><span data-stu-id="16ca7-115">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="16ca7-116">Il cmdlet **Test-CsXmppIM** verifica che un utente possa scambiare messaggi istantanei con un utente in una rete XMPP.</span><span class="sxs-lookup"><span data-stu-id="16ca7-116">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="16ca7-117">Tenere presente che, affinché il test venga eseguito correttamente, è necessario disporre di un indirizzo SIP valido per l'utente XMPP e l'indirizzo SIP deve trovarsi in una rete configurata come partner XMPP consentito.</span><span class="sxs-lookup"><span data-stu-id="16ca7-117">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="16ca7-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="16ca7-118">Running the test</span></span>

<span data-ttu-id="16ca7-119">Nell'esempio seguente vengono verificate le funzionalità di messaggistica istantanea XMPP per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="16ca7-119">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="16ca7-120">Questo comando funzionerà solo se gli utenti di test sono definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="16ca7-120">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="16ca7-121">Se necessario, il comando determinerà se il primo utente di test può inviare un messaggio istantaneo XMPP a un utente a cui è associato l'indirizzo SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="16ca7-121">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="16ca7-122">Se gli utenti di test non sono definiti, il comando avrà esito negativo perché non è in grado di individuare l'utente a cui eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="16ca7-122">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="16ca7-123">Se non sono stati definiti gli utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'utente che deve essere utilizzato dal comando quando si tenta di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="16ca7-123">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="16ca7-124">I comandi mostrati nell'esempio seguente verificano la capacità di un utente specifico (litwareinc \\ Pilar) di accedere per inviare un messaggio istantaneo XMPP all'utente adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="16ca7-124">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="16ca7-125">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet Get-Credential per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="16ca7-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="16ca7-126">Poiché il nome di accesso litwareinc \\ Pilar è stato incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Pilar Ackerman. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="16ca7-126">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="16ca7-127">Il secondo comando verifica quindi se l'utente può accedere al pool atl-cs-001.litwareinc.com e inviare il messaggio istantaneo XMPP.</span><span class="sxs-lookup"><span data-stu-id="16ca7-127">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="16ca7-128">Per eseguire questa attività, viene chiamato il cmdlet **test-CsXmppIm** , insieme a quattro parametri: TargetFqdn (il nome di dominio completo del pool di registrazione). Receiver (l'indirizzo SIP dell'utente a cui è indirizzato il messaggio); UserCredential (l'oggetto di Windows PowerShell che contiene le credenziali utente di Pilar Ackerman); e UserSipAddress (l'indirizzo SIP corrispondente alle credenziali utente fornite).</span><span class="sxs-lookup"><span data-stu-id="16ca7-128">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="16ca7-129">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="16ca7-129">Determining success or failure</span></span>

<span data-ttu-id="16ca7-130">Se la messaggistica istantanea XMPP è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="16ca7-130">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="16ca7-131">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="16ca7-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="16ca7-132">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="16ca7-132">Result : Success</span></span>

<span data-ttu-id="16ca7-133">Latenza: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="16ca7-133">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="16ca7-134">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="16ca7-134">Error Message :</span></span>

<span data-ttu-id="16ca7-135">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="16ca7-135">Diagnosis :</span></span>

<span data-ttu-id="16ca7-136">Se gli utenti specificati non possono utilizzare la messaggistica istantanea XMPP, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="16ca7-136">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="16ca7-137">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="16ca7-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="16ca7-138">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="16ca7-138">domain name (FQDN).</span></span> <span data-ttu-id="16ca7-139">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="16ca7-139">Using default Registrar port number.</span></span> <span data-ttu-id="16ca7-140">Eccezione</span><span class="sxs-lookup"><span data-stu-id="16ca7-140">Exception:</span></span>

<span data-ttu-id="16ca7-141">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="16ca7-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="16ca7-142">a</span><span class="sxs-lookup"><span data-stu-id="16ca7-142">at</span></span>

<span data-ttu-id="16ca7-143">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="16ca7-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="16ca7-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="16ca7-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="16ca7-145">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="16ca7-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="16ca7-146">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="16ca7-146">Result : Failure</span></span>

<span data-ttu-id="16ca7-147">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="16ca7-147">Latency : 00:00:00</span></span>

<span data-ttu-id="16ca7-148">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="16ca7-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="16ca7-149">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="16ca7-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="16ca7-150">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="16ca7-150">established connection failed because connected host has</span></span>

<span data-ttu-id="16ca7-151">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="16ca7-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="16ca7-152">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="16ca7-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="16ca7-153">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="16ca7-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="16ca7-154">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="16ca7-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="16ca7-155">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="16ca7-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="16ca7-156">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="16ca7-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="16ca7-157">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="16ca7-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="16ca7-158">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsXmppIM** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="16ca7-158">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="16ca7-159">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="16ca7-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="16ca7-160">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="16ca7-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="16ca7-161">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="16ca7-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="16ca7-162">Questo comando avrà esito negativo se la configurazione del gateway XMPP non è configurata correttamente o non è stata ancora distribuita.</span><span class="sxs-lookup"><span data-stu-id="16ca7-162">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16ca7-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16ca7-163">See Also</span></span>


[<span data-ttu-id="16ca7-164">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="16ca7-164">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

