---
title: 'Lync Server 2013: verificare la pubblicazione e la sottoscrizione della presenza utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d506ed0115fd5346048ff8870763a7ffc888a69
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="d48eb-102">Test della pubblicazione e della sottoscrizione della presenza utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48eb-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d48eb-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d48eb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d48eb-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="d48eb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d48eb-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="d48eb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48eb-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="d48eb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d48eb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d48eb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48eb-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="d48eb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d48eb-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d48eb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d48eb-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsPresence.</span><span class="sxs-lookup"><span data-stu-id="d48eb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="d48eb-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d48eb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d48eb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48eb-112">Description</span></span>

<span data-ttu-id="d48eb-113">Test-CsPresence viene usato per determinare se una coppia di utenti di test può accedere a Lync Server e quindi scambiare le informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="d48eb-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="d48eb-114">A questo scopo, il cmdlet esegue prima di tutto il log dei due utenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d48eb-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="d48eb-115">Se entrambi gli accessi hanno esito positivo, il primo utente di test chiede quindi di ricevere le informazioni sulla presenza dal secondo utente.</span><span class="sxs-lookup"><span data-stu-id="d48eb-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="d48eb-116">Il secondo utente pubblica queste informazioni e Test-CsPresence verifica che le informazioni siano state trasmesse correttamente al primo utente.</span><span class="sxs-lookup"><span data-stu-id="d48eb-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="d48eb-117">Dopo lo scambio di informazioni sulla presenza, i due utenti di test vengono disconnessi da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d48eb-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d48eb-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="d48eb-118">Running the test</span></span>

<span data-ttu-id="d48eb-119">Il cmdlet Test-CsPresence può essere eseguito usando una coppia di account di test preconfigurati (vedere Configurazione degli account di test per l'esecuzione di test Lync Server) o degli account di due utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d48eb-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d48eb-120">Per eseguire questo controllo usando gli account di prova, devi solo specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="d48eb-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d48eb-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d48eb-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d48eb-122">Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="d48eb-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d48eb-123">È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsPresence:</span><span class="sxs-lookup"><span data-stu-id="d48eb-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="d48eb-124">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="d48eb-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d48eb-125">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="d48eb-125">Determining success or failure</span></span>

<span data-ttu-id="d48eb-126">Se gli utenti specificati possono scambiare le informazioni sulla presenza, riceverai un output simile a questo, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="d48eb-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d48eb-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d48eb-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d48eb-128">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="d48eb-128">Result : Success</span></span>

<span data-ttu-id="d48eb-129">Latenza: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="d48eb-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="d48eb-130">Errore</span><span class="sxs-lookup"><span data-stu-id="d48eb-130">Error :</span></span>

<span data-ttu-id="d48eb-131">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="d48eb-131">Diagnosis :</span></span>

<span data-ttu-id="d48eb-132">Se i due utenti non possono scambiare le informazioni sulla presenza, il risultato verrà visualizzato come errore e verranno registrate altre informazioni nelle proprietà di errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="d48eb-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d48eb-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d48eb-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d48eb-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="d48eb-134">Result : Failure</span></span>

<span data-ttu-id="d48eb-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d48eb-135">Latency : 00:00:00</span></span>

<span data-ttu-id="d48eb-136">Errore: 404, non trovato</span><span class="sxs-lookup"><span data-stu-id="d48eb-136">Error : 404, Not Found</span></span>

<span data-ttu-id="d48eb-137">Diagnosi: ErrorCode = 4005, source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="d48eb-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="d48eb-138">Reason = URI di destinazione non abilitato per SIP o non</span><span class="sxs-lookup"><span data-stu-id="d48eb-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="d48eb-139">esiste.</span><span class="sxs-lookup"><span data-stu-id="d48eb-139">exist.</span></span>

<span data-ttu-id="d48eb-140">Microsoft. Rtc. signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d48eb-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d48eb-141">Ad esempio, l'output precedente indica che il test non è riuscito perché almeno uno dei due account utente non è valido: l'account non esiste o non è stato abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d48eb-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="d48eb-142">È possibile verificare che gli account esistano e determinare se sono abilitati per Lync Server eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d48eb-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="d48eb-143">Se Test-CsPresence non riesce, potrebbe essere necessario rieseguire il test, questa volta includendo il parametro Verbose:</span><span class="sxs-lookup"><span data-stu-id="d48eb-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="d48eb-144">Quando viene incluso il parametro Verbose, Test-CsPresence restituirà un account dettagliato di ogni azione provata quando ha verificato la capacità dell'utente specificato di accedere a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d48eb-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d48eb-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d48eb-145">For example:</span></span>

<span data-ttu-id="d48eb-146">Richiesta di registrazione incentrata su sconosciuto</span><span class="sxs-lookup"><span data-stu-id="d48eb-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="d48eb-147">Attività "Register" completata in "0,0345791" secs.</span><span class="sxs-lookup"><span data-stu-id="d48eb-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="d48eb-148">Attività' SelfSubscribeActivity ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="d48eb-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="d48eb-149">Attività "SelfSubscribeActivity" completata in "0,0041174" secs.</span><span class="sxs-lookup"><span data-stu-id="d48eb-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="d48eb-150">Attività' SubscribePresence ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="d48eb-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="d48eb-151">Attività "SubscribePresence" completata in "0,0038764" secs.</span><span class="sxs-lookup"><span data-stu-id="d48eb-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="d48eb-152">Attività' PublishPresence ' iniziata.</span><span class="sxs-lookup"><span data-stu-id="d48eb-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="d48eb-153">La notifica di presenza di un'eccezione non viene ricevuta entro 25 secondi.</span><span class="sxs-lookup"><span data-stu-id="d48eb-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="d48eb-154">si è verificato rovinato flusso di lavoro Microsoft. Rtc. SyntheticTransactions. flussi di lavoro. STPresenceWorkflow esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d48eb-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="d48eb-155">Il fatto che la notifica di presenza non sia stata ricevuta entro 25 secondi potrebbe indicare che i problemi di rete impediscono lo scambio di informazioni.</span><span class="sxs-lookup"><span data-stu-id="d48eb-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d48eb-156">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="d48eb-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="d48eb-157">Ecco alcuni motivi comuni per cui Test-CsPresence potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="d48eb-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="d48eb-158">È stato specificato un account utente non corretto.</span><span class="sxs-lookup"><span data-stu-id="d48eb-158">You specified an incorrect user account.</span></span> <span data-ttu-id="d48eb-159">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d48eb-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d48eb-160">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d48eb-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d48eb-161">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d48eb-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d48eb-162">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d48eb-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

