---
title: 'Lync Server 2013: verifica della capacità di un utente di accedere a Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71629cb844b8f65ab6f54c0d604fad0d152705d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="c0d61-102">Verifica della capacità di un utente di accedere a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0d61-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0d61-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c0d61-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0d61-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="c0d61-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c0d61-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="c0d61-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0d61-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="c0d61-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c0d61-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0d61-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0d61-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="c0d61-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c0d61-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c0d61-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c0d61-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="c0d61-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="c0d61-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c0d61-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c0d61-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0d61-112">Description</span></span>

<span data-ttu-id="c0d61-113">Il cmdlet Test-CsRegistration consente di verificare che gli utenti dell'organizzazione possano accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0d61-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="c0d61-114">Quando si esegue Test-CsRegistration, il cmdlet tenta di eseguire l'accesso a un utente di test a Lync Server e quindi, se ha esito positivo, disconnette l'utente di test dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c0d61-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="c0d61-115">Tutta la procedura viene eseguita senza alcuna interazione da parte degli utenti e senza che questi vengano coinvolti.</span><span class="sxs-lookup"><span data-stu-id="c0d61-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="c0d61-116">Si supponga, ad esempio, che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che dispone di un account Lync Server reale.</span><span class="sxs-lookup"><span data-stu-id="c0d61-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="c0d61-117">In questo caso, il test verrà eseguito senza coinvolgere il vero Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c0d61-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="c0d61-118">Quando l'account di test di Ken è disconnesso dal sistema, Ken è la persona che continuerà a essere connessa.</span><span class="sxs-lookup"><span data-stu-id="c0d61-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c0d61-119">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="c0d61-119">Running the test</span></span>

<span data-ttu-id="c0d61-120">È possibile eseguire il cmdlet Test-CsRegistration utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0d61-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="c0d61-121">Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo del pool di registrazione di Lync Server in fase di test.</span><span class="sxs-lookup"><span data-stu-id="c0d61-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="c0d61-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c0d61-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c0d61-123">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="c0d61-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="c0d61-124">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="c0d61-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="c0d61-125">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="c0d61-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c0d61-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="c0d61-126">Determining success or failure</span></span>

<span data-ttu-id="c0d61-127">Se l'utente specificato può accedere a (e quindi disconnettersi da) Lync Server, verrà visualizzato un output simile al seguente con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="c0d61-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c0d61-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c0d61-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c0d61-129">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="c0d61-129">Result : Success</span></span>

<span data-ttu-id="c0d61-130">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="c0d61-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="c0d61-131">Errore</span><span class="sxs-lookup"><span data-stu-id="c0d61-131">Error :</span></span>

<span data-ttu-id="c0d61-132">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="c0d61-132">Diagnosis :</span></span>

<span data-ttu-id="c0d61-133">Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="c0d61-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c0d61-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c0d61-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c0d61-135">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="c0d61-135">Result : Failure</span></span>

<span data-ttu-id="c0d61-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c0d61-136">Latency : 00:00:00</span></span>

<span data-ttu-id="c0d61-137">Errore: 404, non trovato</span><span class="sxs-lookup"><span data-stu-id="c0d61-137">Error : 404, Not Found</span></span>

<span data-ttu-id="c0d61-138">Diagnosi: ErrorCode = 1003, source = atl-cs-001. litwareinc. com, Reason = utente</span><span class="sxs-lookup"><span data-stu-id="c0d61-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="c0d61-139">non esiste</span><span class="sxs-lookup"><span data-stu-id="c0d61-139">not exist</span></span>

<span data-ttu-id="c0d61-140">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="c0d61-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="c0d61-141">Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="c0d61-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="c0d61-142">È possibile determinare se un indirizzo SIP è valido (e se l'utente assegnato l'indirizzo SIP è abilitato per Lync Server) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c0d61-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="c0d61-143">Se Test-CsRegistration ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="c0d61-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="c0d61-144">Quando viene incluso il parametro Verbose, Test-CsRegistration restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0d61-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="c0d61-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c0d61-145">For example:</span></span>

<span data-ttu-id="c0d61-146">VERBOse: attività di registrazione avviata.</span><span class="sxs-lookup"><span data-stu-id="c0d61-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="c0d61-147">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="c0d61-147">Sending Registration request:</span></span>

<span data-ttu-id="c0d61-148">FQDN di destinazione = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c0d61-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="c0d61-149">Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c0d61-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="c0d61-150">Porta di registrazione = 5061.</span><span class="sxs-lookup"><span data-stu-id="c0d61-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="c0d61-151">Il tipo di autenticazione ' attendibile ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="c0d61-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="c0d61-152">Eccezione ' l'endpoint non è in grado di effettuare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="c0d61-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="c0d61-153">Per un motivo specifico si è verificato l'errore durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="c0d61-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="c0d61-154">Stack di chiamate di eccezione: in Microsoft. Rtc. signaling. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="c0d61-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c0d61-155">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="c0d61-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="c0d61-156">Di seguito sono riportate alcune ragioni comuni per cui Test-CsRegistration potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="c0d61-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="c0d61-157">È stato specificato un account utente non corretto.</span><span class="sxs-lookup"><span data-stu-id="c0d61-157">You specified an incorrect user account.</span></span> <span data-ttu-id="c0d61-158">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c0d61-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="c0d61-159">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0d61-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="c0d61-160">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c0d61-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="c0d61-161">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0d61-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="c0d61-162">È stato specificato un pool di registrazione non corretto.</span><span class="sxs-lookup"><span data-stu-id="c0d61-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="c0d61-163">È possibile restituire i nomi FQDN dei pool di registrazione utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c0d61-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="c0d61-164">Il pool di registrazione non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="c0d61-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="c0d61-165">Provare a eseguire il ping del pool per verificare se risponde:</span><span class="sxs-lookup"><span data-stu-id="c0d61-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

