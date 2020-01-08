---
title: "Lync Server 2013: verificare l'accesso alle app Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d118f019883bd5c0f00295bb92287c9593192a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="147ea-102">Verificare l'accesso alle app Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="147ea-102">Test Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="147ea-103">_**Argomento Ultima modifica:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="147ea-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="147ea-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="147ea-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="147ea-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="147ea-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="147ea-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="147ea-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="147ea-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="147ea-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="147ea-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="147ea-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="147ea-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="147ea-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="147ea-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsWebApp.</span><span class="sxs-lookup"><span data-stu-id="147ea-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="147ea-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="147ea-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="147ea-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="147ea-112">Description</span></span>

<span data-ttu-id="147ea-113">Il cmdlet Test-CsWebApp verifica che gli utenti autenticati possano partecipare a conferenze di Lync Server tramite Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="147ea-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="147ea-114">Quando si esegue il cmdlet, Test-CsWebApp Contatta il servizio ticket web per ottenere i ticket web per gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="147ea-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="147ea-115">Questi biglietti agiscono efficacemente come "ticket di ammissione" alla conferenza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="147ea-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="147ea-116">Se i ticket possono essere recuperati e se gli utenti possono essere autenticati, Test-CsWebApp contatterà Lync Server e tenterà di stabilire conferenze separate per la messaggistica istantanea, la condivisione delle applicazioni e la collaborazione ai dati.</span><span class="sxs-lookup"><span data-stu-id="147ea-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="147ea-117">Tieni presente che Test-CsWebApp verifica solo le API e le connessioni usate per creare queste conferenze.</span><span class="sxs-lookup"><span data-stu-id="147ea-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="147ea-118">Il cmdlet è progettato per verificare che Lync Web app possa essere usato per creare e partecipare a conferenze.</span><span class="sxs-lookup"><span data-stu-id="147ea-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="147ea-119">Tuttavia, in realtà non crea e conduce una conferenza.</span><span class="sxs-lookup"><span data-stu-id="147ea-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="147ea-120">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="147ea-120">Running the test</span></span>

<span data-ttu-id="147ea-121">Il cmdlet Test-CsWebApp può essere eseguito usando una coppia di account di test preconfigurati o gli account di due utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="147ea-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="147ea-122">Per eseguire questo controllo con gli account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server testato.</span><span class="sxs-lookup"><span data-stu-id="147ea-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="147ea-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="147ea-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="147ea-124">Per eseguire questo controllo usando gli account utente effettivi, devi creare due oggetti delle credenziali di Windows PowerShell (oggetti che contengono il nome dell'account e la password) per ogni account.</span><span class="sxs-lookup"><span data-stu-id="147ea-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="147ea-125">È quindi necessario includere tali oggetti Credentials e gli indirizzi SIP dei due account quando si chiama Test-CsWebApp:</span><span class="sxs-lookup"><span data-stu-id="147ea-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="147ea-126">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="147ea-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="147ea-127">Tieni presente che Test-CsWebApp è stato deprecato per l'uso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="147ea-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="147ea-128">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="147ea-128">Determining success or failure</span></span>

<span data-ttu-id="147ea-129">Se Test-CsWebApp può partecipare agli utenti alle proprie conferenze, il cmdlet restituirà il risultato del test:</span><span class="sxs-lookup"><span data-stu-id="147ea-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="147ea-130">FQDN di destinazione:</span><span class="sxs-lookup"><span data-stu-id="147ea-130">Target Fqdn :</span></span>

<span data-ttu-id="147ea-131">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="147ea-131">Result : Success</span></span>

<span data-ttu-id="147ea-132">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="147ea-132">Latency : 00:00:00</span></span>

<span data-ttu-id="147ea-133">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="147ea-133">Error Message :</span></span>

<span data-ttu-id="147ea-134">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="147ea-134">Diagnosis :</span></span>

<span data-ttu-id="147ea-135">Se gli utenti non possono partecipare alle conferenze necessarie, il risultato del test verrà contrassegnato come errore.</span><span class="sxs-lookup"><span data-stu-id="147ea-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="147ea-136">In genere Test-CsWebApp riporterà anche un messaggio di errore e una diagnosi dettagliati:</span><span class="sxs-lookup"><span data-stu-id="147ea-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="147ea-137">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="147ea-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="147ea-138">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="147ea-138">Result : Failure</span></span>

<span data-ttu-id="147ea-139">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="147ea-139">Latency : 00:00:00</span></span>

<span data-ttu-id="147ea-140">Messaggio di errore: nessuna risposta ricevuta per il servizio Ticket Web</span><span class="sxs-lookup"><span data-stu-id="147ea-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="147ea-141">Diagnosi: la richiesta HTTP non è autorizzata con il client</span><span class="sxs-lookup"><span data-stu-id="147ea-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="147ea-142">schema di autenticazione "NTLM".</span><span class="sxs-lookup"><span data-stu-id="147ea-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="147ea-143">L'autenticazione</span><span class="sxs-lookup"><span data-stu-id="147ea-143">The authentication</span></span>

<span data-ttu-id="147ea-144">l'intestazione ricevuta dal server è "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="147ea-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="147ea-145">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="147ea-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="147ea-146">Gli errori di Test-CsWebApp in genere comportano errore di autenticazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="147ea-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="147ea-147">Se Test-CsWebApp non riesce, verificare prima di tutto che gli utenti specificati dispongano di account utente validi e siano abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="147ea-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="147ea-148">Puoi recuperare le informazioni dell'account usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="147ea-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="147ea-149">Se la proprietà Enabled non è uguale a true o se il comando non riesce, significa che l'utente non ha un account di Lync Server valido. Dovresti anche verificare che le password fornite al cmdlet siano valide.</span><span class="sxs-lookup"><span data-stu-id="147ea-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

