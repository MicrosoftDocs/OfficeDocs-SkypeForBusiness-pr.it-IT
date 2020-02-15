---
title: 'Lync Server 2013: testing della sessione di conferenza telefonica con accesso esterno'
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
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="3e258-102">Testing della sessione di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e258-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e258-103">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3e258-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e258-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="3e258-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3e258-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="3e258-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e258-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="3e258-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3e258-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e258-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e258-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="3e258-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3e258-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3e258-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3e258-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="3e258-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="3e258-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3e258-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3e258-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e258-112">Description</span></span>

<span data-ttu-id="3e258-113">Il cmdlet Test-CsDialInConferencing verifica se un utente può partecipare a una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3e258-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="3e258-114">Test-CsDialInConferencing funziona cercando di registrare un utente di test nel sistema.</span><span class="sxs-lookup"><span data-stu-id="3e258-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="3e258-115">Se l'accesso ha esito positivo, il cmdlet utilizzerà le credenziali e le autorizzazioni dell'utente per provare tutti i numeri di accesso per le conferenze telefoniche in ingresso disponibili.</span><span class="sxs-lookup"><span data-stu-id="3e258-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="3e258-116">L'esito positivo o negativo di ogni tentativo di accesso esterno verrà annotato, quindi l'utente di prova verrà disconnesso da Lync Server. Test-CsDialInConferencing verifica solo che sia possibile effettuare le connessioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="3e258-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="3e258-117">Con il cmdlet non vengono infatti effettuate chiamate telefoniche né create conferenze telefoniche con accesso esterno a cui possano partecipare altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3e258-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3e258-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="3e258-118">Running the test</span></span>

<span data-ttu-id="3e258-119">È possibile eseguire il cmdlet Test-CsDialInConferencing utilizzando un account di test preconfigurato (vedere Configurazione degli account di prova per l'esecuzione di test di Lync Server) oppure l'account di qualsiasi utente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e258-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="3e258-120">Per eseguire questo controllo utilizzando un account di prova, è sufficiente specificare il nome di dominio completo del pool di Lync Server da testare.</span><span class="sxs-lookup"><span data-stu-id="3e258-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3e258-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3e258-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="3e258-122">Per eseguire questo controllo utilizzando un account utente effettivo, è necessario creare un oggetto credenziali di Windows PowerShell contenente il nome e la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="3e258-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="3e258-123">È quindi necessario includere l'oggetto credentials e l'indirizzo SIP account the calling Test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="3e258-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="3e258-124">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="3e258-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3e258-125">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="3e258-125">Determining success or failure</span></span>

<span data-ttu-id="3e258-126">Se l'utente specificato può accedere a Lync Server e quindi eseguire una connessione utilizzando uno dei numeri di accesso per le conferenze telefoniche in ingresso disponibili, riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="3e258-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3e258-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3e258-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3e258-128">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="3e258-128">Result : Success</span></span>

<span data-ttu-id="3e258-129">Latenza: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="3e258-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="3e258-130">Errore</span><span class="sxs-lookup"><span data-stu-id="3e258-130">Error :</span></span>

<span data-ttu-id="3e258-131">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="3e258-131">Diagnosis :</span></span>

<span data-ttu-id="3e258-132">Se l'utente specificato non è in grado di effettuare questa connessione, il risultato verrà visualizzato come errore e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="3e258-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3e258-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3e258-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3e258-134">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="3e258-134">Result : Failure</span></span>

<span data-ttu-id="3e258-135">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3e258-135">Latency : 00:00:00</span></span>

<span data-ttu-id="3e258-136">Errore: l'accesso è stato negato.</span><span class="sxs-lookup"><span data-stu-id="3e258-136">Error : The log on was denied.</span></span> <span data-ttu-id="3e258-137">Verificare che le credenziali appropriate siano</span><span class="sxs-lookup"><span data-stu-id="3e258-137">Check that the proper credentials are</span></span>

<span data-ttu-id="3e258-138">utilizzato e l'account è attivo.</span><span class="sxs-lookup"><span data-stu-id="3e258-138">being used and the account is active.</span></span>

<span data-ttu-id="3e258-139">Eccezione interna: NegotiateSecurityAssociation non riuscita, errore:-</span><span class="sxs-lookup"><span data-stu-id="3e258-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="3e258-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="3e258-140">2146893044</span></span>

<span data-ttu-id="3e258-141">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="3e258-141">Diagnosis :</span></span>

<span data-ttu-id="3e258-142">L'output precedente indica che all'utente di test è stato negato l'accesso a Lync Server stesso.</span><span class="sxs-lookup"><span data-stu-id="3e258-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="3e258-143">Questo significa in genere che le credenziali utente passate a Test-CsDialInConferencing non erano valide.</span><span class="sxs-lookup"><span data-stu-id="3e258-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="3e258-144">A sua incirca, è necessario ricreare l'oggetto credenziali di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e258-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="3e258-145">Anche se è possibile recuperare la password per l'account utente, è possibile verificare l'indirizzo SIP utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3e258-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3e258-146">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3e258-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="3e258-147">Di seguito sono riportate alcune ragioni comuni per cui Test-CsDialInConferencing potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="3e258-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="3e258-148">È stato specificato un account utente non valido.</span><span class="sxs-lookup"><span data-stu-id="3e258-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="3e258-149">È possibile verificare che esista un account utente eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3e258-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3e258-150">L'account utente è valido, ma l'account non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e258-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3e258-151">Per verificare che un account utente sia abilitato per Lync Server, eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3e258-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="3e258-152">Se la proprietà Enabled è impostata su false, significa che l'utente non è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e258-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="3e258-153">È possibile che si disponga di un numero di accesso per le conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="3e258-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="3e258-154">È possibile restituire l'elenco attualmente configurato dei numeri di accesso per le conferenze telefoniche con chiamata in ingresso utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3e258-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

