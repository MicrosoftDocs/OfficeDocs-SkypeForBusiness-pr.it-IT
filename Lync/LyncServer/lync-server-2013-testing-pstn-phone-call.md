---
title: 'Lync Server 2013: test di chiamata telefonica PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8095b4b0bb6aa4e6920d291c3fde3885ae6bfb03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="995dd-102">Test di chiamata telefonica PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="995dd-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="995dd-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="995dd-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="995dd-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="995dd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="995dd-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="995dd-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995dd-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="995dd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="995dd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="995dd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="995dd-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="995dd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="995dd-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="995dd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="995dd-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="995dd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="995dd-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="995dd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="995dd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="995dd-112">Description</span></span>

<span data-ttu-id="995dd-113">Il cmdlet Test-CsPstnOutboundCall verifica la possibilità di un utente di effettuare una chiamata a un numero di telefono situato nella rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="995dd-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="995dd-114">Quando si esegue Test-CsPstnOutboundCall, il cmdlet tenta prima di tutto di registrare l'utente di test in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="995dd-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="995dd-115">Se l'accesso viene eseguito correttamente, il cmdlet tenterà di effettuare una chiamata telefonica attraverso il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="995dd-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="995dd-116">Questa chiamata telefonica verrà eseguita tramite il dial plan, il criterio vocale e altri criteri e impostazioni assegnati all'account di test.</span><span class="sxs-lookup"><span data-stu-id="995dd-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="995dd-117">Quando la chiamata viene risolta, il cmdlet invia codici DTMF (Dual-Tone Multi-Frequency) tramite la rete per verificare la connettività multimediale.</span><span class="sxs-lookup"><span data-stu-id="995dd-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="995dd-118">Durante l'esecuzione del test, Test-CsPstnOutboundCall effettuerà una chiamata telefonica effettiva: il telefono di destinazione suonerà e dovrà rispondere affinché il test abbia successo.</span><span class="sxs-lookup"><span data-stu-id="995dd-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="995dd-119">Anche questa chiamata deve essere terminata manualmente dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="995dd-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="995dd-120">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="995dd-120">Running the test</span></span>

<span data-ttu-id="995dd-121">Il cmdlet Test-CsPstnOutboundCall può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="995dd-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="995dd-122">Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare e il numero di telefono PSTN che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="995dd-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="995dd-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="995dd-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="995dd-124">Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password.</span><span class="sxs-lookup"><span data-stu-id="995dd-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="995dd-125">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsPstnOutboundCall:</span><span class="sxs-lookup"><span data-stu-id="995dd-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="995dd-126">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="995dd-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="995dd-127">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="995dd-127">Determining success or failure</span></span>

<span data-ttu-id="995dd-128">Se l'utente specificato può effettuare la chiamata e se la chiamata viene risolta, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="995dd-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="995dd-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="995dd-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="995dd-130">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="995dd-130">Result : Success</span></span>

<span data-ttu-id="995dd-131">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="995dd-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="995dd-132">Errore</span><span class="sxs-lookup"><span data-stu-id="995dd-132">Error :</span></span>

<span data-ttu-id="995dd-133">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="995dd-133">Diagnosis :</span></span>

<span data-ttu-id="995dd-134">Se l'utente specificato non può effettuare la chiamata o se la chiamata non viene risolta, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="995dd-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="995dd-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="995dd-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="995dd-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="995dd-136">Result : Failure</span></span>

<span data-ttu-id="995dd-137">Latenza: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="995dd-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="995dd-138">Errore: 403, Forbidden</span><span class="sxs-lookup"><span data-stu-id="995dd-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="995dd-139">Diagnosi: ErrorCode = 12001, source = atl-cs-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="995dd-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="995dd-140">Il criterio non contiene l'utilizzo della route telefonica</span><span class="sxs-lookup"><span data-stu-id="995dd-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="995dd-141">L'output precedente dichiara che il test non è riuscito perché il criterio vocale assegnato all'utente specificato non include un uso del telefono.</span><span class="sxs-lookup"><span data-stu-id="995dd-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="995dd-142">(Gli usi telefonici collegano i criteri vocali alle route vocali.</span><span class="sxs-lookup"><span data-stu-id="995dd-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="995dd-143">Senza un criterio vocale e una route vocale corrispondente non è possibile effettuare chiamate tramite la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="995dd-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="995dd-144">Se Test-CsPstnOutboundCall non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="995dd-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="995dd-145">Quando viene incluso il parametro Verbose, Test-CsPstnOutboundCall restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="995dd-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="995dd-146">Ad esempio, questo output indica che i problemi di rete impediscono una connessione con PSTN:</span><span class="sxs-lookup"><span data-stu-id="995dd-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="995dd-147">Creazione di videochiamata audio in ' SIP: + 12065551219@litwareinc. com; user = phone '.</span><span class="sxs-lookup"><span data-stu-id="995dd-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="995dd-148">È stata ricevuta una risposta di 404 (non trovata) dalla rete e l'operazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="995dd-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="995dd-149">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="995dd-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="995dd-150">Ecco alcuni motivi comuni per cui Test-CsPstnOutboundCall potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="995dd-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="995dd-151">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="995dd-151">You specified an invalid user account.</span></span> <span data-ttu-id="995dd-152">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="995dd-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="995dd-153">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="995dd-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="995dd-154">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="995dd-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="995dd-155">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="995dd-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="995dd-156">Il criterio vocale assegnato all'utente specificato non ha un uso PSTN valido.</span><span class="sxs-lookup"><span data-stu-id="995dd-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="995dd-157">Puoi determinare il criterio vocale assegnato a un utente usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="995dd-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="995dd-158">E quindi puoi determinare gli usi PSTN (se presenti) assegnati a tale criterio usando un comando simile al seguente, che recupera le informazioni sul criterio vocale per utente RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="995dd-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

