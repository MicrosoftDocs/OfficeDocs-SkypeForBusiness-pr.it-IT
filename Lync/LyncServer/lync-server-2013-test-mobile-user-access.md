---
title: "Lync Server 2013: verificare l'accesso degli utenti di dispositivi mobili"
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
ms.openlocfilehash: 628fd3aae4f66316627176c3af025eb63202bafb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="bfef1-102">Testare l'accesso degli utenti di dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfef1-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfef1-103">_**Argomento Ultima modifica:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="bfef1-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfef1-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="bfef1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bfef1-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="bfef1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfef1-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="bfef1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bfef1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfef1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfef1-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="bfef1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bfef1-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bfef1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bfef1-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="bfef1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="bfef1-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bfef1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bfef1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfef1-112">Description</span></span>

<span data-ttu-id="bfef1-113">Il servizio di mobilità consente agli utenti di dispositivi mobili di eseguire operazioni come:</span><span class="sxs-lookup"><span data-stu-id="bfef1-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="bfef1-114">Scambiare messaggi istantanei e informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="bfef1-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="bfef1-115">Archiviare e recuperare i messaggi vocali internamente anziché con il provider wireless.</span><span class="sxs-lookup"><span data-stu-id="bfef1-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="bfef1-116">Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="bfef1-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="bfef1-117">Il cmdlet Test-CsMcxConference offre un modo semplice e rapido per verificare che gli utenti possano partecipare e partecipare alle conferenze di Lync Server usando un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="bfef1-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bfef1-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="bfef1-118">Running the test</span></span>

<span data-ttu-id="bfef1-119">Per eseguire questo controllo, è necessario creare tre oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="bfef1-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="bfef1-120">È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsMcxConference, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bfef1-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="bfef1-121">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="bfef1-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bfef1-122">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="bfef1-122">Determining success or failure</span></span>

<span data-ttu-id="bfef1-123">Se il controllo ha esito positivo, Test-CsMcxConference segnalerà un risultato di test positivo:</span><span class="sxs-lookup"><span data-stu-id="bfef1-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="bfef1-124">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bfef1-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bfef1-125">URI di destinazione:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="bfef1-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="bfef1-126">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="bfef1-126">Result : Success</span></span>

<span data-ttu-id="bfef1-127">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bfef1-127">Latency : 00:00:00</span></span>

<span data-ttu-id="bfef1-128">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="bfef1-128">Error Message :</span></span>

<span data-ttu-id="bfef1-129">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="bfef1-129">Diagnosis :</span></span>

<span data-ttu-id="bfef1-130">Se il controllo non è riuscito, il Test CsMcxConference segnalerà un risultato di errore.</span><span class="sxs-lookup"><span data-stu-id="bfef1-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="bfef1-131">Questo risultato del test sarà in genere accompagnato da un messaggio di errore e una diagnosi dettagliati.</span><span class="sxs-lookup"><span data-stu-id="bfef1-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="bfef1-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bfef1-132">For example:</span></span>

<span data-ttu-id="bfef1-133">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bfef1-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bfef1-134">URI di destinazione:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="bfef1-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="bfef1-135">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="bfef1-135">Result : Failure</span></span>

<span data-ttu-id="bfef1-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bfef1-136">Latency : 00:00:00</span></span>

<span data-ttu-id="bfef1-137">Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web.</span><span class="sxs-lookup"><span data-stu-id="bfef1-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="bfef1-138">Eccezione interna: la richiesta HHTP non è autorizzata con il client</span><span class="sxs-lookup"><span data-stu-id="bfef1-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="bfef1-139">schema di negoziazione "NTLM".</span><span class="sxs-lookup"><span data-stu-id="bfef1-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="bfef1-140">Intestazione di autenticazione ricevuta</span><span class="sxs-lookup"><span data-stu-id="bfef1-140">The authentication header received</span></span>

<span data-ttu-id="bfef1-141">dal server è stato "negozia".</span><span class="sxs-lookup"><span data-stu-id="bfef1-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="bfef1-142">Eccezione interna: il server remoto ha restituito un errore: (401)</span><span class="sxs-lookup"><span data-stu-id="bfef1-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="bfef1-143">Autorizzato.</span><span class="sxs-lookup"><span data-stu-id="bfef1-143">Unauthorized.</span></span>

<span data-ttu-id="bfef1-144">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="bfef1-144">Diagnosis :</span></span>

<span data-ttu-id="bfef1-145">Diagnosi interna: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bfef1-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bfef1-146">Cache-Control: private</span><span class="sxs-lookup"><span data-stu-id="bfef1-146">Cache-Control : private</span></span>

<span data-ttu-id="bfef1-147">Content-Type: text/html; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bfef1-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="bfef1-148">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="bfef1-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="bfef1-149">Autenticazione WWW: negozia, NTLM</span><span class="sxs-lookup"><span data-stu-id="bfef1-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="bfef1-150">X-Powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bfef1-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="bfef1-151">X-Content-Type-Options: nosniffing</span><span class="sxs-lookup"><span data-stu-id="bfef1-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="bfef1-152">Data: Mer, 28 mag 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="bfef1-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="bfef1-153">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="bfef1-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bfef1-154">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="bfef1-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="bfef1-155">Se Test-CsMcxConference non riesce, è necessario iniziare verificando che il servizio di mobilità sia in funzione ed è possibile accedervi.</span><span class="sxs-lookup"><span data-stu-id="bfef1-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="bfef1-156">Questa operazione può essere eseguita usando un Web browser per verificare che sia possibile accedere all'URL del servizio di mobilità per il pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfef1-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="bfef1-157">Questo comando, ad esempio, verifica l'URL per il pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="bfef1-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="bfef1-158">Se è possibile accedere al servizio di mobilità, verificare che gli utenti di test dispongano di account di Lync Server validi.</span><span class="sxs-lookup"><span data-stu-id="bfef1-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="bfef1-159">Puoi recuperare le informazioni dell'account usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bfef1-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="bfef1-160">Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido. Dovresti anche verificare che ogni account utente sia abilitato per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="bfef1-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="bfef1-161">A questo scopo, determina prima di tutto i criteri di mobilità assegnati all'account:</span><span class="sxs-lookup"><span data-stu-id="bfef1-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="bfef1-162">Dopo aver conosciuto il nome del criterio, usare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio RedmondMobilityPolicy) disponga della proprietà EnableMobility impostata su true:</span><span class="sxs-lookup"><span data-stu-id="bfef1-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="bfef1-163">Se viene visualizzato un messaggio di errore "intestazione di autenticazione" quando si esegue Test-CsMcxConference, che spesso significa che non è stato specificato un account utente valido, verificare il nome utente e la password e quindi riprovare il test.</span><span class="sxs-lookup"><span data-stu-id="bfef1-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="bfef1-164">Se si è certi che l'account utente sia valido, usare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="bfef1-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="bfef1-165">In questo modo verranno spiegati i metodi di autenticazione abilitati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfef1-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="bfef1-166">Per altre informazioni su come risolvere i problemi relativi al servizio di mobilità, vedere il post di Blog risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="bfef1-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

