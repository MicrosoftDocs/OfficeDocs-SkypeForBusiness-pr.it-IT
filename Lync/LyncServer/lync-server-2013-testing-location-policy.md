---
title: 'Lync Server 2013: criteri posizione test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="66cf2-102">Test dei criteri di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66cf2-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66cf2-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="66cf2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66cf2-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="66cf2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="66cf2-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="66cf2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cf2-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="66cf2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="66cf2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66cf2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cf2-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="66cf2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="66cf2-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="66cf2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="66cf2-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="66cf2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="66cf2-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="66cf2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="66cf2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66cf2-112">Description</span></span>

<span data-ttu-id="66cf2-113">Il cmdlet Test-CsLocationPolicy verifica che un criterio di posizione venga assegnato a un utente.</span><span class="sxs-lookup"><span data-stu-id="66cf2-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="66cf2-114">Il criterio di posizione viene usato per applicare le impostazioni relative alla funzionalità E9-1-1 e alla posizione del client.</span><span class="sxs-lookup"><span data-stu-id="66cf2-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="66cf2-115">I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, se la risposta è "Sì", qual è il comportamento di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="66cf2-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="66cf2-116">Ad esempio, è possibile usare i criteri di posizione per definire il numero che compone una chiamata di emergenza (911 negli Stati Uniti), se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="66cf2-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="66cf2-117">È possibile testare i criteri di posizione per gli utenti o le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="66cf2-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="66cf2-118">Se si esegue il test in una subnet (specificando un valore per il parametro subnet), il cmdlet tenterà di risolvere i criteri di posizione per la subnet.</span><span class="sxs-lookup"><span data-stu-id="66cf2-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="66cf2-119">Se alla subnet non viene assegnato alcun criterio di posizione, verranno recuperati i criteri di posizione per l'utente configurato.</span><span class="sxs-lookup"><span data-stu-id="66cf2-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="66cf2-120">Se i criteri di subnet vengono recuperati correttamente, l'output includerà un valore LocationPolicyTagID che inizia con subnet-tagid.</span><span class="sxs-lookup"><span data-stu-id="66cf2-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="66cf2-121">Se non è stato trovato un criterio di posizione per la subnet, LocationPolicyTagID inizierà con User-tagid.</span><span class="sxs-lookup"><span data-stu-id="66cf2-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="66cf2-122">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="66cf2-122">Running the test</span></span>

<span data-ttu-id="66cf2-123">Il cmdlet Test-CsLocationPolicy può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66cf2-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="66cf2-124">Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="66cf2-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="66cf2-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="66cf2-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="66cf2-126">Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password.</span><span class="sxs-lookup"><span data-stu-id="66cf2-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="66cf2-127">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="66cf2-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="66cf2-128">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="66cf2-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="66cf2-129">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="66cf2-129">Determining success or failure</span></span>

<span data-ttu-id="66cf2-130">Se l'utente specificato ha un criterio di posizione valido, riceverai un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="66cf2-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="66cf2-131">EnhancedEmergencyServicesEnabled: vero</span><span class="sxs-lookup"><span data-stu-id="66cf2-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="66cf2-132">LocationPolicyTagID: utente-TagId</span><span class="sxs-lookup"><span data-stu-id="66cf2-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="66cf2-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66cf2-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="66cf2-134">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="66cf2-134">Result : Success</span></span>

<span data-ttu-id="66cf2-135">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="66cf2-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="66cf2-136">Errore</span><span class="sxs-lookup"><span data-stu-id="66cf2-136">Error :</span></span>

<span data-ttu-id="66cf2-137">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="66cf2-137">Diagnosis :</span></span>

<span data-ttu-id="66cf2-138">Se non è possibile trovare un criterio di posizione valido per l'utente specificato, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="66cf2-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="66cf2-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66cf2-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="66cf2-140">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="66cf2-140">Result : Failure</span></span>

<span data-ttu-id="66cf2-141">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="66cf2-141">Latency : 00:00:00</span></span>

<span data-ttu-id="66cf2-142">Errore: 404, non trovato</span><span class="sxs-lookup"><span data-stu-id="66cf2-142">Error : 404, Not Found</span></span>

<span data-ttu-id="66cf2-143">Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="66cf2-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="66cf2-144">Reason = URI di destinazione non abilitato per SIP o non</span><span class="sxs-lookup"><span data-stu-id="66cf2-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="66cf2-145">esiste.</span><span class="sxs-lookup"><span data-stu-id="66cf2-145">exist.</span></span>

<span data-ttu-id="66cf2-146">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="66cf2-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="66cf2-147">L'output precedente indica che il test non è riuscito perché l'utente specificato non è valido: l'account non esiste oppure l'utente non è stato abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66cf2-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="66cf2-148">È possibile verificare la validità di un account e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66cf2-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="66cf2-149">Se Test-CsLocationPolicy non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="66cf2-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="66cf2-150">Quando viene incluso il parametro Verbose, Test-CsLocationPolicy restituirà un account dettagliato di ogni azione provata durante la verifica dei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="66cf2-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="66cf2-151">Ad esempio, questo output indica che Lync Server non è in grado di accedere all'utente di test, probabilmente perché è stata specificata una password non valida:</span><span class="sxs-lookup"><span data-stu-id="66cf2-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="66cf2-152">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="66cf2-152">Sending Registration request :</span></span>

<span data-ttu-id="66cf2-153">FQDN di destinazione = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66cf2-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="66cf2-154">Indirizzo SIP utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66cf2-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="66cf2-155">Porta registrar = 5061</span><span class="sxs-lookup"><span data-stu-id="66cf2-155">Registrar Port = 5061</span></span>

<span data-ttu-id="66cf2-156">Viene selezionato il tipo di autenticazione "IWA".</span><span class="sxs-lookup"><span data-stu-id="66cf2-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="66cf2-157">Hit di registrazione su SIP/atl-cs-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="66cf2-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="66cf2-158">Attività "Register" completata in "0,0601795" secs.</span><span class="sxs-lookup"><span data-stu-id="66cf2-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="66cf2-159">Eccezione ' il log-in è stato negato.</span><span class="sxs-lookup"><span data-stu-id="66cf2-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="66cf2-160">Verificare che vengano usate le credenziali corrette e che l'account sia attivo.</span><span class="sxs-lookup"><span data-stu-id="66cf2-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="66cf2-161">si è verificato durante il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="66cf2-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="66cf2-162">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="66cf2-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="66cf2-163">Ecco alcuni motivi comuni per cui Test-CsLocationPolicy potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="66cf2-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="66cf2-164">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="66cf2-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="66cf2-165">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66cf2-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="66cf2-166">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66cf2-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="66cf2-167">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66cf2-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="66cf2-168">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66cf2-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

