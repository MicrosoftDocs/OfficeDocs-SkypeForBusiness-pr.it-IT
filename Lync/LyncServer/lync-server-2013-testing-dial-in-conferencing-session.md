---
title: 'Lync Server 2013: testing della sessione di conferenza telefonica con accesso esterno'
description: 'Lync Server 2013: testing della sessione di conferenza telefonica con accesso esterno.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d0c51b16df674dbf8bf7f0a2c6c4c93c2606d95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560632"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="6034c-103">Testing della sessione di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6034c-103">Testing dial-in conferencing session in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6034c-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6034c-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6034c-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="6034c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6034c-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="6034c-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6034c-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="6034c-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6034c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6034c-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6034c-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="6034c-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6034c-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6034c-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6034c-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="6034c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="6034c-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6034c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6034c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6034c-113">Description</span></span>

<span data-ttu-id="6034c-114">Il cmdlet Test-CsDialInConferencing verifica se un utente può partecipare a una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6034c-114">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="6034c-115">Test-CsDialInConferencing è compatibile con il tentativo di registrare un utente di test nel sistema.</span><span class="sxs-lookup"><span data-stu-id="6034c-115">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="6034c-116">Se l'accesso ha esito positivo, il cmdlet utilizzerà le credenziali e le autorizzazioni dell'utente per provare tutti i numeri di accesso per le conferenze telefoniche in ingresso disponibili.</span><span class="sxs-lookup"><span data-stu-id="6034c-116">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="6034c-117">L'esito positivo o negativo di ogni tentativo di accesso esterno verrà annotato, quindi l'utente di prova verrà disconnesso da Lync Server. Test-CsDialInConferencing verifica solo che sia possibile effettuare le connessioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="6034c-117">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="6034c-118">Con il cmdlet non vengono infatti effettuate chiamate telefoniche né create conferenze telefoniche con accesso esterno a cui possano partecipare altri utenti.</span><span class="sxs-lookup"><span data-stu-id="6034c-118">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6034c-119">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="6034c-119">Running the test</span></span>

<span data-ttu-id="6034c-120">È possibile eseguire il cmdlet Test-CsDialInConferencing utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6034c-120">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="6034c-121">Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="6034c-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="6034c-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6034c-122">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="6034c-123">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="6034c-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="6034c-124">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP account the calling Test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="6034c-124">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6034c-125">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="6034c-125">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6034c-126">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="6034c-126">Determining success or failure</span></span>

<span data-ttu-id="6034c-127">Se l'utente specificato può accedere a Lync Server e quindi eseguire una connessione utilizzando uno dei numeri di accesso per le conferenze telefoniche in ingresso disponibili, riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="6034c-127">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="6034c-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6034c-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6034c-129">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="6034c-129">Result : Success</span></span>

<span data-ttu-id="6034c-130">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="6034c-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="6034c-131">Errore</span><span class="sxs-lookup"><span data-stu-id="6034c-131">Error :</span></span>

<span data-ttu-id="6034c-132">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="6034c-132">Diagnosis :</span></span>

<span data-ttu-id="6034c-133">Se l'utente specificato non è in grado di effettuare questa connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="6034c-133">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6034c-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6034c-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6034c-135">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="6034c-135">Result : Failure</span></span>

<span data-ttu-id="6034c-136">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6034c-136">Latency : 00:00:00</span></span>

<span data-ttu-id="6034c-137">Errore: l'accesso è stato negato.</span><span class="sxs-lookup"><span data-stu-id="6034c-137">Error : The log on was denied.</span></span> <span data-ttu-id="6034c-138">Verificare che le credenziali appropriate siano</span><span class="sxs-lookup"><span data-stu-id="6034c-138">Check that the proper credentials are</span></span>

<span data-ttu-id="6034c-139">utilizzato e l'account è attivo.</span><span class="sxs-lookup"><span data-stu-id="6034c-139">being used and the account is active.</span></span>

<span data-ttu-id="6034c-140">Eccezione interna: NegotiateSecurityAssociation non riuscita, errore:-</span><span class="sxs-lookup"><span data-stu-id="6034c-140">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="6034c-141">2146893044</span><span class="sxs-lookup"><span data-stu-id="6034c-141">2146893044</span></span>

<span data-ttu-id="6034c-142">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="6034c-142">Diagnosis :</span></span>

<span data-ttu-id="6034c-143">L'output precedente indica che all'utente di test è stato negato l'accesso a Lync Server stesso.</span><span class="sxs-lookup"><span data-stu-id="6034c-143">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="6034c-144">Questo significa in genere che le credenziali utente passate a Test-CsDialInConferencing non sono valide.</span><span class="sxs-lookup"><span data-stu-id="6034c-144">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="6034c-145">A sua incirca, è necessario ricreare l'oggetto credenziali di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6034c-145">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="6034c-146">Anche se è possibile recuperare la password per l'account utente, è possibile verificare l'indirizzo SIP utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6034c-146">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6034c-147">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="6034c-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="6034c-148">Di seguito sono riportate alcune ragioni comuni per cui Test-CsDialInConferencing potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="6034c-148">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="6034c-149">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="6034c-149">You specified a user account that is not valid.</span></span> <span data-ttu-id="6034c-150">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6034c-150">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6034c-151">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6034c-151">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="6034c-152">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6034c-152">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6034c-153">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6034c-153">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="6034c-154">È possibile che si disponga di un numero di accesso per le conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="6034c-154">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="6034c-155">È possibile restituire l'elenco attualmente configurato dei numeri di accesso per le conferenze telefoniche con chiamata in ingresso utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6034c-155">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

