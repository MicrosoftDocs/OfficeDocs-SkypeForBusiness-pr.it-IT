---
title: "Lync Server 2013: testare l'accesso degli utenti di dispositivi mobili"
description: "Lync Server 2013: testare l'accesso degli utenti di dispositivi mobili."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541872"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="805bf-103">Verificare l'accesso degli utenti di dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805bf-103">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="805bf-104">_**Ultimo argomento modificato:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="805bf-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="805bf-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="805bf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="805bf-106">Mensile</span><span class="sxs-lookup"><span data-stu-id="805bf-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="805bf-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="805bf-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="805bf-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="805bf-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="805bf-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="805bf-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="805bf-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="805bf-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="805bf-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="805bf-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="805bf-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="805bf-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="805bf-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="805bf-113">Description</span></span>

<span data-ttu-id="805bf-114">Il servizio per dispositivi mobili consente agli utenti del dispositivo mobile di eseguire operazioni quali:</span><span class="sxs-lookup"><span data-stu-id="805bf-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="805bf-115">Scambiare messaggi istantanei e informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="805bf-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="805bf-116">Archiviare e recuperare i messaggi vocali internamente anziché con il provider di servizi di rete.</span><span class="sxs-lookup"><span data-stu-id="805bf-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="805bf-117">Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="805bf-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="805bf-118">Il cmdlet Test-CsMcxConference fornisce un modo semplice e rapido per verificare che gli utenti possano partecipare a conferenze di Lync Server utilizzando un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="805bf-118">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="805bf-119">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="805bf-119">Running the test</span></span>

<span data-ttu-id="805bf-120">Per eseguire il controllo, è necessario creare tre oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="805bf-120">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="805bf-121">È quindi necessario includere gli oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsMcxConference come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="805bf-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="805bf-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="805bf-122">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="805bf-123">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="805bf-123">Determining success or failure</span></span>

<span data-ttu-id="805bf-124">Se il controllo ha esito positivo, Test-CsMcxConference segnalerà un risultato di esito positivo:</span><span class="sxs-lookup"><span data-stu-id="805bf-124">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="805bf-125">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="805bf-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="805bf-126">URI di destinazione: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="805bf-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="805bf-127">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="805bf-127">Result : Success</span></span>

<span data-ttu-id="805bf-128">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="805bf-128">Latency : 00:00:00</span></span>

<span data-ttu-id="805bf-129">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="805bf-129">Error Message :</span></span>

<span data-ttu-id="805bf-130">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="805bf-130">Diagnosis :</span></span>

<span data-ttu-id="805bf-131">Se il controllo non ha avuto esito positivo Test-CsMcxConference segnalerà un esito negativo del test.</span><span class="sxs-lookup"><span data-stu-id="805bf-131">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="805bf-132">Questo risultato del test sarà generalmente accompagnato da un messaggio di errore dettagliato e da una diagnosi.</span><span class="sxs-lookup"><span data-stu-id="805bf-132">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="805bf-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="805bf-133">For example:</span></span>

<span data-ttu-id="805bf-134">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="805bf-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="805bf-135">URI di destinazione: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="805bf-135">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="805bf-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="805bf-136">Result : Failure</span></span>

<span data-ttu-id="805bf-137">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="805bf-137">Latency : 00:00:00</span></span>

<span data-ttu-id="805bf-138">Messaggio di errore: nessuna risposta ricevuta per il servizio Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="805bf-138">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="805bf-139">Eccezione interna: la richiesta di HHTP non è autorizzata con il client</span><span class="sxs-lookup"><span data-stu-id="805bf-139">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="805bf-140">schema di negoziazione ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="805bf-140">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="805bf-141">Intestazione di autenticazione ricevuta</span><span class="sxs-lookup"><span data-stu-id="805bf-141">The authentication header received</span></span>

<span data-ttu-id="805bf-142">dal server è stato ' Negotiate '.</span><span class="sxs-lookup"><span data-stu-id="805bf-142">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="805bf-143">Eccezione interna: il server remoto ha restituito un errore: (401)</span><span class="sxs-lookup"><span data-stu-id="805bf-143">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="805bf-144">Non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="805bf-144">Unauthorized.</span></span>

<span data-ttu-id="805bf-145">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="805bf-145">Diagnosis :</span></span>

<span data-ttu-id="805bf-146">Diagnosi interna: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="805bf-146">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="805bf-147">Cache-Control: privato</span><span class="sxs-lookup"><span data-stu-id="805bf-147">Cache-Control : private</span></span>

<span data-ttu-id="805bf-148">Content-Type: text/html; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="805bf-148">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="805bf-149">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="805bf-149">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="805bf-150">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="805bf-150">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="805bf-151">X-Powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="805bf-151">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="805bf-152">X-Content-Type-Options: nosniff</span><span class="sxs-lookup"><span data-stu-id="805bf-152">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="805bf-153">Data: Mer, 28 May 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="805bf-153">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="805bf-154">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="805bf-154">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="805bf-155">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="805bf-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="805bf-156">Se Test-CsMcxConference ha esito negativo, è innanzitutto necessario verificare che il servizio per dispositivi mobili sia in esecuzione e che sia possibile accedervi.</span><span class="sxs-lookup"><span data-stu-id="805bf-156">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="805bf-157">Che è possibile eseguire utilizzando un Web browser per verificare che sia possibile accedere all'URL del servizio per dispositivi mobili per il pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="805bf-157">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="805bf-158">Ad esempio, questo comando consente di verificare l'URL per il pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="805bf-158">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="805bf-159">Se è possibile accedere al servizio per dispositivi mobili, è necessario verificare che gli utenti di test dispongano di account Lync Server validi.</span><span class="sxs-lookup"><span data-stu-id="805bf-159">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="805bf-160">È possibile recuperare le informazioni dell'account utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="805bf-160">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="805bf-161">Se la proprietà Enabled non è uguale a true o se il comando ha esito negativo, significa che l'utente non dispone di un account Lync Server valido. È inoltre necessario verificare che ogni account utente sia abilitato per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="805bf-161">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="805bf-162">A tale scopo, determinare innanzitutto i criteri per dispositivi mobili assegnati all'account:</span><span class="sxs-lookup"><span data-stu-id="805bf-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="805bf-163">Una volta che si conosce il nome del criterio, utilizzare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio, RedmondMobilityPolicy) la proprietà EnableMobility sia impostata su true:</span><span class="sxs-lookup"><span data-stu-id="805bf-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="805bf-164">Se si riceve un messaggio di errore "intestazione di autenticazione" quando si esegue Test-CsMcxConference che spesso significa che non è stato specificato un account utente valido, verificare il nome utente e la password e quindi provare di nuovo il test.</span><span class="sxs-lookup"><span data-stu-id="805bf-164">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="805bf-165">Se si è certi che l'account utente sia valido, utilizzare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="805bf-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="805bf-166">Che vi dirà quali metodi di autenticazione sono abilitati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="805bf-166">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="805bf-167">Per ulteriori suggerimenti su come risolvere i problemi relativi al servizio per dispositivi mobili, vedere il post di Blog per la risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="805bf-167">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

