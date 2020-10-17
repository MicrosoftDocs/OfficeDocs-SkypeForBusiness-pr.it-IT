---
title: "Lync Server 2013: test dell'utilità di pianificazione Web"
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
ms.openlocfilehash: b385184486cdbf8e2ee18956df1546d09335e6c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503943"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="f5d91-102">Test dell'utilità di pianificazione Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5d91-102">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5d91-103">_**Ultimo argomento modificato:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="f5d91-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5d91-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="f5d91-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f5d91-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="f5d91-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5d91-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="f5d91-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f5d91-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5d91-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5d91-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="f5d91-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f5d91-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5d91-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f5d91-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="f5d91-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="f5d91-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f5d91-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f5d91-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5d91-112">Description</span></span>

<span data-ttu-id="f5d91-113">Il cmdlet **Test-CsWebScheduler** consente di determinare se un utente specifico può pianificare una riunione utilizzando l'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="f5d91-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="f5d91-114">L'utilità di pianificazione Web consente agli utenti che non eseguono Outlook di pianificare riunioni online.</span><span class="sxs-lookup"><span data-stu-id="f5d91-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="f5d91-115">Tra le altre cose, questa nuova funzionalità, che include le funzionalità trovate nello strumento utilità di pianificazione Web inclusa in Microsoft Lync Server 2010 Resource Kit, consente agli utenti di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5d91-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="f5d91-116">Pianificare una nuova riunione online.</span><span class="sxs-lookup"><span data-stu-id="f5d91-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="f5d91-117">Elencare tutte le riunioni pianificate.</span><span class="sxs-lookup"><span data-stu-id="f5d91-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="f5d91-118">Visualizzare/modificare una riunione esistente.</span><span class="sxs-lookup"><span data-stu-id="f5d91-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="f5d91-119">Eliminare una riunione esistente.</span><span class="sxs-lookup"><span data-stu-id="f5d91-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="f5d91-120">Inviare un invito tramite posta elettronica ai partecipanti di una riunione utilizzando un server di posta elettronica SMTP preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="f5d91-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="f5d91-121">Partecipare a una conferenza esistente.</span><span class="sxs-lookup"><span data-stu-id="f5d91-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f5d91-122">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="f5d91-122">Running the test</span></span>

<span data-ttu-id="f5d91-123">Nell'esempio seguente viene verificata l'utilità di pianificazione Web per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5d91-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f5d91-124">Questo comando funzionerà solo se gli utenti di test sono definiti per il pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5d91-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f5d91-125">Se necessario, il comando determinerà se il primo utente di test può pianificare una riunione online utilizzando l'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="f5d91-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="f5d91-126">Se gli utenti di test non sono definiti, il comando avrà esito negativo perché non è in grado di individuare l'utente a cui eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f5d91-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="f5d91-127">Se non sono stati definiti gli utenti di test per un pool, è necessario includere il parametro UserSipAddress e le credenziali dell'utente che il comando deve utilizzare quando si tenta di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f5d91-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f5d91-128">Nei comandi illustrati nell'esempio seguente viene verificata la capacità di un utente specifico (litwareinc \\ kenmeyer) di pianificare una riunione online tramite l'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="f5d91-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="f5d91-129">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto credenziale dell'interfaccia della riga di comando di Windows PowerShell contenente il nome e la password dell'utente Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="f5d91-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="f5d91-130">Poiché il nome di accesso litwareinc \\ kenmeyer è incluso come parametro, la finestra di dialogo richiesta credenziali di Windows PowerShell richiede solo all'amministratore di immettere la password per l'account Ken Meyer. L'oggetto Credential risultante viene quindi memorizzato in una variabile denominata $cred 1.</span><span class="sxs-lookup"><span data-stu-id="f5d91-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="f5d91-131">Il secondo comando verifica quindi se l'utente può accedere al pool atl-cs-001.litwareinc.com e pianificare una riunione online.</span><span class="sxs-lookup"><span data-stu-id="f5d91-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="f5d91-132">Per eseguire questa attività, viene chiamato il cmdlet **Test-CsWebScheduler** , insieme a tre parametri: TargetFqdn (il nome di dominio completo del pool di registrazione). UserCredential (l'oggetto di Windows PowerShell che contiene le credenziali utente di Pilar Ackerman); e UserSipAddress (l'indirizzo SIP corrispondente alle credenziali utente fornite).</span><span class="sxs-lookup"><span data-stu-id="f5d91-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f5d91-133">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="f5d91-133">Determining success or failure</span></span>

<span data-ttu-id="f5d91-134">Se l'utilità di pianificazione Web è configurata correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita**:</span><span class="sxs-lookup"><span data-stu-id="f5d91-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="f5d91-135">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5d91-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f5d91-136">URI di destinazione: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5d91-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="f5d91-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="f5d91-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="f5d91-138">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="f5d91-138">Result : Success</span></span>

<span data-ttu-id="f5d91-139">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f5d91-139">Latency : 00:00:00</span></span>

<span data-ttu-id="f5d91-140">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="f5d91-140">Error Message :</span></span>

<span data-ttu-id="f5d91-141">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="f5d91-141">Diagnosis :</span></span>

<span data-ttu-id="f5d91-142">Se l'utilità di pianificazione Web non è configurata correttamente, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="f5d91-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f5d91-143">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="f5d91-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="f5d91-144">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f5d91-144">domain name (FQDN).</span></span> <span data-ttu-id="f5d91-145">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="f5d91-145">Using default Registrar port number.</span></span> <span data-ttu-id="f5d91-146">Eccezione</span><span class="sxs-lookup"><span data-stu-id="f5d91-146">Exception:</span></span>

<span data-ttu-id="f5d91-147">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="f5d91-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="f5d91-148">a</span><span class="sxs-lookup"><span data-stu-id="f5d91-148">at</span></span>

<span data-ttu-id="f5d91-149">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="f5d91-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="f5d91-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="f5d91-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="f5d91-151">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5d91-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f5d91-152">URI di destinazione:</span><span class="sxs-lookup"><span data-stu-id="f5d91-152">Target Uri :</span></span>

<span data-ttu-id="f5d91-153">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="f5d91-153">Result : Failure</span></span>

<span data-ttu-id="f5d91-154">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f5d91-154">Latency : 00:00:00</span></span>

<span data-ttu-id="f5d91-155">Messaggio di errore: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="f5d91-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="f5d91-156">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="f5d91-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f5d91-157">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="f5d91-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="f5d91-158">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsWebScheduler** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="f5d91-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="f5d91-159">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="f5d91-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f5d91-160">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f5d91-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f5d91-161">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f5d91-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f5d91-162">Questo comando avrà esito negativo se l'utilità di pianificazione Web non è stata configurata correttamente o non è stata ancora distribuita.</span><span class="sxs-lookup"><span data-stu-id="f5d91-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5d91-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5d91-163">See Also</span></span>


[<span data-ttu-id="f5d91-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="f5d91-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

