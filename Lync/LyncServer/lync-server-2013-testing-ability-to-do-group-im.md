---
title: 'Lync Server 2013: testare la capacità di eseguire un gruppo di messaggistica istantanea'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef76c8728a7b5a569efee9305505f4e19f6bceb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="ced01-102">Verifica della capacità di eseguire un gruppo di messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ced01-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ced01-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ced01-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ced01-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ced01-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ced01-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="ced01-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced01-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="ced01-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ced01-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ced01-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced01-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ced01-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ced01-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ced01-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ced01-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="ced01-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="ced01-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ced01-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ced01-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ced01-112">Description</span></span>

<span data-ttu-id="ced01-113">Il cmdlet Test-CsGroupIM verifica che gli utenti dell'organizzazione possano condurre sessioni di messaggistica istantanea di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ced01-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="ced01-114">Quando si esegue Test-CsGroupIM, il cmdlet tenta di accedere a una coppia di utenti di test a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ced01-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="ced01-115">Se l'accesso riesce, il cmdlet Test-CsGroupIM crea una nuova conferenza utilizzando il primo utente di test, quindi invita il secondo utente a parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="ced01-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="ced01-116">Dopo uno scambio di messaggi, entrambi gli utenti vengono disconnessi dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ced01-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="ced01-117">Si noti che tutto questo accade senza alcuna interazione dell'utente e senza influire su eventuali utenti effettivi.</span><span class="sxs-lookup"><span data-stu-id="ced01-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="ced01-118">Si supponga, ad esempio, che l'account di test sip:kenmyer@litwareinc.com corrisponda a un utente reale che dispone di un account Lync Server reale.</span><span class="sxs-lookup"><span data-stu-id="ced01-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="ced01-119">In questo caso, il test verrà eseguito senza coinvolgere il vero Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="ced01-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="ced01-120">Ad esempio, anche quando l'account di test di Ken Myer si disconnette, il vero Ken Myer resterà connesso al sistema.</span><span class="sxs-lookup"><span data-stu-id="ced01-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="ced01-121">Analogamente, il vero Ken non riceverà un invito a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ced01-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="ced01-122">L'invio verrà inviato all'account di test e da quest'ultimo accettato.</span><span class="sxs-lookup"><span data-stu-id="ced01-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="ced01-123">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="ced01-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ced01-124">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="ced01-124">Running the test</span></span>

<span data-ttu-id="ced01-125">Il cmdlet Test-CsGroupIM può essere eseguito utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ced01-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="ced01-126">Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="ced01-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="ced01-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ced01-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ced01-128">Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Lync Server Management Shell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="ced01-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ced01-129">Quando si chiama Test-CsGroupIM, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:</span><span class="sxs-lookup"><span data-stu-id="ced01-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="ced01-130">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="ced01-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ced01-131">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ced01-131">Determining Success or Failure</span></span>

<span data-ttu-id="ced01-132">Se i due utenti possono completare una sessione di messaggistica istantanea di gruppo, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="ced01-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ced01-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ced01-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ced01-134">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="ced01-134">Result : Success</span></span>

<span data-ttu-id="ced01-135">Latenza: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="ced01-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="ced01-136">Errore</span><span class="sxs-lookup"><span data-stu-id="ced01-136">Error :</span></span>

<span data-ttu-id="ced01-137">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="ced01-137">Diagnosis :</span></span>

<span data-ttu-id="ced01-138">Se i due utenti non sono in grado di completare la sessione di messaggistica istantanea, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="ced01-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ced01-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ced01-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ced01-140">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="ced01-140">Result : Failure</span></span>

<span data-ttu-id="ced01-141">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ced01-141">Latency : 00:00:00</span></span>

<span data-ttu-id="ced01-142">Errore: 404, non trovato</span><span class="sxs-lookup"><span data-stu-id="ced01-142">Error : 404, Not Found</span></span>

<span data-ttu-id="ced01-143">Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="ced01-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="ced01-144">Reason = URI di destinazione non abilitato per SIP o non</span><span class="sxs-lookup"><span data-stu-id="ced01-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="ced01-145">esiste.</span><span class="sxs-lookup"><span data-stu-id="ced01-145">exist.</span></span>

<span data-ttu-id="ced01-146">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="ced01-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="ced01-147">L'output precedente dichiara che il test ha avuto esito negativo perché almeno uno degli account di test non era valido, perché l'account non esiste o perché l'utente non è stato abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ced01-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="ced01-148">È possibile verificare l'esistenza dell'account e se l'account è stato abilitato per Nm-OCS-14-3rd eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ced01-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="ced01-149">Se Test-CsGroupIM ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="ced01-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="ced01-150">Quando viene incluso il parametro Verbose, Test-CsGroupIM restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità degli utenti specificati di partecipare a sessioni di messaggistica istantanea di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="ced01-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="ced01-151">Ad esempio, se il test ha esito negativo e si dice che uno o più account utente non sono validi, è possibile rieseguire il test utilizzando il parametro Verbose e determinare quale account utente non è valido:</span><span class="sxs-lookup"><span data-stu-id="ced01-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="ced01-152">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="ced01-152">Sending Registration request:</span></span>

 <span data-ttu-id="ced01-153">FQDN di destinazione = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ced01-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="ced01-154">Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ced01-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="ced01-155">Registrazione porta = 5061</span><span class="sxs-lookup"><span data-stu-id="ced01-155">Register Port    = 5061</span></span>

<span data-ttu-id="ced01-156">Il tipo di autenticazione ' IWA ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="ced01-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="ced01-157">Eccezione ' il login è stato negato.</span><span class="sxs-lookup"><span data-stu-id="ced01-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="ced01-158">Verificare che le credenziali corrette vengano utilizzate e che l'account sia attivo.</span><span class="sxs-lookup"><span data-stu-id="ced01-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="ced01-159">Come si può notare, in questo esempio l'utente con l'indirizzo SIP sip:kenmyer@litwareinc.com non è stato in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ced01-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ced01-160">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="ced01-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="ced01-161">Di seguito sono riportate alcune ragioni comuni per cui Test-CsGroupIM potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ced01-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="ced01-162">È stato specificato un account utente non corretto.</span><span class="sxs-lookup"><span data-stu-id="ced01-162">You specified an incorrect user account.</span></span> <span data-ttu-id="ced01-163">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ced01-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ced01-164">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ced01-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="ced01-165">Per verificare che un account utente sia stato abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ced01-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="ced01-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span><span class="sxs-lookup"><span data-stu-id="ced01-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="ced01-167">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ced01-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="ced01-168">Il servizio di messaggistica istantanea potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="ced01-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="ced01-169">Con Lync Server, è possibile configurare il sistema in modo che la messaggistica istantanea non sia disponibile se non è possibile accedere al database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ced01-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="ced01-170">È possibile verificare che eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ced01-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="ced01-171">Se BlockOnArchiveFailure è impostato su true, è necessario determinare se il database di archiviazione è disponibile o meno.</span><span class="sxs-lookup"><span data-stu-id="ced01-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="ced01-172">È possibile restituire le posizioni dei database di archiviazione utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ced01-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="ced01-173">Il server di archiviazione potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="ced01-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="ced01-174">Per recuperare il nome di dominio completo dei server di archiviazione, è possibile utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ced01-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="ced01-175">È quindi possibile eseguire il ping del server appropriato per verificare che sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="ced01-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="ced01-176">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ced01-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

