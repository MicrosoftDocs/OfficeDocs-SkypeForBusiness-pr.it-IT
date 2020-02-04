---
title: "Lync Server 2013: convalida dell'accesso alla Rubrica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="d3e3e-102">Convalida dell'accesso alla Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3e3e-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e3e-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d3e3e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3e3e-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="d3e3e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d3e3e-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="d3e3e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e3e-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="d3e3e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d3e3e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3e3e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e3e-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="d3e3e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d3e3e-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d3e3e-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="d3e3e-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d3e3e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3e3e-112">Description</span></span>

<span data-ttu-id="d3e3e-113">Il cmdlet Test-CsAddressBookService offre un modo per verificare che un utente possa connettersi al servizio Web di download rubrica.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="d3e3e-114">Quando si esegue il cmdlet, Test-CsAddressBookService si connette al servizio Web di download rubrica nel pool specificato e richiede la posizione dei file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="d3e3e-115">Se il servizio Web di download della Rubrica fornisce tale posizione, il test viene considerato riuscito.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="d3e3e-116">Se la richiesta viene rifiutata, il test viene considerato un errore.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d3e3e-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="d3e3e-117">Running the test</span></span>

<span data-ttu-id="d3e3e-118">Il cmdlet Test-CsAddressBookService può essere eseguito usando un account di test preconfigurato (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="d3e3e-119">Per eseguire questo controllo usando un account di prova, è sufficiente specificare il nome di dominio completo (FQDN) del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="d3e3e-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d3e3e-121">Per eseguire questo controllo usando un account utente effettivo, è necessario prima di tutto creare un oggetto credenziali di Windows PowerShell contenente il nome dell'account e la password.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="d3e3e-122">Devi quindi includere l'oggetto credenziali e l'indirizzo SIP assegnato all'account quando chiami Test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d3e3e-123">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="d3e3e-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d3e3e-124">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="d3e3e-124">Determining success or failure</span></span>

<span data-ttu-id="d3e3e-125">Se l'utente specificato è in grado di connettersi al servizio Rubrica, verrà restituito l'output simile a questo, con la proprietà Result contrassegnata come **riuscita**:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="d3e3e-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="d3e3e-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="d3e3e-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d3e3e-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d3e3e-128">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="d3e3e-128">Result : Success</span></span>

<span data-ttu-id="d3e3e-129">Latenza: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="d3e3e-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="d3e3e-130">Errore</span><span class="sxs-lookup"><span data-stu-id="d3e3e-130">Error :</span></span>

<span data-ttu-id="d3e3e-131">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="d3e3e-131">Diagnosis :</span></span>

<span data-ttu-id="d3e3e-132">Se l'utente specificato non è in grado di eseguire questa connessione, il risultato verrà visualizzato come errore e le informazioni aggiuntive verranno registrate nelle proprietà Error e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d3e3e-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="d3e3e-133">TargetUri :</span></span>

<span data-ttu-id="d3e3e-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d3e3e-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d3e3e-135">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="d3e3e-135">Result : Failure</span></span>

<span data-ttu-id="d3e3e-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d3e3e-136">Latency : 00:00:00</span></span>

<span data-ttu-id="d3e3e-137">Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="d3e3e-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="d3e3e-138">Reason = URI di destinazione non abilitato per SIP o non</span><span class="sxs-lookup"><span data-stu-id="d3e3e-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="d3e3e-139">esiste.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-139">exist.</span></span>

<span data-ttu-id="d3e3e-140">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d3e3e-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d3e3e-141">Ad esempio, l'output precedente indica che il test non è riuscito perché l'utente specificato (ovvero "URI di destinazione") non esiste o non è stato abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="d3e3e-142">È possibile verificare se un account utente è valido e verificare che sia stato fornito l'indirizzo SIP corretto eseguendo un comando come questo:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="d3e3e-143">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span><span class="sxs-lookup"><span data-stu-id="d3e3e-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="d3e3e-144">Se Test-CsAddressBookService non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="d3e3e-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="d3e3e-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="d3e3e-146">Quando il parametro Verbose è incluso Test-CsAddressBookService restituirà un account dettagliato di ogni azione che ha tentato quando controlla la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d3e3e-147">Ad esempio, questo output di esempio mostra che Test-CsAddressBookService, almeno in questo esempio, è stato in grado di scaricare il file della Rubrica:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="d3e3e-148">Invio della richiesta GET HTTP.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-148">Sending Http GET Request.</span></span>

<span data-ttu-id="d3e3e-149">Percorso file =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="d3e3e-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="d3e3e-150">Numero tentativo = 1</span><span class="sxs-lookup"><span data-stu-id="d3e3e-150">Attempt Number = 1</span></span>

<span data-ttu-id="d3e3e-151">TimeOut (msec) = 60000</span><span class="sxs-lookup"><span data-stu-id="d3e3e-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="d3e3e-152">È stato scaricato correttamente il file ABShttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="d3e3e-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d3e3e-153">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="d3e3e-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="d3e3e-154">Ecco alcuni motivi comuni per cui Test-CsAddressBookService potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="d3e3e-155">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-155">You specified an invalid user account.</span></span> <span data-ttu-id="d3e3e-156">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d3e3e-157">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="d3e3e-158">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d3e3e-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d3e3e-159">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3e3e-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3e3e-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3e3e-160">See Also</span></span>


[<span data-ttu-id="d3e3e-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="d3e3e-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

