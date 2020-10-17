---
title: "Lync Server 2013: test dell'utilità di pianificazione Web"
description: "Lync Server 2013: test dell'utilità di pianificazione Web."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556152"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="36e00-103">Test dell'utilità di pianificazione Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36e00-103">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36e00-104">_**Ultimo argomento modificato:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="36e00-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36e00-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="36e00-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="36e00-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="36e00-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36e00-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="36e00-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="36e00-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36e00-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36e00-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="36e00-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="36e00-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="36e00-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="36e00-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="36e00-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="36e00-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="36e00-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="36e00-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36e00-113">Description</span></span>

<span data-ttu-id="36e00-114">Il cmdlet **Test-CsWebScheduler** consente di determinare se un utente specifico può pianificare una riunione utilizzando l'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="36e00-114">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="36e00-115">L'utilità di pianificazione Web consente agli utenti che non eseguono Outlook di pianificare riunioni online.</span><span class="sxs-lookup"><span data-stu-id="36e00-115">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="36e00-116">Tra le altre cose, questa nuova funzionalità, che include le funzionalità trovate nello strumento utilità di pianificazione Web inclusa in Microsoft Lync Server 2010 Resource Kit, consente agli utenti di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36e00-116">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="36e00-117">Pianificare una nuova riunione online.</span><span class="sxs-lookup"><span data-stu-id="36e00-117">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="36e00-118">Elencare tutte le riunioni pianificate.</span><span class="sxs-lookup"><span data-stu-id="36e00-118">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="36e00-119">Visualizzare/modificare una riunione esistente.</span><span class="sxs-lookup"><span data-stu-id="36e00-119">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="36e00-120">Eliminare una riunione esistente.</span><span class="sxs-lookup"><span data-stu-id="36e00-120">Delete an existing meeting.</span></span>

  - <span data-ttu-id="36e00-121">Inviare un invito tramite posta elettronica ai partecipanti di una riunione utilizzando un server di posta elettronica SMTP preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="36e00-121">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="36e00-122">Partecipare a una conferenza esistente.</span><span class="sxs-lookup"><span data-stu-id="36e00-122">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="36e00-123">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="36e00-123">Running the test</span></span>

<span data-ttu-id="36e00-124">Nell'esempio seguente viene verificata l'utilità di pianificazione Web per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="36e00-124">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="36e00-125">Questo comando funzionerà solo se gli utenti di test sono definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="36e00-125">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="36e00-126">Se necessario, il comando determinerà se il primo utente di test può pianificare una riunione online utilizzando l'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="36e00-126">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="36e00-127">Se gli utenti di test non sono definiti, il comando avrà esito negativo perché non è in grado di individuare l'utente a cui eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="36e00-127">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="36e00-128">Se non sono stati definiti gli utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'utente che il comando deve utilizzare quando si tenta di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="36e00-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="36e00-129">Nei comandi illustrati nell'esempio seguente viene verificata la capacità di un utente specifico (litwareinc \\ kenmeyer) di pianificare una riunione online tramite l'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="36e00-129">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="36e00-130">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="36e00-130">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="36e00-131">Poiché il nome di accesso litwareinc \\ kenmeyer è incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Ken Meyer. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="36e00-131">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="36e00-132">Il secondo comando verifica quindi se l'utente può accedere al pool atl-cs-001.litwareinc.com e pianificare una riunione online.</span><span class="sxs-lookup"><span data-stu-id="36e00-132">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="36e00-133">Per eseguire questa attività, viene chiamato il cmdlet **Test-CsWebScheduler** , insieme a tre parametri: TargetFqdn (il nome di dominio completo del pool di registrazione). UserCredential (l'oggetto di Windows PowerShell che contiene le credenziali utente di Pilar Ackerman); e UserSipAddress (l'indirizzo SIP corrispondente alle credenziali utente fornite).</span><span class="sxs-lookup"><span data-stu-id="36e00-133">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="36e00-134">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="36e00-134">Determining success or failure</span></span>

<span data-ttu-id="36e00-135">Se l'utilità di pianificazione Web è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="36e00-135">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="36e00-136">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36e00-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="36e00-137">URI di destinazione: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="36e00-137">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="36e00-138">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="36e00-138">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="36e00-139">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="36e00-139">Result : Success</span></span>

<span data-ttu-id="36e00-140">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="36e00-140">Latency : 00:00:00</span></span>

<span data-ttu-id="36e00-141">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="36e00-141">Error Message :</span></span>

<span data-ttu-id="36e00-142">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="36e00-142">Diagnosis :</span></span>

<span data-ttu-id="36e00-143">Se l'utilità di pianificazione Web non è configurata correttamente, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="36e00-143">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="36e00-144">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="36e00-144">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="36e00-145">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="36e00-145">domain name (FQDN).</span></span> <span data-ttu-id="36e00-146">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="36e00-146">Using default Registrar port number.</span></span> <span data-ttu-id="36e00-147">Eccezione</span><span class="sxs-lookup"><span data-stu-id="36e00-147">Exception:</span></span>

<span data-ttu-id="36e00-148">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="36e00-148">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="36e00-149">a</span><span class="sxs-lookup"><span data-stu-id="36e00-149">at</span></span>

<span data-ttu-id="36e00-150">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="36e00-150">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="36e00-151">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="36e00-151">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="36e00-152">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36e00-152">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="36e00-153">URI di destinazione:</span><span class="sxs-lookup"><span data-stu-id="36e00-153">Target Uri :</span></span>

<span data-ttu-id="36e00-154">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="36e00-154">Result : Failure</span></span>

<span data-ttu-id="36e00-155">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="36e00-155">Latency : 00:00:00</span></span>

<span data-ttu-id="36e00-156">Messaggio di errore: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="36e00-156">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="36e00-157">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="36e00-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="36e00-158">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="36e00-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="36e00-159">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsWebScheduler** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="36e00-159">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="36e00-160">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="36e00-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="36e00-161">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="36e00-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="36e00-162">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="36e00-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="36e00-163">Questo comando avrà esito negativo se l'utilità di pianificazione Web non è stata configurata correttamente o non è stata ancora distribuita.</span><span class="sxs-lookup"><span data-stu-id="36e00-163">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36e00-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36e00-164">See Also</span></span>


[<span data-ttu-id="36e00-165">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="36e00-165">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

