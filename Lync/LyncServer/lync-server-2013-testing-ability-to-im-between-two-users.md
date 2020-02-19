---
title: 'Lync Server 2013: verifica della capacità di messaggistica istantanea tra due utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0573e668915737ea09cfb660ac7c7b72f237ed83
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="41a59-102">Verifica della capacità di messaggistica istantanea tra due utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a59-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a59-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="41a59-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41a59-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="41a59-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="41a59-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="41a59-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41a59-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="41a59-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="41a59-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41a59-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41a59-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="41a59-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="41a59-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="41a59-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="41a59-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="41a59-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="41a59-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41a59-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="41a59-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41a59-112">Description</span></span>

<span data-ttu-id="41a59-113">Il cmdlet Test-CsIM verifica che una coppia di utenti di test sia in grado di scambiare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="41a59-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="41a59-114">Quando viene chiamato, il cmdlet Test-CsIM inizia cercando di accedere a una coppia di utenti di test a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41a59-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="41a59-115">Presupponendo che i due accessi abbiano esito positivo, il cmdlet avvia quindi una sessione di messaggistica istantanea tra i due utenti di test.</span><span class="sxs-lookup"><span data-stu-id="41a59-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="41a59-116">(L'utente 1 invita l'utente 2 a una sessione di messaggistica istantanea e l'utente 2 accetta l'invito). Dopo aver verificato che i messaggi possono essere scambiati tra i due utenti, Test-CsIM quindi termina la sessione di messaggistica istantanea e disconnette entrambi gli utenti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="41a59-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="41a59-117">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="41a59-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="41a59-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="41a59-118">Running the Test</span></span>

<span data-ttu-id="41a59-119">Il cmdlet Test-CsIM può essere eseguito utilizzando una coppia di account di test preconfigurati (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure gli account di tutti e due gli utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41a59-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="41a59-120">Per eseguire questo controllo utilizzando gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="41a59-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="41a59-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41a59-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="41a59-122">Per eseguire questo controllo utilizzando account utente effettivi, è necessario creare due oggetti credenziali di Windows PowerShell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="41a59-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="41a59-123">Quando si chiama Test-CsIM, è necessario includere gli oggetti Credential e gli indirizzi SIP dei due account:</span><span class="sxs-lookup"><span data-stu-id="41a59-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="41a59-124">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="41a59-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="41a59-125">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="41a59-125">Determining Success or Failure</span></span>

<span data-ttu-id="41a59-126">Se i due utenti possono completare una sessione di messaggistica istantanea, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="41a59-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="41a59-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="41a59-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="41a59-128">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="41a59-128">Result : Success</span></span>

<span data-ttu-id="41a59-129">Latenza: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="41a59-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="41a59-130">Errore</span><span class="sxs-lookup"><span data-stu-id="41a59-130">Error :</span></span>

<span data-ttu-id="41a59-131">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="41a59-131">Diagnosis :</span></span>

<span data-ttu-id="41a59-132">Se gli utenti di test non sono in grado di completare la sessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="41a59-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="41a59-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="41a59-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="41a59-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="41a59-134">Result : Failure</span></span>

<span data-ttu-id="41a59-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="41a59-135">Latency : 00:00:00</span></span>

<span data-ttu-id="41a59-136">Errore: 504, timeout del server</span><span class="sxs-lookup"><span data-stu-id="41a59-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="41a59-137">Diagnosi: ErrorCode = 2, source = atl-cs-001. litwareinc. com, Reason = See</span><span class="sxs-lookup"><span data-stu-id="41a59-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="41a59-138">codice di risposta e frase del motivo.</span><span class="sxs-lookup"><span data-stu-id="41a59-138">response code and reason phrase.</span></span>

<span data-ttu-id="41a59-139">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="41a59-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="41a59-140">Ad esempio, l'output precedente dichiara che il test ha avuto esito negativo perché l'utente specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="41a59-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="41a59-141">È possibile determinare se un indirizzo SIP è valido (e se l'utente assegnato l'indirizzo SIP è stato abilitato per Lync Server) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="41a59-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="41a59-142">Se Test-CsIM ha esito negativo, potrebbe essere necessario eseguire nuovamente il test, che include il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="41a59-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="41a59-143">Quando viene incluso il parametro Verbose, Test-CsIM restituirà un account dettagliato di ogni azione che ha provato quando ha verificato la capacità dei due utenti di test di prendere parte a una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="41a59-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="41a59-144">Ad esempio, ecco l'output di esempio che si verifica quando viene fornito un set di credenziali utente non corretto (in questo caso una password non corretta) a Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="41a59-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="41a59-145">Invio della richiesta di registrazione:</span><span class="sxs-lookup"><span data-stu-id="41a59-145">Sending Registration request :</span></span>

<span data-ttu-id="41a59-146">FQDN di destinazione = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="41a59-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="41a59-147">Indirizzo SIP dell'utente = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="41a59-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="41a59-148">Porta di registrazione = 5061</span><span class="sxs-lookup"><span data-stu-id="41a59-148">Registrar Port = 5061</span></span>

<span data-ttu-id="41a59-149">Il tipo di autenticazione ' IWA ' è selezionato.</span><span class="sxs-lookup"><span data-stu-id="41a59-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="41a59-150">Hit di registrazione per SIP/atl-cs-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="41a59-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="41a59-151">Attività' Register ' completata in ' 0,0601795' secs.</span><span class="sxs-lookup"><span data-stu-id="41a59-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="41a59-152">Eccezione ' il login è stato negato.</span><span class="sxs-lookup"><span data-stu-id="41a59-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="41a59-153">Verificare che le credenziali corrette vengano utilizzate e che l'account sia attivo.</span><span class="sxs-lookup"><span data-stu-id="41a59-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="41a59-154">si è verificato durante il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="41a59-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="41a59-155">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="41a59-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="41a59-156">Di seguito sono riportate alcune ragioni comuni per cui Test-CsIM potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="41a59-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="41a59-157">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="41a59-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="41a59-158">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="41a59-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="41a59-159">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41a59-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="41a59-160">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="41a59-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="41a59-161">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41a59-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="41a59-162">Il servizio di messaggistica istantanea potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="41a59-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="41a59-163">Con Lync Server, è possibile configurare il sistema in modo che la messaggistica istantanea non sia disponibile se non è possibile accedere al database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="41a59-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="41a59-164">È possibile verificare che eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="41a59-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="41a59-165">Se BlockOnArchiveFailure è impostato su true, è necessario determinare se il database di archiviazione è disponibile o meno.</span><span class="sxs-lookup"><span data-stu-id="41a59-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="41a59-166">È possibile restituire le posizioni dei database di archiviazione utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="41a59-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="41a59-167">Il server di archiviazione potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="41a59-167">The Archiving server might not be available.</span></span> <span data-ttu-id="41a59-168">Per recuperare il nome di dominio completo dei server di archiviazione, è possibile utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="41a59-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="41a59-169">È quindi possibile eseguire il ping del server appropriato per verificare che sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="41a59-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="41a59-170">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41a59-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

