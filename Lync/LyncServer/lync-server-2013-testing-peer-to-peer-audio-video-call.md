---
title: 'Lync Server 2013: testing delle chiamate audio/video peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462442b7afea193866dc96aaf57085d780f43a39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="fb5de-102">Test delle chiamate audio/video peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5de-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb5de-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fb5de-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb5de-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="fb5de-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fb5de-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="fb5de-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5de-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="fb5de-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fb5de-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb5de-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5de-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="fb5de-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fb5de-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fb5de-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fb5de-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsP2PAV.</span><span class="sxs-lookup"><span data-stu-id="fb5de-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="fb5de-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fb5de-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fb5de-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb5de-112">Description</span></span>

<span data-ttu-id="fb5de-113">Test-CsP2PAV viene utilizzato per determinare se una coppia di utenti di test è in grado di partecipare a una conversazione a/V peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="fb5de-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="fb5de-114">Per testare questo scenario, il cmdlet inizia dalla registrazione dei due utenti a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb5de-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="fb5de-115">Presupponendo che i due accessi abbiano esito positivo, il primo utente invita quindi il secondo utente a partecipare a una chiamata A/V.</span><span class="sxs-lookup"><span data-stu-id="fb5de-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="fb5de-116">Dopo che il secondo utente ha accettato la chiamata, viene testata la connessione tra i due utenti e quindi la chiamata viene terminata e gli utenti di test vengono disconnessi dal sistema.</span><span class="sxs-lookup"><span data-stu-id="fb5de-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="fb5de-117">Test-CsP2PAV non esegue effettivamente una chiamata A/V.</span><span class="sxs-lookup"><span data-stu-id="fb5de-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="fb5de-118">Le informazioni multimediali non vengono scambiate tra gli utenti di test.</span><span class="sxs-lookup"><span data-stu-id="fb5de-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="fb5de-119">Al contrario, il cmdlet verifica solo che è possibile effettuare le connessioni appropriate e che i due utenti possono eseguire tale chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb5de-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="fb5de-120">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="fb5de-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fb5de-121">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="fb5de-121">Running the test</span></span>

<span data-ttu-id="fb5de-122">Il cmdlet Test-CsP2PAV può essere eseguito utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb5de-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="fb5de-123">Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="fb5de-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="fb5de-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fb5de-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="fb5de-125">Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Lync Server (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="fb5de-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="fb5de-126">Quando si chiama Test-CsP2PAV, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:</span><span class="sxs-lookup"><span data-stu-id="fb5de-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fb5de-127">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="fb5de-127">Determining success or failure</span></span>

<span data-ttu-id="fb5de-128">Se i due utenti di test possono completare una chiamata A/V peer-to-peer, verrà visualizzato un output simile al seguente con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="fb5de-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fb5de-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb5de-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fb5de-130">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="fb5de-130">Result : Success</span></span>

<span data-ttu-id="fb5de-131">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="fb5de-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="fb5de-132">Errore</span><span class="sxs-lookup"><span data-stu-id="fb5de-132">Error :</span></span>

<span data-ttu-id="fb5de-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="fb5de-133">Diagnosis :</span></span>

<span data-ttu-id="fb5de-134">Se gli utenti di test non sono in grado di completare la chiamata, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="fb5de-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fb5de-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb5de-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fb5de-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="fb5de-136">Result : Failure</span></span>

<span data-ttu-id="fb5de-137">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fb5de-137">Latency : 00:00:00</span></span>

<span data-ttu-id="fb5de-138">Errore: 480, temporaneamente non disponibile</span><span class="sxs-lookup"><span data-stu-id="fb5de-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="fb5de-139">Diagnosi: ErrorCode = 15030, source = atl-cs-001. litwareinc. com, Reason = failed</span><span class="sxs-lookup"><span data-stu-id="fb5de-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="fb5de-140">per instradare a Exchange Server</span><span class="sxs-lookup"><span data-stu-id="fb5de-140">to route to Exchange Server</span></span>

<span data-ttu-id="fb5de-141">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="fb5de-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="fb5de-142">Ad esempio, l'output precedente dichiara che il test non ha avuto esito positivo perché il server di Microsoft Exchange non è stato contattato.</span><span class="sxs-lookup"><span data-stu-id="fb5de-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="fb5de-143">Questo messaggio di errore indica in genere un problema relativo alla configurazione della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fb5de-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="fb5de-144">Se Test-CsP2PAV ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="fb5de-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="fb5de-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="fb5de-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="fb5de-146">Quando viene incluso il parametro Verbose, Test-CsP2PAV restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb5de-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="fb5de-147">Si supponga, ad esempio, che il test non abbia avuto esito positivo con la diagnosi seguente:</span><span class="sxs-lookup"><span data-stu-id="fb5de-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="fb5de-148">ErrorCode = 6003, source = atl-cs-001. litwareinc. com, Reason = non supportato dalla richiesta di finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="fb5de-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="fb5de-149">Se si esegue nuovamente Test-CsP2PAV e si include il parametro Verbose, si otterrà un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fb5de-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="fb5de-150">VERBOse: attività di registrazione avviata.</span><span class="sxs-lookup"><span data-stu-id="fb5de-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="fb5de-151">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="fb5de-151">Sending Registration request:</span></span>

<span data-ttu-id="fb5de-152">FQDN di destinazione = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb5de-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="fb5de-153">Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb5de-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="fb5de-154">Porta di registrazione = 5062.</span><span class="sxs-lookup"><span data-stu-id="fb5de-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="fb5de-155">Il tipo di autenticazione ' IWA ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="fb5de-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="fb5de-156">Eccezione ' l'endpoint non è stato in grado di registrare.</span><span class="sxs-lookup"><span data-stu-id="fb5de-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="fb5de-157">Per motivi specifici, vedere ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="fb5de-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="fb5de-158">si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflows. STP2PAVWorkflow.</span><span class="sxs-lookup"><span data-stu-id="fb5de-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="fb5de-159">Anche se potrebbe non essere immediatamente evidente, se si esamina l'output con attenzione, si noterà che è stata specificata una porta di registrazione non corretta (porta 5062).</span><span class="sxs-lookup"><span data-stu-id="fb5de-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="fb5de-160">A sua incirca, ciò ha causato l'esito negativo del test.</span><span class="sxs-lookup"><span data-stu-id="fb5de-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fb5de-161">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="fb5de-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="fb5de-162">Di seguito sono riportate alcune ragioni comuni per cui Test-CsP2PAV potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="fb5de-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="fb5de-163">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="fb5de-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="fb5de-164">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fb5de-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="fb5de-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="fb5de-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="fb5de-166">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb5de-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="fb5de-167">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fb5de-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="fb5de-168">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb5de-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

