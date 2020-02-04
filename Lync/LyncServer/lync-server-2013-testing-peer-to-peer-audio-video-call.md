---
title: 'Lync Server 2013: test della chiamata audio/video peer-to-peer'
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
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="db9d4-102">Test della chiamata audio/video peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db9d4-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db9d4-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="db9d4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db9d4-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="db9d4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="db9d4-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="db9d4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db9d4-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="db9d4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="db9d4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db9d4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db9d4-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="db9d4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="db9d4-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="db9d4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="db9d4-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsP2PAV.</span><span class="sxs-lookup"><span data-stu-id="db9d4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="db9d4-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="db9d4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="db9d4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db9d4-112">Description</span></span>

<span data-ttu-id="db9d4-113">Test-CsP2PAV viene usato per determinare se una coppia di utenti di test può partecipare a una conversazione a/V peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="db9d4-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="db9d4-114">Per verificare questo scenario, il cmdlet si avvia effettuando la registrazione dei due utenti in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db9d4-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="db9d4-115">Supponendo che i due accessi abbiano successo, il primo utente invita quindi il secondo utente a partecipare a una chiamata A/V.</span><span class="sxs-lookup"><span data-stu-id="db9d4-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="db9d4-116">Il secondo utente accetta la chiamata, la connessione tra i due utenti viene testata e la chiamata viene terminata e gli utenti di test vengono disconnessi dal sistema.</span><span class="sxs-lookup"><span data-stu-id="db9d4-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="db9d4-117">Test-CsP2PAV non esegue effettivamente una chiamata A/V.</span><span class="sxs-lookup"><span data-stu-id="db9d4-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="db9d4-118">Le informazioni multimediali non vengono scambiate tra gli utenti di test.</span><span class="sxs-lookup"><span data-stu-id="db9d4-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="db9d4-119">Al contrario, il cmdlet verifica semplicemente che le connessioni appropriate possano essere effettuate e che i due utenti possano eseguire tale chiamata.</span><span class="sxs-lookup"><span data-stu-id="db9d4-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="db9d4-120">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="db9d4-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="db9d4-121">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="db9d4-121">Running the test</span></span>

<span data-ttu-id="db9d4-122">Il cmdlet Test-CsP2PAV può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db9d4-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="db9d4-123">Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="db9d4-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="db9d4-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="db9d4-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="db9d4-125">Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti credenziali di Lync Server (oggetti che contengono il nome dell'account e la password) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="db9d4-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="db9d4-126">È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsP2PAV:</span><span class="sxs-lookup"><span data-stu-id="db9d4-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="db9d4-127">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="db9d4-127">Determining success or failure</span></span>

<span data-ttu-id="db9d4-128">Se i due utenti di test possono completare una chiamata A/V peer-to-peer, riceverai un output simile a quello con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="db9d4-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="db9d4-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db9d4-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db9d4-130">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="db9d4-130">Result : Success</span></span>

<span data-ttu-id="db9d4-131">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="db9d4-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="db9d4-132">Errore</span><span class="sxs-lookup"><span data-stu-id="db9d4-132">Error :</span></span>

<span data-ttu-id="db9d4-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="db9d4-133">Diagnosis :</span></span>

<span data-ttu-id="db9d4-134">Se gli utenti di test non riescono a completare la chiamata, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="db9d4-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="db9d4-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db9d4-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db9d4-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="db9d4-136">Result : Failure</span></span>

<span data-ttu-id="db9d4-137">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="db9d4-137">Latency : 00:00:00</span></span>

<span data-ttu-id="db9d4-138">Errore: 480, temporaneamente non disponibile</span><span class="sxs-lookup"><span data-stu-id="db9d4-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="db9d4-139">Diagnosi: ErrorCode = 15030, source = atl-cs-001. litwareinc. com, Reason = failed</span><span class="sxs-lookup"><span data-stu-id="db9d4-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="db9d4-140">per instradare a Exchange Server</span><span class="sxs-lookup"><span data-stu-id="db9d4-140">to route to Exchange Server</span></span>

<span data-ttu-id="db9d4-141">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="db9d4-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="db9d4-142">Ad esempio, l'output precedente indica che il test non è riuscito perché non è stato possibile contattare il server di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="db9d4-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="db9d4-143">Questo messaggio di errore indica in genere un problema la configurazione della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="db9d4-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="db9d4-144">Se Test-CsP2PAV non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="db9d4-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="db9d4-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="db9d4-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="db9d4-146">Quando viene incluso il parametro Verbose, Test-CsP2PAV restituirà un account dettagliato di ogni azione provata mentre controlla la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db9d4-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="db9d4-147">Supponiamo ad esempio che il test non sia riuscito con la diagnosi seguente:</span><span class="sxs-lookup"><span data-stu-id="db9d4-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="db9d4-148">ErrorCode = 6003, source = atl-cs-001. litwareinc. com, Reason = non supportato dalla richiesta di finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="db9d4-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="db9d4-149">Se si riesegue Test-CsP2PAV e si include il parametro Verbose, si otterrà un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="db9d4-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="db9d4-150">VERBOse: è stata avviata l'attività "Register".</span><span class="sxs-lookup"><span data-stu-id="db9d4-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="db9d4-151">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="db9d4-151">Sending Registration request:</span></span>

<span data-ttu-id="db9d4-152">FQDN di destinazione = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db9d4-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="db9d4-153">Indirizzo SIP utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db9d4-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="db9d4-154">Porta registrar = 5062.</span><span class="sxs-lookup"><span data-stu-id="db9d4-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="db9d4-155">Viene selezionato il tipo di autenticazione "IWA".</span><span class="sxs-lookup"><span data-stu-id="db9d4-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="db9d4-156">Eccezione "l'endpoint non è stato in grado di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="db9d4-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="db9d4-157">Vedere il ErrorCode per un motivo specifico.</span><span class="sxs-lookup"><span data-stu-id="db9d4-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="db9d4-158">si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflows. STP2PAVWorkflow.</span><span class="sxs-lookup"><span data-stu-id="db9d4-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="db9d4-159">Anche se potrebbe non essere immediatamente evidente, se esamini attentamente l'output vedrai che è stata specificata una porta di registrazione non corretta (porta 5062).</span><span class="sxs-lookup"><span data-stu-id="db9d4-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="db9d4-160">A sua volta, il test ha causato un errore.</span><span class="sxs-lookup"><span data-stu-id="db9d4-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="db9d4-161">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="db9d4-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="db9d4-162">Ecco alcuni motivi comuni per cui Test-CsP2PAV potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="db9d4-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="db9d4-163">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="db9d4-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="db9d4-164">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="db9d4-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="db9d4-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="db9d4-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="db9d4-166">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db9d4-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="db9d4-167">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="db9d4-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="db9d4-168">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db9d4-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

