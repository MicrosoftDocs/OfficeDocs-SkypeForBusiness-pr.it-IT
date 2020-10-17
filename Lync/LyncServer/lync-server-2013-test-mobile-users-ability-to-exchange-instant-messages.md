---
title: 'Lync Server 2013: testare la possibilità per gli utenti di dispositivi mobili di scambiare messaggi istantanei'
description: 'Lync Server 2013: testare la possibilità per gli utenti di dispositivi mobili di scambiare messaggi istantanei.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558292"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="9977e-103">Testare la possibilità per gli utenti di dispositivi mobili di scambiare messaggi istantanei in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9977e-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9977e-104">_**Ultimo argomento modificato:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="9977e-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9977e-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="9977e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9977e-106">Mensile</span><span class="sxs-lookup"><span data-stu-id="9977e-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9977e-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="9977e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9977e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9977e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9977e-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="9977e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9977e-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9977e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9977e-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="9977e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="9977e-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9977e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9977e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9977e-113">Description</span></span>

<span data-ttu-id="9977e-114">Il servizio per dispositivi mobili consente agli utenti del dispositivo mobile di eseguire operazioni quali:</span><span class="sxs-lookup"><span data-stu-id="9977e-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="9977e-115">Scambiare messaggi istantanei e informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="9977e-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="9977e-116">Archiviare e recuperare i messaggi vocali internamente anziché con il provider di servizi di rete.</span><span class="sxs-lookup"><span data-stu-id="9977e-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="9977e-117">Sfruttare le funzionalità di Lync Server, ad esempio la chiamata tramite il lavoro e le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9977e-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="9977e-118">Il cmdlet Test-CsMxcP2PIM fornisce un modo semplice e rapido per verificare che gli utenti possano utilizzare il servizio per dispositivi mobili per scambiare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="9977e-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9977e-119">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="9977e-119">Running the test</span></span>

<span data-ttu-id="9977e-120">Per eseguire questo test, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="9977e-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="9977e-121">Quando si chiama Test-CsMcxP2PIM, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:</span><span class="sxs-lookup"><span data-stu-id="9977e-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="9977e-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="9977e-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9977e-123">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="9977e-123">Determining success or failure</span></span>

<span data-ttu-id="9977e-124">Se i due utenti di test possono scambiare messaggi istantanei utilizzando il servizio per dispositivi mobili, Test-CsMcxP2PIM restituirà il risultato del test:</span><span class="sxs-lookup"><span data-stu-id="9977e-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="9977e-125">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9977e-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9977e-126">URI di destinazione: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="9977e-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="9977e-127">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="9977e-127">Result : Success</span></span>

<span data-ttu-id="9977e-128">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9977e-128">Latency : 00:00:00</span></span>

<span data-ttu-id="9977e-129">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="9977e-129">Error Message :</span></span>

<span data-ttu-id="9977e-130">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="9977e-130">Diagnosis :</span></span>

<span data-ttu-id="9977e-131">Se il test ha esito negativo, il risultato verrà impostato su errore e verrà visualizzato un messaggio di errore dettagliato e la diagnosi:</span><span class="sxs-lookup"><span data-stu-id="9977e-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="9977e-132">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9977e-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9977e-133">URI di destinazione: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="9977e-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="9977e-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="9977e-134">Result : Failure</span></span>

<span data-ttu-id="9977e-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9977e-135">Latency : 00:00:00</span></span>

<span data-ttu-id="9977e-136">Messaggio di errore: nessuna risposta ricevuta per il servizio Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="9977e-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="9977e-137">Eccezione interna: la richiesta di HHTP non è stata autorizzata con</span><span class="sxs-lookup"><span data-stu-id="9977e-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="9977e-138">schema di negoziazione client ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="9977e-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="9977e-139">L'autenticazione</span><span class="sxs-lookup"><span data-stu-id="9977e-139">The authentication</span></span>

<span data-ttu-id="9977e-140">l'intestazione ricevuta dal server è "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="9977e-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="9977e-141">Eccezione interna: il server remoto ha restituito un errore:</span><span class="sxs-lookup"><span data-stu-id="9977e-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="9977e-142">(401) non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="9977e-142">(401) Unauthorized.</span></span>

<span data-ttu-id="9977e-143">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="9977e-143">Diagnosis :</span></span>

<span data-ttu-id="9977e-144">Diagnosi interna: X-MS-Server-Fqdb: atl-cs-</span><span class="sxs-lookup"><span data-stu-id="9977e-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="9977e-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9977e-145">001.litwareinc.com</span></span>

<span data-ttu-id="9977e-146">Cache-Control: privato</span><span class="sxs-lookup"><span data-stu-id="9977e-146">Cache-Control : private</span></span>

<span data-ttu-id="9977e-147">Content-Type: text/html; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9977e-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="9977e-148">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="9977e-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="9977e-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="9977e-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="9977e-150">X-Powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9977e-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="9977e-151">X-Content-Type-Options: nosniff</span><span class="sxs-lookup"><span data-stu-id="9977e-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="9977e-152">Data: Mer, 28 May 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="9977e-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="9977e-153">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="9977e-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9977e-154">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="9977e-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="9977e-155">Se Test-CsMcxP2PIM ha esito negativo, il primo passaggio consiste nel verificare che il servizio per dispositivi mobili sia attivo e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9977e-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="9977e-156">Che è possibile eseguire utilizzando un Web browser per verificare che sia possibile accedere all'URL del servizio per dispositivi mobili per il pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9977e-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="9977e-157">Ad esempio, questo comando consente di verificare l'URL per il pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="9977e-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="9977e-158">Se il servizio per dispositivi mobili sembra essere in esecuzione, verificare che i due utenti di test dispongano di account di Lync Server validi.</span><span class="sxs-lookup"><span data-stu-id="9977e-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="9977e-159">È possibile recuperare le informazioni dell'account utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9977e-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="9977e-160">Se la proprietà Enabled non è uguale a true o se il comando ha esito negativo, significa che l'utente non dispone di un account Lync Server valido.</span><span class="sxs-lookup"><span data-stu-id="9977e-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="9977e-161">È inoltre necessario verificare che l'utente sia abilitato per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="9977e-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="9977e-162">A tale scopo, determinare innanzitutto i criteri per dispositivi mobili assegnati all'account:</span><span class="sxs-lookup"><span data-stu-id="9977e-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="9977e-163">Una volta che si conosce il nome del criterio, utilizzare il cmdlet Get-CsMobilityPolicy per verificare che il criterio in questione (ad esempio, RedmondMobilityPolicy) la proprietà EnableMobility sia impostata su true:</span><span class="sxs-lookup"><span data-stu-id="9977e-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="9977e-164">Se viene visualizzato un messaggio di errore con intestazioni di autenticazione, significa che spesso non è stato specificato un account utente valido.</span><span class="sxs-lookup"><span data-stu-id="9977e-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="9977e-165">Verificare il nome utente e la password e quindi provare a eseguire di nuovo il test.</span><span class="sxs-lookup"><span data-stu-id="9977e-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="9977e-166">Se si è certi che l'account utente sia valido, utilizzare il cmdlet Get-CsWebServiceConfiguration e controllare il valore della Proprietà UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="9977e-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="9977e-167">Che vi dirà quali metodi di autenticazione sono abilitati nell'organizzazione. Per ulteriori suggerimenti su come risolvere i problemi relativi al servizio per dispositivi mobili, vedere il post di Blog per la risoluzione dei problemi relativi alla [connettività per dispositivi mobili esterni di Lync](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="9977e-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

