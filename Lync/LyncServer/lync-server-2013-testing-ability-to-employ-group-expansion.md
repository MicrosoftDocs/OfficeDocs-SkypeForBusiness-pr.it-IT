---
title: "Lync Server 2013: test della capacità di usare l'espansione del gruppo"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="91f91-102">Possibilità di test per l'utilizzo dell'espansione di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91f91-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91f91-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="91f91-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91f91-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="91f91-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="91f91-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="91f91-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91f91-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="91f91-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="91f91-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91f91-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91f91-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="91f91-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="91f91-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="91f91-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="91f91-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="91f91-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="91f91-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="91f91-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="91f91-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91f91-112">Description</span></span>

<span data-ttu-id="91f91-113">Il cmdlet Test-CsGroupExpansion consente di determinare se l'espansione di gruppo sta funzionando all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="91f91-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="91f91-114">Quando l'espansione del gruppo è abilitata, gli utenti configurano i gruppi di distribuzione come contatto.</span><span class="sxs-lookup"><span data-stu-id="91f91-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="91f91-115">Ciò significa che gli utenti possono quindi inviare lo stesso messaggio istantaneo a tutti i membri del gruppo indirizzando il messaggio al gruppo anziché ai singoli membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="91f91-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="91f91-116">Espansione gruppo consente di visualizzare in modo semplice e rapido tutti i membri del gruppo e il relativo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="91f91-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="91f91-117">Con il cmdlet Test-CsGroupExpansion, devi specificare un gruppo di distribuzione di Active Directory usando l'indirizzo di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="91f91-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="91f91-118">Test-CsGroupExpansion usa quindi l'espansione di gruppo per recuperare l'appartenenza al gruppo e confrontare l'elenco recuperato con l'appartenenza dell'indirizzo di posta elettronica del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="91f91-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="91f91-119">Se i due elenchi corrispondono, l'espansione del gruppo funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="91f91-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="91f91-120">Tieni presente che puoi testare l'espansione del gruppo in due modi: testando il servizio stesso o provando il servizio Web associato.</span><span class="sxs-lookup"><span data-stu-id="91f91-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="91f91-121">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="91f91-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="91f91-122">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="91f91-122">Running the test</span></span>

<span data-ttu-id="91f91-123">Il cmdlet Test-CsGroupExpansion può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91f91-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="91f91-124">Per eseguire questo controllo usando un account di test, devi solo specificare il nome di dominio completo del pool di Lync Server da testare e l'indirizzo di posta elettronica per un gruppo di distribuzione valido.</span><span class="sxs-lookup"><span data-stu-id="91f91-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="91f91-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91f91-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="91f91-126">Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Lync Server contenente il nome dell'account e la password.</span><span class="sxs-lookup"><span data-stu-id="91f91-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="91f91-127">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="91f91-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="91f91-128">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="91f91-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="91f91-129">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="91f91-129">Determining success or failure</span></span>

<span data-ttu-id="91f91-130">Se l'utente specificato può usare l'espansione di gruppo, riceverai un output simile a quello con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="91f91-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="91f91-131">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="91f91-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="91f91-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91f91-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91f91-133">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="91f91-133">Result : Success</span></span>

<span data-ttu-id="91f91-134">Latenza: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="91f91-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="91f91-135">Errore</span><span class="sxs-lookup"><span data-stu-id="91f91-135">Error :</span></span>

<span data-ttu-id="91f91-136">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="91f91-136">Diagnosis :</span></span>

<span data-ttu-id="91f91-137">Se l'utente specificato non può usare l'espansione di gruppo, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="91f91-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="91f91-138">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="91f91-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="91f91-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91f91-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91f91-140">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="91f91-140">Result : Failure</span></span>

<span data-ttu-id="91f91-141">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="91f91-141">Latency : 00:00:00</span></span>

<span data-ttu-id="91f91-142">Errore</span><span class="sxs-lookup"><span data-stu-id="91f91-142">Error :</span></span>

<span data-ttu-id="91f91-143">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="91f91-143">Diagnosis :</span></span>

<span data-ttu-id="91f91-144">Test-CsGroupExpansion: l'endpoint non è stato in grado di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="91f91-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="91f91-145">Vedere il ErrorCode per un motivo specifico.</span><span class="sxs-lookup"><span data-stu-id="91f91-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="91f91-146">L'output precedente indica che il test non è riuscito perché l'utente specificato non è riuscito a eseguire la registrazione con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91f91-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="91f91-147">In genere si verifica se l'account di test non esiste o non è abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91f91-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="91f91-148">Puoi verificare che l'account esista e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="91f91-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="91f91-149">Se Test-CsGroupExpansion non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="91f91-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="91f91-150">Quando il parametro Verbose è incluso Test-CsGroupExpansion restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91f91-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="91f91-151">Ad esempio, questo output indica che non è stato possibile trovare il gruppo di distribuzione specificato:</span><span class="sxs-lookup"><span data-stu-id="91f91-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="91f91-152">Provare a ottenere un biglietto Web.</span><span class="sxs-lookup"><span data-stu-id="91f91-152">Trying to get web ticket.</span></span>

<span data-ttu-id="91f91-153">URL del servizio Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="91f91-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="91f91-154">Uso dell'autenticazione NTLM/cordolo.</span><span class="sxs-lookup"><span data-stu-id="91f91-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="91f91-155">GetWebTicketActivity completata.</span><span class="sxs-lookup"><span data-stu-id="91f91-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="91f91-156">Attività' VerifyDistributionList ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="91f91-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="91f91-157">Lo stato di risposta del servizio Web DLX è: NotFound.</span><span class="sxs-lookup"><span data-stu-id="91f91-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="91f91-158">Attività "VerifyDistributionList" completata in "0,2597923" secs.</span><span class="sxs-lookup"><span data-stu-id="91f91-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="91f91-159">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="91f91-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="91f91-160">Ecco alcuni motivi comuni per cui Test-CsGroupExpansion potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="91f91-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="91f91-161">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="91f91-161">You specified an invalid user account.</span></span> <span data-ttu-id="91f91-162">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="91f91-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="91f91-163">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91f91-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="91f91-164">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="91f91-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="91f91-165">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91f91-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="91f91-166">L'espansione del gruppo potrebbe essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="91f91-166">Group expansion might be disabled.</span></span> <span data-ttu-id="91f91-167">È possibile disattivare l'espansione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="91f91-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="91f91-168">Se l'espansione del gruppo è stata disattivata, il cmdlet Test-CsGroupExpansion avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="91f91-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="91f91-169">Per determinare se l'espansione del gruppo è abilitata, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="91f91-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

