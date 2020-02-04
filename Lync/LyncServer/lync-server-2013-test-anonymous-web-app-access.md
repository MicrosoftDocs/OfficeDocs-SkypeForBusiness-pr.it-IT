---
title: "Lync Server 2013: verificare l'accesso anonimo all'app Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aabac9e106c325b7b1b964e6e594bb2b05ef85c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="5d553-102">Verificare l'accesso anonimo all'app Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d553-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d553-103">_**Argomento Ultima modifica:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="5d553-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d553-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="5d553-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5d553-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="5d553-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d553-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="5d553-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5d553-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d553-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d553-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="5d553-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5d553-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5d553-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5d553-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="5d553-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="5d553-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5d553-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5d553-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d553-112">Description</span></span>

<span data-ttu-id="5d553-113">Il cmdlet Test-CsWebAppAnonymous verifica che un utente anonimo possa partecipare a conferenze di Lync Server tramite Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5d553-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="5d553-114">Quando si esegue il cmdlet, Test-CsWebAppAnonymous Contatta il servizio ticket web per ottenere un ticket web per l'utente anonimo.</span><span class="sxs-lookup"><span data-stu-id="5d553-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="5d553-115">Se il cmdlet riesce a ottenere questo ticket, Test-CsWebAppAnonymous contatterà Lync Server e tenterà di stabilire conferenze separate per la messaggistica istantanea, la condivisione delle applicazioni e la collaborazione ai dati.</span><span class="sxs-lookup"><span data-stu-id="5d553-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="5d553-116">Tieni presente che Test-CsWebAppAnonymous verifica solo le API e le connessioni usate per creare queste conferenze.</span><span class="sxs-lookup"><span data-stu-id="5d553-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="5d553-117">Il cmdlet in realtà non crea e gestisce alcuna conferenza.</span><span class="sxs-lookup"><span data-stu-id="5d553-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5d553-118">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="5d553-118">Running the test</span></span>

<span data-ttu-id="5d553-119">Il cmdlet Test-CsWebAppAnonymous può essere eseguito usando una coppia di account di test preconfigurati o gli account di due utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d553-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="5d553-120">Per eseguire questo controllo con gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server testato.</span><span class="sxs-lookup"><span data-stu-id="5d553-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="5d553-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5d553-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="5d553-122">Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti credenziali di Lync Server Management Shell (oggetti che contengono il nome e la password dell'account) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="5d553-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="5d553-123">È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsWebAppAnonymous:</span><span class="sxs-lookup"><span data-stu-id="5d553-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="5d553-124">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="5d553-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="5d553-125">Tieni presente che Test-CsWebAppAnonymous è deprecato per l'uso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d553-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5d553-126">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="5d553-126">Determining success or failure</span></span>

<span data-ttu-id="5d553-127">Se Test-CsWebAppAnonymous può partecipare all'utente anonimo alle proprie conferenze, il cmdlet restituirà il risultato del test:</span><span class="sxs-lookup"><span data-stu-id="5d553-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="5d553-128">FQDN di destinazione:</span><span class="sxs-lookup"><span data-stu-id="5d553-128">Target Fqdn :</span></span>

<span data-ttu-id="5d553-129">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="5d553-129">Result : Success</span></span>

<span data-ttu-id="5d553-130">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5d553-130">Latency : 00:00:00</span></span>

<span data-ttu-id="5d553-131">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="5d553-131">Error Message :</span></span>

<span data-ttu-id="5d553-132">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="5d553-132">Diagnosis :</span></span>

<span data-ttu-id="5d553-133">Se l'utente anonimo non è in grado di partecipare alle conferenze necessarie, il risultato del test verrà contrassegnato come errore.</span><span class="sxs-lookup"><span data-stu-id="5d553-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="5d553-134">In genere Test-CsWebAppAnonymous riporterà anche un messaggio di errore e una diagnosi dettagliati:</span><span class="sxs-lookup"><span data-stu-id="5d553-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="5d553-135">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5d553-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5d553-136">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="5d553-136">Result : Failure</span></span>

<span data-ttu-id="5d553-137">Latenza: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="5d553-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="5d553-138">Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web</span><span class="sxs-lookup"><span data-stu-id="5d553-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="5d553-139">Diagnosi: la richiesta HTTP non è autorizzata con il client</span><span class="sxs-lookup"><span data-stu-id="5d553-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="5d553-140">schema di autenticazione "NTLM".</span><span class="sxs-lookup"><span data-stu-id="5d553-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="5d553-141">L'autenticazione</span><span class="sxs-lookup"><span data-stu-id="5d553-141">The authentication</span></span>

<span data-ttu-id="5d553-142">l'intestazione ricevuta dal server è "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="5d553-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5d553-143">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="5d553-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="5d553-144">Gli errori di Test-CsWebAppAnonymous in genere ruotano intorno a un errore di autenticazione degli utenti: è necessario eseguire il test usando un account utente valido anche se il cmdlet controlla la possibilità che un utente anonimo si connetta a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d553-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="5d553-145">Se Test-CsWebAppAnonymous non riesce, è necessario verificare che l'utente specificato abbia un account utente di Lync Server valido.</span><span class="sxs-lookup"><span data-stu-id="5d553-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="5d553-146">Puoi recuperare le informazioni sull'account di Lync Server usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5d553-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="5d553-147">Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido.</span><span class="sxs-lookup"><span data-stu-id="5d553-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="5d553-148">Devi anche verificare che la password specificata durante l'esecuzione del cmdlet sia una password valida.</span><span class="sxs-lookup"><span data-stu-id="5d553-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="5d553-149">I problemi di configurazione con Office Web Apps Server possono anche causare un errore di Test-CsWebAppAnonymous; Questo è spesso il caso se si riceve la diagnosi seguente:</span><span class="sxs-lookup"><span data-stu-id="5d553-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="5d553-150">La richiesta HTTP non è autorizzata con lo schema di autenticazione client "NTLM".</span><span class="sxs-lookup"><span data-stu-id="5d553-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="5d553-151">L'intestazione di autenticazione ricevuta dal server è "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="5d553-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="5d553-152">Per altre informazioni sulla diagnosi e la risoluzione dei problemi del server di Office Web Apps, vedere il post di Blog [Office Web Apps server 2013-i computer vengono sempre segnalati come non sani](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="5d553-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

