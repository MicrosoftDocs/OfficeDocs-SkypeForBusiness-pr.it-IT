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
ms.openlocfilehash: 3f3c99e9f10f98d93af73869d166c33a27e9ce18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="49641-102">Test della configurazione del server LIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49641-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49641-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="49641-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49641-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="49641-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="49641-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="49641-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49641-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="49641-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="49641-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49641-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49641-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="49641-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="49641-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="49641-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="49641-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="49641-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="49641-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49641-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="49641-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49641-112">Description</span></span>

<span data-ttu-id="49641-113">Il cmdlet Test-CsLisConfiguration verifica la possibilità di contattare il servizio Web LIS.</span><span class="sxs-lookup"><span data-stu-id="49641-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="49641-114">Se il servizio Web può essere contattato, il test verrà considerato un successo, indipendentemente dal fatto che sia possibile trovare posizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="49641-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="49641-115">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="49641-115">Running the test</span></span>

<span data-ttu-id="49641-116">Il cmdlet test-CsLisConfguration può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49641-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="49641-117">Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="49641-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="49641-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="49641-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="49641-119">Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password.</span><span class="sxs-lookup"><span data-stu-id="49641-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="49641-120">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="49641-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="49641-121">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="49641-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="49641-122">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="49641-122">Determining success or failure</span></span>

<span data-ttu-id="49641-123">Se la LIS è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **Success:**</span><span class="sxs-lookup"><span data-stu-id="49641-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="49641-124">TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="49641-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="49641-125">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="49641-125">liservice.svc</span></span>

<span data-ttu-id="49641-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49641-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="49641-127">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="49641-127">Result : Success</span></span>

<span data-ttu-id="49641-128">Latenza: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="49641-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="49641-129">Errore</span><span class="sxs-lookup"><span data-stu-id="49641-129">Error :</span></span>

<span data-ttu-id="49641-130">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="49641-130">Diagnosis :</span></span>

<span data-ttu-id="49641-131">Se l'utente specificato non riesce ad accedere o disconnettersi, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="49641-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="49641-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="49641-132">TargetUri :</span></span>

<span data-ttu-id="49641-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49641-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="49641-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="49641-134">Result : Failure</span></span>

<span data-ttu-id="49641-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="49641-135">Latency : 00:00:00</span></span>

<span data-ttu-id="49641-136">Errore: 11004, il nome richiesto è valido ma non contiene dati della richiesta</span><span class="sxs-lookup"><span data-stu-id="49641-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="49641-137">il tipo è stato trovato</span><span class="sxs-lookup"><span data-stu-id="49641-137">type was found</span></span>

<span data-ttu-id="49641-138">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="49641-138">Diagnosis :</span></span>

<span data-ttu-id="49641-139">Test-CsLisConfiguration: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="49641-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="49641-140">Ad esempio, l'output precedente include la nota "Nessun cluster corrispondente trovato nella topologia".</span><span class="sxs-lookup"><span data-stu-id="49641-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="49641-141">Questo indica in genere un problema con il server perimetrale: la LIS che usa il server perimetrale per connettersi al provider di servizi e convalidare gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="49641-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="49641-142">Se Test-CsLisConfiguration non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="49641-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="49641-143">Quando viene incluso il parametro Verbose, Test-CsLisConfiguration restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49641-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="49641-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="49641-144">For example:</span></span>

<span data-ttu-id="49641-145">Servizio informazioni sulla posizione chiamante.</span><span class="sxs-lookup"><span data-stu-id="49641-145">Calling Location Information Service.</span></span>

<span data-ttu-id="49641-146">Percorso servizio =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="49641-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="49641-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="49641-147">Subnet =</span></span>

<span data-ttu-id="49641-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="49641-148">BssId = 5</span></span>

<span data-ttu-id="49641-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="49641-149">ChassisId =</span></span>

<span data-ttu-id="49641-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="49641-150">PortId =</span></span>

<span data-ttu-id="49641-151">PortIdSubType = tipo non definito</span><span class="sxs-lookup"><span data-stu-id="49641-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="49641-152">Mac</span><span class="sxs-lookup"><span data-stu-id="49641-152">Mac</span></span>

<span data-ttu-id="49641-153">Eccezione "la richiesta di servizio Web di informazioni sulla posizione non è riuscita con un codice di risposta Item400".</span><span class="sxs-lookup"><span data-stu-id="49641-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="49641-154">si è verificato durante l'esecuzione del flusso di lavoro Microsoft. Rtc. SyntheticTrsnactions. Workflows. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="49641-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="49641-155">Se esamini attentamente l'output precedente, vedrai che il cmdlet non è riuscito dopo aver provato a chiamare il servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="49641-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="49641-156">Uno dei parametri usati in quella chiamata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="49641-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="49641-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="49641-157">BssId = 5</span></span>

<span data-ttu-id="49641-158">Questo non è un valore valido per l'identificatore del set di servizi di base (BssID).</span><span class="sxs-lookup"><span data-stu-id="49641-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="49641-159">Al contrario, un BssID dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49641-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="49641-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="49641-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="49641-161">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="49641-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="49641-162">Ecco alcuni motivi comuni per cui Test-CsLisConfiguration potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="49641-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="49641-163">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="49641-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="49641-164">Come illustrato nell'esempio precedente, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="49641-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="49641-165">Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="49641-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

