---
title: "Lync Server 2013: testare la possibilità di utilizzare l'espansione dei gruppi"
description: "Lync Server 2013: testare la possibilità di utilizzare l'espansione dei gruppi."
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
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560792"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="2d20f-103">Verifica della capacità di utilizzare l'espansione dei gruppi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d20f-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d20f-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2d20f-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d20f-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="2d20f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2d20f-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="2d20f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d20f-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="2d20f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2d20f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d20f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d20f-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="2d20f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2d20f-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2d20f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2d20f-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="2d20f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="2d20f-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2d20f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2d20f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d20f-113">Description</span></span>

<span data-ttu-id="2d20f-114">Il cmdlet Test-CsGroupExpansion consente di determinare se l'espansione di gruppo sta funzionando all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d20f-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="2d20f-115">Quando l'espansione dei gruppi è abilitata, gli utenti configurano i gruppi di distribuzione come contatto.</span><span class="sxs-lookup"><span data-stu-id="2d20f-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="2d20f-116">Questo significa che gli utenti possono quindi inviare lo stesso messaggio istantaneo a tutti i membri del gruppo, indirizzando il messaggio al gruppo anziché ai singoli membri di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="2d20f-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="2d20f-117">l'espansione dei gruppi consente di visualizzare in modo semplice e rapido tutti i membri di un gruppo e il relativo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="2d20f-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="2d20f-118">Con il cmdlet Test-CsGroupExpansion, è necessario specificare un gruppo di distribuzione di Active Directory utilizzando l'indirizzo di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2d20f-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="2d20f-119">Test-CsGroupExpansion utilizza quindi l'espansione dei gruppi per recuperare l'appartenenza al gruppo e confrontare l'elenco recuperato con l'appartenenza all'indirizzo di posta elettronica del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="2d20f-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="2d20f-120">Se i due elenchi corrispondono, l'espansione dei gruppi sta funzionando correttamente.</span><span class="sxs-lookup"><span data-stu-id="2d20f-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="2d20f-121">Si noti che è possibile testare l'espansione dei gruppi in due modi: testando il servizio stesso o testando il servizio Web associato.</span><span class="sxs-lookup"><span data-stu-id="2d20f-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="2d20f-122">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="2d20f-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2d20f-123">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="2d20f-123">Running the test</span></span>

<span data-ttu-id="2d20f-124">È possibile eseguire il cmdlet Test-CsGroupExpansion utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d20f-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="2d20f-125">Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare e l'indirizzo di posta elettronica per un gruppo di distribuzione valido.</span><span class="sxs-lookup"><span data-stu-id="2d20f-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="2d20f-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2d20f-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="2d20f-127">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Lync Server che contenga il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="2d20f-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="2d20f-128">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="2d20f-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="2d20f-129">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="2d20f-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2d20f-130">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="2d20f-130">Determining success or failure</span></span>

<span data-ttu-id="2d20f-131">Se l'utente specificato è in grado di utilizzare l'espansione dei gruppi, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="2d20f-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2d20f-132">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="2d20f-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="2d20f-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2d20f-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2d20f-134">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="2d20f-134">Result : Success</span></span>

<span data-ttu-id="2d20f-135">Latenza: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="2d20f-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="2d20f-136">Errore</span><span class="sxs-lookup"><span data-stu-id="2d20f-136">Error :</span></span>

<span data-ttu-id="2d20f-137">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="2d20f-137">Diagnosis :</span></span>

<span data-ttu-id="2d20f-138">Se l'utente specificato non è in grado di utilizzare l'espansione di gruppo, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="2d20f-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2d20f-139">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="2d20f-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="2d20f-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2d20f-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2d20f-141">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="2d20f-141">Result : Failure</span></span>

<span data-ttu-id="2d20f-142">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="2d20f-142">Latency : 00:00:00</span></span>

<span data-ttu-id="2d20f-143">Errore</span><span class="sxs-lookup"><span data-stu-id="2d20f-143">Error :</span></span>

<span data-ttu-id="2d20f-144">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="2d20f-144">Diagnosis :</span></span>

<span data-ttu-id="2d20f-145">Test-CsGroupExpansion: l'endpoint non è stato in grado di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2d20f-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="2d20f-146">Per motivi specifici, vedere ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="2d20f-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="2d20f-147">L'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato in grado di eseguire la registrazione con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d20f-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="2d20f-148">Ciò si verifica in genere se l'account di test non esiste o non è abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d20f-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="2d20f-149">È possibile verificare che l'account esista e determinare se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2d20f-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="2d20f-150">Se Test-CsGroupExpansion ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="2d20f-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="2d20f-151">Quando viene incluso il parametro Verbose Test-CsGroupExpansion restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d20f-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2d20f-152">Ad esempio, questo output indica che non è stato possibile trovare il gruppo di distribuzione specificato:</span><span class="sxs-lookup"><span data-stu-id="2d20f-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="2d20f-153">Tentativo di ottenere il ticket web.</span><span class="sxs-lookup"><span data-stu-id="2d20f-153">Trying to get web ticket.</span></span>

<span data-ttu-id="2d20f-154">URL del servizio Web: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="2d20f-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="2d20f-155">Utilizzo dell'autenticazione NTLM/cordolo.</span><span class="sxs-lookup"><span data-stu-id="2d20f-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="2d20f-156">GetWebTicketActivity completata.</span><span class="sxs-lookup"><span data-stu-id="2d20f-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="2d20f-157">Attività' VerifyDistributionList ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="2d20f-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="2d20f-158">Lo stato di risposta del servizio Web DLX è: NotFound.</span><span class="sxs-lookup"><span data-stu-id="2d20f-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="2d20f-159">Attività' VerifyDistributionList ' completata in ' 0,2597923' secs.</span><span class="sxs-lookup"><span data-stu-id="2d20f-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2d20f-160">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="2d20f-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="2d20f-161">Di seguito sono riportate alcune ragioni comuni per cui Test-CsGroupExpansion potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="2d20f-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="2d20f-162">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="2d20f-162">You specified an invalid user account.</span></span> <span data-ttu-id="2d20f-163">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2d20f-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2d20f-164">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d20f-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2d20f-165">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2d20f-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2d20f-166">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d20f-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="2d20f-167">L'espansione del gruppo potrebbe essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="2d20f-167">Group expansion might be disabled.</span></span> <span data-ttu-id="2d20f-168">È possibile disattivare l'espansione dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="2d20f-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="2d20f-169">Se l'espansione del gruppo è stata disattivata, il cmdlet Test-CsGroupExpansion avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2d20f-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="2d20f-170">Per determinare se l'espansione dei gruppi è abilitata, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2d20f-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

