---
title: 'Lync Server 2013: test della configurazione del server LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8893964ce1982c67dc97ed93bca9ba19ec2f24e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536013"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="acf66-102">Test della configurazione del server LIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acf66-102">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acf66-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="acf66-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acf66-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="acf66-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="acf66-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="acf66-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acf66-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="acf66-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="acf66-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="acf66-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acf66-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="acf66-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="acf66-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="acf66-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="acf66-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="acf66-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="acf66-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="acf66-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="acf66-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="acf66-112">Description</span></span>

<span data-ttu-id="acf66-113">Il cmdlet Test-CsLisConfiguration verifica la possibilità di contattare il servizio Web LIS.</span><span class="sxs-lookup"><span data-stu-id="acf66-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="acf66-114">Se il servizio Web può essere contattato, il test sarà considerato un esito positivo, indipendentemente dal fatto che sia possibile trovare posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="acf66-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="acf66-115">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="acf66-115">Running the test</span></span>

<span data-ttu-id="acf66-116">È possibile eseguire il cmdlet Test-CsLisConfguration utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acf66-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="acf66-117">Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="acf66-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="acf66-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="acf66-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="acf66-119">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="acf66-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="acf66-120">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="acf66-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="acf66-121">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="acf66-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="acf66-122">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="acf66-122">Determining success or failure</span></span>

<span data-ttu-id="acf66-123">Se la LIS è configurata correttamente, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="acf66-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="acf66-124">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="acf66-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="acf66-125">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="acf66-125">liservice.svc</span></span>

<span data-ttu-id="acf66-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="acf66-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="acf66-127">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="acf66-127">Result : Success</span></span>

<span data-ttu-id="acf66-128">Latenza: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="acf66-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="acf66-129">Errore</span><span class="sxs-lookup"><span data-stu-id="acf66-129">Error :</span></span>

<span data-ttu-id="acf66-130">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="acf66-130">Diagnosis :</span></span>

<span data-ttu-id="acf66-131">Se l'utente specificato non è in grado di accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="acf66-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="acf66-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="acf66-132">TargetUri :</span></span>

<span data-ttu-id="acf66-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="acf66-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="acf66-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="acf66-134">Result : Failure</span></span>

<span data-ttu-id="acf66-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="acf66-135">Latency : 00:00:00</span></span>

<span data-ttu-id="acf66-136">Errore: 11004, il nome richiesto è valido ma nessun dato del richiesto</span><span class="sxs-lookup"><span data-stu-id="acf66-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="acf66-137">il tipo è stato trovato</span><span class="sxs-lookup"><span data-stu-id="acf66-137">type was found</span></span>

<span data-ttu-id="acf66-138">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="acf66-138">Diagnosis :</span></span>

<span data-ttu-id="acf66-139">Test-CsLisConfiguration: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="acf66-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="acf66-140">Ad esempio, nell'output precedente è inclusa la nota "Nessun cluster corrispondente trovato nella topologia".</span><span class="sxs-lookup"><span data-stu-id="acf66-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="acf66-141">Questo indica in genere un problema con il server perimetrale: l'LIS che utilizza il server perimetrale per connettersi al provider di servizi e convalidare gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="acf66-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="acf66-142">Se Test-CsLisConfiguration ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="acf66-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="acf66-143">Quando viene incluso il parametro Verbose, Test-CsLisConfiguration restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acf66-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="acf66-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="acf66-144">For example:</span></span>

<span data-ttu-id="acf66-145">Servizio informazioni percorso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="acf66-145">Calling Location Information Service.</span></span>

<span data-ttu-id="acf66-146">Percorso servizio = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="acf66-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="acf66-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="acf66-147">Subnet =</span></span>

<span data-ttu-id="acf66-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="acf66-148">BssId = 5</span></span>

<span data-ttu-id="acf66-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="acf66-149">ChassisId =</span></span>

<span data-ttu-id="acf66-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="acf66-150">PortId =</span></span>

<span data-ttu-id="acf66-151">PortIdSubType = tipo non definito</span><span class="sxs-lookup"><span data-stu-id="acf66-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="acf66-152">Mac</span><span class="sxs-lookup"><span data-stu-id="acf66-152">Mac</span></span>

<span data-ttu-id="acf66-153">Eccezione ' richiesta di servizio Web informazioni percorso non riuscita con un codice di risposta Item400'.</span><span class="sxs-lookup"><span data-stu-id="acf66-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="acf66-154">si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTrsnactions. Workflows. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="acf66-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="acf66-155">Se si esamina l'output precedente da vicino, si noterà che il cmdlet ha avuto esito negativo dopo la chiamata al servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="acf66-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="acf66-156">Uno dei parametri che sono stati utilizzati in tale chiamata è stato il seguente:</span><span class="sxs-lookup"><span data-stu-id="acf66-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="acf66-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="acf66-157">BssId = 5</span></span>

<span data-ttu-id="acf66-158">Questo non è un valore valido per l'identificatore del set di servizi di base (BssID).</span><span class="sxs-lookup"><span data-stu-id="acf66-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="acf66-159">Al contrario, un BssID dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="acf66-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="acf66-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="acf66-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="acf66-161">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="acf66-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="acf66-162">Di seguito sono riportate alcune ragioni comuni per cui Test-CsLisConfiguration potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="acf66-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="acf66-163">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="acf66-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="acf66-164">Come illustrato nell'esempio precedente, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="acf66-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="acf66-165">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="acf66-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

