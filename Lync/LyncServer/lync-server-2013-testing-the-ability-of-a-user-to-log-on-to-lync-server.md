---
title: 'Lync Server 2013: verifica della capacità di un utente di accedere a Lync Server'
description: 'Lync Server 2013: verifica della capacità di un utente di accedere a Lync Server.'
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
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556212"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="ec5f7-103">Verifica della capacità di un utente di accedere a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec5f7-103">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec5f7-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ec5f7-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec5f7-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ec5f7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ec5f7-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="ec5f7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec5f7-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="ec5f7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ec5f7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec5f7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec5f7-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ec5f7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ec5f7-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ec5f7-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="ec5f7-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ec5f7-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec5f7-113">Description</span></span>

<span data-ttu-id="ec5f7-114">Il cmdlet Test-CsRegistration consente di verificare che gli utenti dell'organizzazione possano accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-114">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="ec5f7-115">Quando si esegue Test-CsRegistration, il cmdlet tenta di eseguire l'accesso a un utente di test a Lync Server e quindi, se ha esito positivo, disconnette l'utente di test dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-115">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="ec5f7-116">Tutta la procedura viene eseguita senza alcuna interazione da parte degli utenti e senza che questi vengano coinvolti.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-116">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="ec5f7-117">Si supponga, ad esempio, che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che dispone di un account Lync Server reale.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-117">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="ec5f7-118">In questo caso, il test verrà eseguito senza coinvolgere il vero Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-118">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="ec5f7-119">Quando l'account di test di Ken è disconnesso dal sistema, Ken è la persona che continuerà a essere connessa.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-119">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ec5f7-120">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="ec5f7-120">Running the test</span></span>

<span data-ttu-id="ec5f7-121">È possibile eseguire il cmdlet Test-CsRegistration utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-121">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="ec5f7-122">Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo del pool di registrazione di Lync Server in fase di test.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="ec5f7-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-123">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ec5f7-124">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="ec5f7-125">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="ec5f7-126">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="ec5f7-126">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ec5f7-127">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ec5f7-127">Determining success or failure</span></span>

<span data-ttu-id="ec5f7-128">Se l'utente specificato può accedere a (e quindi disconnettersi da) Lync Server, verrà visualizzato un output simile al seguente con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="ec5f7-128">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ec5f7-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec5f7-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec5f7-130">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="ec5f7-130">Result : Success</span></span>

<span data-ttu-id="ec5f7-131">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="ec5f7-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="ec5f7-132">Errore</span><span class="sxs-lookup"><span data-stu-id="ec5f7-132">Error :</span></span>

<span data-ttu-id="ec5f7-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ec5f7-133">Diagnosis :</span></span>

<span data-ttu-id="ec5f7-134">Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-134">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ec5f7-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec5f7-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec5f7-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="ec5f7-136">Result : Failure</span></span>

<span data-ttu-id="ec5f7-137">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec5f7-137">Latency : 00:00:00</span></span>

<span data-ttu-id="ec5f7-138">Errore: 404, non trovato</span><span class="sxs-lookup"><span data-stu-id="ec5f7-138">Error : 404, Not Found</span></span>

<span data-ttu-id="ec5f7-139">Diagnosi: ErrorCode = 1003, source = atl-cs-001. litwareinc. com, Reason = utente</span><span class="sxs-lookup"><span data-stu-id="ec5f7-139">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="ec5f7-140">non esiste</span><span class="sxs-lookup"><span data-stu-id="ec5f7-140">not exist</span></span>

<span data-ttu-id="ec5f7-141">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="ec5f7-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="ec5f7-142">Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-142">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="ec5f7-143">È possibile determinare se un indirizzo SIP è valido (e se l'utente assegnato l'indirizzo SIP è abilitato per Lync Server) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-143">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="ec5f7-144">Se Test-CsRegistration ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-144">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="ec5f7-145">Quando viene incluso il parametro Verbose, Test-CsRegistration restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-145">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ec5f7-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-146">For example:</span></span>

<span data-ttu-id="ec5f7-147">VERBOse: attività di registrazione avviata.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-147">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="ec5f7-148">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-148">Sending Registration request:</span></span>

<span data-ttu-id="ec5f7-149">FQDN di destinazione = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec5f7-149">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="ec5f7-150">Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec5f7-150">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="ec5f7-151">Porta di registrazione = 5061.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-151">Registrar Port = 5061.</span></span>

<span data-ttu-id="ec5f7-152">Il tipo di autenticazione ' attendibile ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-152">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="ec5f7-153">Eccezione ' l'endpoint non è in grado di effettuare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-153">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="ec5f7-154">Per un motivo specifico si è verificato l'errore durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-154">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="ec5f7-155">Stack di chiamate di eccezione: in Microsoft. Rtc. signaling. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="ec5f7-155">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ec5f7-156">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="ec5f7-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="ec5f7-157">Di seguito sono riportate alcune ragioni comuni per cui Test-CsRegistration potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-157">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="ec5f7-158">È stato specificato un account utente non corretto.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-158">You specified an incorrect user account.</span></span> <span data-ttu-id="ec5f7-159">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ec5f7-160">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="ec5f7-161">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="ec5f7-162">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-162">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="ec5f7-163">È stato specificato un pool di registrazione non corretto.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-163">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="ec5f7-164">È possibile restituire i nomi FQDN dei pool di registrazione utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-164">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="ec5f7-165">Il pool di registrazione non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-165">The Registrar pool is currently not available.</span></span> <span data-ttu-id="ec5f7-166">Provare a eseguire il ping del pool per verificare se risponde:</span><span class="sxs-lookup"><span data-stu-id="ec5f7-166">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

