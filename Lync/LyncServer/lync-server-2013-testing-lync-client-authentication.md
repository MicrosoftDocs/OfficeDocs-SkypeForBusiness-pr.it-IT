---
title: "Lync Server 2013: verificare l'autenticazione del client Lync"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="734bb-102">Test dell'autenticazione del client Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="734bb-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="734bb-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="734bb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="734bb-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="734bb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="734bb-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="734bb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="734bb-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="734bb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="734bb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="734bb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="734bb-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="734bb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="734bb-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="734bb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="734bb-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="734bb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="734bb-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="734bb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="734bb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="734bb-112">Description</span></span>

<span data-ttu-id="734bb-113">Il cmdlet Test-CsClientAuth consente di determinare se un utente può accedere al server Lync usando un certificato client, è possibile eseguire il cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="734bb-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="734bb-114">Dopo aver chiamato Test-CsClientAuth, il cmdlet contatterà il servizio di provisioning dei certificati e scaricherà una copia dei certificati client per l'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="734bb-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="734bb-115">Se è possibile trovare e scaricare un certificato client, Test-CsClientAuth cercherà di accedere tramite tale certificato.</span><span class="sxs-lookup"><span data-stu-id="734bb-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="734bb-116">Se l'accesso riesce, Test-CsClientAuth si disconnetterà e riferirà che il test è riuscito.</span><span class="sxs-lookup"><span data-stu-id="734bb-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="734bb-117">Se non è possibile trovare o scaricare un certificato oppure se il cmdlet non riesce ad accedere con tale certificato, Test-CsClientAuth segnalerà che il test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="734bb-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="734bb-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="734bb-118">Running the test</span></span>

<span data-ttu-id="734bb-119">Il cmdlet Test-CsClientAuth viene eseguito usando l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="734bb-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="734bb-120">Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password.</span><span class="sxs-lookup"><span data-stu-id="734bb-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="734bb-121">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando il sistema chiama Test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="734bb-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="734bb-122">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="734bb-122">For more information, see the Help documentation for the [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="734bb-123">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="734bb-123">Determining success or failure</span></span>

<span data-ttu-id="734bb-124">Se l'utente specificato può accedere a Lync Server usando un certificato client, si riceverà un output simile a questo, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="734bb-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="734bb-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="734bb-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="734bb-126">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="734bb-126">Result : Success</span></span>

<span data-ttu-id="734bb-127">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="734bb-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="734bb-128">Errore</span><span class="sxs-lookup"><span data-stu-id="734bb-128">Error :</span></span>

<span data-ttu-id="734bb-129">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="734bb-129">Diagnosis :</span></span>

<span data-ttu-id="734bb-130">Se l'utente specificato non riesce ad accedere, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="734bb-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="734bb-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="734bb-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="734bb-132">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="734bb-132">Result : Failure</span></span>

<span data-ttu-id="734bb-133">Latenza: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="734bb-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="734bb-134">Errore: non è stato possibile scaricare un certificato CS per l'utente specifico.</span><span class="sxs-lookup"><span data-stu-id="734bb-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="734bb-135">Verificare se</span><span class="sxs-lookup"><span data-stu-id="734bb-135">Check if</span></span>

<span data-ttu-id="734bb-136">URI e credenziali specificati sono corretti.</span><span class="sxs-lookup"><span data-stu-id="734bb-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="734bb-137">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="734bb-137">Diagnosis :</span></span>

<span data-ttu-id="734bb-138">Ad esempio, l'output precedente indica che il test non è riuscito perché un certificato client valido non è stato individuato per l'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="734bb-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="734bb-139">È possibile restituire un elenco dei certificati client rilasciati a un utente eseguendo un comando come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="734bb-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="734bb-140">Se Test-CsClientAuth non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="734bb-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="734bb-141">Quando viene incluso il parametro Verbose, Test-CsClientAuth restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="734bb-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="734bb-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="734bb-142">For example:</span></span>

<span data-ttu-id="734bb-143">Provare a scaricare un certificato CS per l'utente: kenmyer@litwareinc.com endpoint: STEpid</span><span class="sxs-lookup"><span data-stu-id="734bb-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="734bb-144">URL del servizio Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="734bb-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="734bb-145">Impossibile scaricare un certificato CS dal servizio Web.</span><span class="sxs-lookup"><span data-stu-id="734bb-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="734bb-146">CONTROLLO</span><span class="sxs-lookup"><span data-stu-id="734bb-146">CHECK:</span></span>

<span data-ttu-id="734bb-147">\-L'URL del servizio Web è valido e i servizi Web sono funzionali</span><span class="sxs-lookup"><span data-stu-id="734bb-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="734bb-148">\-Se si usa\\\\PhoneNo pin per eseguire l'autenticazione, verificare che corrispondano all'URI dell'utente</span><span class="sxs-lookup"><span data-stu-id="734bb-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="734bb-149">\-Se si usa\\l'autenticazione Kerberos NTLM, verificare che siano state fornite credenziali valide</span><span class="sxs-lookup"><span data-stu-id="734bb-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="734bb-150">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="734bb-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="734bb-151">Ecco alcuni motivi comuni per cui Test-CsClientAuth potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="734bb-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="734bb-152">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="734bb-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="734bb-153">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="734bb-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="734bb-154">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="734bb-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="734bb-155">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="734bb-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="734bb-156">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="734bb-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="734bb-157">L'utente di test potrebbe non avere un certificato client valido.</span><span class="sxs-lookup"><span data-stu-id="734bb-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="734bb-158">Puoi restituire informazioni sui certificati client assegnati a un utente usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="734bb-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

