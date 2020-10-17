---
title: 'Lync Server 2013: convalidare le conferenze audio/video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0bfeef1abcf7b5859c365b7c64b4fcc84f49ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503703"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="9f264-102">Convalidare le conferenze audio/video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f264-102">Validating audio/video conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f264-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9f264-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f264-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="9f264-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f264-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="9f264-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f264-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="9f264-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f264-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f264-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f264-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="9f264-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f264-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9f264-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f264-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsAVConference.</span><span class="sxs-lookup"><span data-stu-id="9f264-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="9f264-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f264-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f264-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f264-112">Description</span></span>

<span data-ttu-id="9f264-113">Il cmdlet Test-CsAVConference verifica se due utenti di test possono partecipare a una conferenza audio/video (A/V).</span><span class="sxs-lookup"><span data-stu-id="9f264-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="9f264-114">Quando viene eseguito il cmdlet, i due utenti vengono connessi al sistema.</span><span class="sxs-lookup"><span data-stu-id="9f264-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="9f264-115">Dopo aver eseguito l'accesso con esito positivo, il primo utente crea una conferenza A/V e quindi attende che il secondo utente partecipi alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="9f264-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="9f264-116">Dopo un breve scambio di dati, la conferenza viene eliminata e i due utenti vengono disconnessi.</span><span class="sxs-lookup"><span data-stu-id="9f264-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="9f264-117">Si noti che Test-CsAVConference non esegue una conferenza audio/video effettiva tra i due utenti di test.</span><span class="sxs-lookup"><span data-stu-id="9f264-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="9f264-118">Al contrario, il cmdlet verifica che i due utenti possano effettuare tutte le connessioni necessarie per condurre una conferenza.</span><span class="sxs-lookup"><span data-stu-id="9f264-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="9f264-119">Ulteriori esempi per questo comando sono disponibili in [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="9f264-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f264-120">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="9f264-120">Running the test</span></span>

<span data-ttu-id="9f264-121">È possibile eseguire il cmdlet Test-CsAVConference utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f264-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="9f264-122">Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="9f264-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9f264-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9f264-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9f264-124">Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="9f264-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="9f264-125">È quindi necessario includere gli oggetti Credentials e gli indirizzi SIP dei due account quando chiamano Test-CsAVConference:</span><span class="sxs-lookup"><span data-stu-id="9f264-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="9f264-126">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="9f264-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f264-127">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="9f264-127">Determining Success or Failure</span></span>

<span data-ttu-id="9f264-128">Se gli utenti specificati possono completare correttamente una conferenza audio/video, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="9f264-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9f264-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f264-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f264-130">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="9f264-130">Result : Success</span></span>

<span data-ttu-id="9f264-131">Latenza: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="9f264-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="9f264-132">Errore</span><span class="sxs-lookup"><span data-stu-id="9f264-132">Error :</span></span>

<span data-ttu-id="9f264-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="9f264-133">Diagnosis :</span></span>

<span data-ttu-id="9f264-134">Se gli utenti non riescono a completare la conferenza, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="9f264-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9f264-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f264-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f264-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="9f264-136">Result : Failure</span></span>

<span data-ttu-id="9f264-137">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f264-137">Latency : 00:00:00</span></span>

<span data-ttu-id="9f264-138">Errore: 404, non trovato</span><span class="sxs-lookup"><span data-stu-id="9f264-138">Error : 404, Not Found</span></span>

<span data-ttu-id="9f264-139">Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="9f264-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="9f264-140">Reason = URI di destinazione non abilitato per SIP o non</span><span class="sxs-lookup"><span data-stu-id="9f264-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="9f264-141">esiste.</span><span class="sxs-lookup"><span data-stu-id="9f264-141">exist.</span></span>

<span data-ttu-id="9f264-142">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="9f264-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9f264-143">Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché almeno uno dei due account utente non era valido, perché l'account non esiste o perché l'account non è stato abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f264-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="9f264-144">È possibile verificare l'esistenza dei due account di test e se sono stati abilitati per Lync Server, eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9f264-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="9f264-145">Se Test-CsAVConference ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="9f264-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="9f264-146">Quando viene incluso il parametro Verbose Test-CsAVConference restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità degli utenti specificati di partecipare a una conferenza AV.</span><span class="sxs-lookup"><span data-stu-id="9f264-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="9f264-147">Ad esempio, si supponga che il test abbia esito negativo e che venga ricevuta la seguente diagnosi:</span><span class="sxs-lookup"><span data-stu-id="9f264-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="9f264-148">ErrorCode = 1008, source = accessproxy. litwareinc. com, Reason = non è in grado di risolvere il record DNS SRV</span><span class="sxs-lookup"><span data-stu-id="9f264-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="9f264-149">Se si esegue di nuovo il test utilizzando il parametro Verbose, le informazioni dettagliate restituite includono un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9f264-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="9f264-150">VERBOse: attività di registrazione avviata.</span><span class="sxs-lookup"><span data-stu-id="9f264-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="9f264-151">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="9f264-151">Sending Registration request:</span></span>

<span data-ttu-id="9f264-152">FQDN di destinazione = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f264-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f264-153">Indirizzo SIP dell'utente = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f264-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="9f264-154">Porta di registrazione = 5061.</span><span class="sxs-lookup"><span data-stu-id="9f264-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="9f264-155">Il tipo di autenticazione ' attendibile ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="9f264-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="9f264-156">Attività' Register ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="9f264-156">'Register' activity started.</span></span>

<span data-ttu-id="9f264-157">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="9f264-157">Sending Registration request:</span></span>

<span data-ttu-id="9f264-158">FQDN di destinazione = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f264-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f264-159">Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f264-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="9f264-160">Porta di registrazione = 5061.</span><span class="sxs-lookup"><span data-stu-id="9f264-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="9f264-161">Il tipo di autenticazione ' attendibile ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="9f264-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="9f264-162">Eccezione ' l'endpoint non è stato in grado di registrare.</span><span class="sxs-lookup"><span data-stu-id="9f264-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="9f264-163">Per motivi specifici, vedere ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="9f264-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="9f264-164">si è verificato durante il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9f264-164">occurred during Workflow</span></span>

<span data-ttu-id="9f264-165">L'ultima riga di tale output indica che l'utente sip:kenmyer@litwareinc.com non è stato in grado di eseguire la registrazione con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f264-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="9f264-166">Questo significa che è necessario verificare che l'indirizzo SIP sip:kenmyer@litwareinc.com sia valido e che l'utente associato sia abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f264-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f264-167">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="9f264-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="9f264-168">Di seguito sono riportate alcune ragioni comuni per cui Test-CsAVConference potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="9f264-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="9f264-169">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="9f264-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="9f264-170">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9f264-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9f264-171">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f264-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9f264-172">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9f264-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9f264-173">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f264-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

