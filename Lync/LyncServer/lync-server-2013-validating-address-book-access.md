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
ms.openlocfilehash: 665ee384afd85c4be5c82182691953e1c78c9659
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="2b17f-102">Convalida dell'accesso alla Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b17f-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b17f-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2b17f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b17f-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="2b17f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2b17f-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="2b17f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b17f-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="2b17f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2b17f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b17f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b17f-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="2b17f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2b17f-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2b17f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2b17f-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="2b17f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="2b17f-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b17f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2b17f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b17f-112">Description</span></span>

<span data-ttu-id="2b17f-113">Il cmdlet Test-CsAddressBookService consente di verificare che un utente possa connettersi al servizio Web di download della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="2b17f-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="2b17f-114">Quando si esegue il cmdlet, Test-CsAddressBookService si connette al servizio Web per il download della Rubrica nel pool specificato e richiede il percorso dei file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="2b17f-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="2b17f-115">Se il servizio Web di download della Rubrica fornisce tale percorso, il test viene considerato completato.</span><span class="sxs-lookup"><span data-stu-id="2b17f-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="2b17f-116">Se la richiesta viene rifiutata, l'esito del test è negativo.</span><span class="sxs-lookup"><span data-stu-id="2b17f-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2b17f-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="2b17f-117">Running the test</span></span>

<span data-ttu-id="2b17f-118">È possibile eseguire il cmdlet Test-CsAddressBookService utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b17f-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="2b17f-119">Per eseguire questo controllo utilizzando un account di prova, è necessario specificare il nome di dominio completo (FQDN) del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="2b17f-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="2b17f-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2b17f-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="2b17f-121">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario innanzitutto creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="2b17f-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="2b17f-122">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP assegnato all'account quando si chiama Test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="2b17f-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="2b17f-123">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="2b17f-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2b17f-124">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="2b17f-124">Determining success or failure</span></span>

<span data-ttu-id="2b17f-125">Se l'utente specificato è in grado di connettersi al servizio Rubrica, verrà restituito un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="2b17f-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="2b17f-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="2b17f-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="2b17f-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2b17f-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2b17f-128">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="2b17f-128">Result : Success</span></span>

<span data-ttu-id="2b17f-129">Latenza: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="2b17f-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="2b17f-130">Errore</span><span class="sxs-lookup"><span data-stu-id="2b17f-130">Error :</span></span>

<span data-ttu-id="2b17f-131">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="2b17f-131">Diagnosis :</span></span>

<span data-ttu-id="2b17f-132">Se l'utente specificato non è in grado di effettuare questa connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="2b17f-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2b17f-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="2b17f-133">TargetUri :</span></span>

<span data-ttu-id="2b17f-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2b17f-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2b17f-135">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="2b17f-135">Result : Failure</span></span>

<span data-ttu-id="2b17f-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="2b17f-136">Latency : 00:00:00</span></span>

<span data-ttu-id="2b17f-137">Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="2b17f-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="2b17f-138">Reason = URI di destinazione non abilitato per SIP o non</span><span class="sxs-lookup"><span data-stu-id="2b17f-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="2b17f-139">esiste.</span><span class="sxs-lookup"><span data-stu-id="2b17f-139">exist.</span></span>

<span data-ttu-id="2b17f-140">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="2b17f-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="2b17f-141">Ad esempio, l'output precedente indica che il test ha avuto esito negativo perché l'utente specificato (ovvero "URI di destinazione") non esiste o non è stato abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b17f-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="2b17f-142">È possibile verificare se un account utente è valido e verificare di aver fornito l'indirizzo SIP corretto eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2b17f-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="2b17f-143">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, abilitato</span><span class="sxs-lookup"><span data-stu-id="2b17f-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="2b17f-144">Se Test-CsAddressBookService ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="2b17f-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="2b17f-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="2b17f-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="2b17f-146">Quando viene incluso il parametro Verbose Test-CsAddressBookService restituirà un account dettagliato di ogni azione tentata quando si verifica la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b17f-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2b17f-147">Ad esempio, in questo output di esempio viene mostrato che Test-CsAddressBookService, almeno in questo esempio, è stato in grado di scaricare il file della Rubrica:</span><span class="sxs-lookup"><span data-stu-id="2b17f-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="2b17f-148">Invio della richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="2b17f-148">Sending Http GET Request.</span></span>

<span data-ttu-id="2b17f-149">Percorso file =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="2b17f-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="2b17f-150">Numero tentativo = 1</span><span class="sxs-lookup"><span data-stu-id="2b17f-150">Attempt Number = 1</span></span>

<span data-ttu-id="2b17f-151">TimeOut (msec) = 60000</span><span class="sxs-lookup"><span data-stu-id="2b17f-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="2b17f-152">Scaricato correttamente il file ABShttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="2b17f-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2b17f-153">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="2b17f-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="2b17f-154">Di seguito sono riportate alcune ragioni comuni per cui Test-CsAddressBookService potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="2b17f-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="2b17f-155">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="2b17f-155">You specified an invalid user account.</span></span> <span data-ttu-id="2b17f-156">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2b17f-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2b17f-157">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b17f-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="2b17f-158">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2b17f-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2b17f-159">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b17f-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b17f-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b17f-160">See Also</span></span>


[<span data-ttu-id="2b17f-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="2b17f-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

