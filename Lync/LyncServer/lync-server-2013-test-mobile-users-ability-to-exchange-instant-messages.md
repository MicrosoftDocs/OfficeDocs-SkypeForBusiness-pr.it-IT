---
title: 'Lync Server 2013: verificare la capacità degli utenti mobili di scambiare messaggi istantanei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="38d8e-102">Testare la capacità degli utenti mobili di scambiare messaggi istantanei in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d8e-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d8e-103">_**Argomento Ultima modifica:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="38d8e-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38d8e-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="38d8e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="38d8e-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="38d8e-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d8e-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="38d8e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="38d8e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38d8e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d8e-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="38d8e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="38d8e-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="38d8e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="38d8e-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="38d8e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="38d8e-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38d8e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="38d8e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38d8e-112">Description</span></span>

<span data-ttu-id="38d8e-113">Il servizio di mobilità consente agli utenti di dispositivi mobili di eseguire operazioni come:</span><span class="sxs-lookup"><span data-stu-id="38d8e-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="38d8e-114">Scambiare messaggi istantanei e informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="38d8e-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="38d8e-115">Archiviare e recuperare i messaggi vocali internamente anziché con il provider wireless.</span><span class="sxs-lookup"><span data-stu-id="38d8e-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="38d8e-116">Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="38d8e-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="38d8e-117">Il cmdlet test-CsMxcP2PIM offre un modo semplice e rapido per verificare che gli utenti possano usare il servizio mobilità per scambiare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="38d8e-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="38d8e-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="38d8e-118">Running the test</span></span>

<span data-ttu-id="38d8e-119">Per eseguire questo test, è necessario creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="38d8e-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="38d8e-120">È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="38d8e-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="38d8e-121">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="38d8e-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="38d8e-122">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="38d8e-122">Determining success or failure</span></span>

<span data-ttu-id="38d8e-123">Se i due utenti di test possono scambiare messaggi istantanei usando il servizio mobilità, Test-CsMcxP2PIM restituirà il risultato del test:</span><span class="sxs-lookup"><span data-stu-id="38d8e-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="38d8e-124">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38d8e-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="38d8e-125">URI di destinazione:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="38d8e-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="38d8e-126">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="38d8e-126">Result : Success</span></span>

<span data-ttu-id="38d8e-127">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="38d8e-127">Latency : 00:00:00</span></span>

<span data-ttu-id="38d8e-128">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="38d8e-128">Error Message :</span></span>

<span data-ttu-id="38d8e-129">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="38d8e-129">Diagnosis :</span></span>

<span data-ttu-id="38d8e-130">Se il test ha esito negativo, il risultato verrà impostato su errore e verrà visualizzato un messaggio di errore e una diagnosi dettagliati:</span><span class="sxs-lookup"><span data-stu-id="38d8e-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="38d8e-131">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38d8e-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="38d8e-132">URI di destinazione:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="38d8e-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="38d8e-133">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="38d8e-133">Result : Failure</span></span>

<span data-ttu-id="38d8e-134">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="38d8e-134">Latency : 00:00:00</span></span>

<span data-ttu-id="38d8e-135">Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web.</span><span class="sxs-lookup"><span data-stu-id="38d8e-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="38d8e-136">Eccezione interna: la richiesta di HHTP non è autorizzata con</span><span class="sxs-lookup"><span data-stu-id="38d8e-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="38d8e-137">schema di negoziazione client "NTLM".</span><span class="sxs-lookup"><span data-stu-id="38d8e-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="38d8e-138">L'autenticazione</span><span class="sxs-lookup"><span data-stu-id="38d8e-138">The authentication</span></span>

<span data-ttu-id="38d8e-139">l'intestazione ricevuta dal server è "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="38d8e-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="38d8e-140">Eccezione interna: il server remoto ha restituito un errore:</span><span class="sxs-lookup"><span data-stu-id="38d8e-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="38d8e-141">(401) non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="38d8e-141">(401) Unauthorized.</span></span>

<span data-ttu-id="38d8e-142">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="38d8e-142">Diagnosis :</span></span>

<span data-ttu-id="38d8e-143">Diagnosi interna: X-MS-Server-Fqdb: atl-cs-</span><span class="sxs-lookup"><span data-stu-id="38d8e-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="38d8e-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38d8e-144">001.litwareinc.com</span></span>

<span data-ttu-id="38d8e-145">Cache-Control: private</span><span class="sxs-lookup"><span data-stu-id="38d8e-145">Cache-Control : private</span></span>

<span data-ttu-id="38d8e-146">Content-Type: text/html; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="38d8e-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="38d8e-147">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="38d8e-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="38d8e-148">Autenticazione WWW: negozia, NTLM</span><span class="sxs-lookup"><span data-stu-id="38d8e-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="38d8e-149">X-Powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="38d8e-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="38d8e-150">X-Content-Type-Options: nosniffing</span><span class="sxs-lookup"><span data-stu-id="38d8e-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="38d8e-151">Data: Mer, 28 mag 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="38d8e-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="38d8e-152">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="38d8e-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="38d8e-153">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="38d8e-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="38d8e-154">Se Test-CsMcxP2PIM non riesce, il primo passaggio deve essere verificare che il servizio di mobilità sia attivo e funzionante.</span><span class="sxs-lookup"><span data-stu-id="38d8e-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="38d8e-155">Questa operazione può essere eseguita usando un Web browser per verificare che sia possibile accedere all'URL del servizio di mobilità per il pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38d8e-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="38d8e-156">Questo comando, ad esempio, verifica l'URL per il pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="38d8e-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="38d8e-157">Se il servizio di mobilità sembra essere in corso, verificare che i due utenti di test dispongano di account di Lync Server validi.</span><span class="sxs-lookup"><span data-stu-id="38d8e-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="38d8e-158">Puoi recuperare le informazioni dell'account usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="38d8e-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="38d8e-159">Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido.</span><span class="sxs-lookup"><span data-stu-id="38d8e-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="38d8e-160">Dovresti anche verificare che l'utente sia abilitato per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="38d8e-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="38d8e-161">A questo scopo, determina prima di tutto i criteri di mobilità assegnati all'account:</span><span class="sxs-lookup"><span data-stu-id="38d8e-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="38d8e-162">Dopo aver conosciuto il nome del criterio, usare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio RedmondMobilityPolicy) disponga della proprietà EnableMobility impostata su true:</span><span class="sxs-lookup"><span data-stu-id="38d8e-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="38d8e-163">Se viene visualizzato un messaggio di errore con le intestazioni di autenticazione, significa che spesso non è stato specificato un account utente valido.</span><span class="sxs-lookup"><span data-stu-id="38d8e-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="38d8e-164">Verificare il nome utente e la password e quindi riprovare il test.</span><span class="sxs-lookup"><span data-stu-id="38d8e-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="38d8e-165">Se si è certi che l'account utente sia valido, usare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="38d8e-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="38d8e-166">In questo modo verranno spiegati i metodi di autenticazione abilitati nell'organizzazione. Per altre informazioni su come risolvere i problemi relativi al servizio di mobilità, vedere il post di Blog risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="38d8e-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

