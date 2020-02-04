---
title: "Lync Server 2013: test dell'accesso all'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d5d216a1d7a389f20bf2c59f94baf54636d409
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="c03f6-102">Test dell'accesso all'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c03f6-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c03f6-103">_**Argomento Ultima modifica:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c03f6-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c03f6-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="c03f6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c03f6-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="c03f6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03f6-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="c03f6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c03f6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c03f6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03f6-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="c03f6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c03f6-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c03f6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c03f6-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="c03f6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="c03f6-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c03f6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c03f6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c03f6-112">Description</span></span>

<span data-ttu-id="c03f6-113">L'archivio contatti unificato introdotto in Lync Server 2013 offre agli amministratori la possibilità di archiviare i contatti di un utente in Microsoft Exchange Server 2013 anziché in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c03f6-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="c03f6-114">In questo modo l'utente deve accedere allo stesso set di contatti in Outlook Web Access oltre a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c03f6-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="c03f6-115">In alternativa, è possibile continuare a archiviare i contatti in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c03f6-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="c03f6-116">In questo caso, gli utenti dovranno gestire due set distinti di contatti: uno da usare con Outlook e Outlook Web Access e uno da usare con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c03f6-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="c03f6-117">È possibile determinare se i contatti di un utente sono stati spostati nell'archivio contatti unificato eseguendo il cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="c03f6-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="c03f6-118">Il cmdlet **Test-CsUnifiedContactStore** prenderà l'account utente specificato, si collegherà all'archivio contatti unificato e tenterà di recuperare un contatto per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c03f6-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="c03f6-119">Se non è possibile recuperare contatti, il comando non riuscirà insieme al messaggio "non sono stati ricevuti contatti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c03f6-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="c03f6-120">Verificare che i contatti siano presenti per l'utente. "</span><span class="sxs-lookup"><span data-stu-id="c03f6-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="c03f6-121">Si noti che il cmdlet **Test-CsUnifiedContactStore** non riesce se l'utente ha eseguito correttamente la migrazione nell'archivio contatti unificato, ma non ha contatti nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="c03f6-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="c03f6-122">Per completare correttamente il cmdlet **Test-CsUnifiedContactStore** , l'utente specificato deve avere almeno un contatto.</span><span class="sxs-lookup"><span data-stu-id="c03f6-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c03f6-123">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="c03f6-123">Running the test</span></span>

<span data-ttu-id="c03f6-124">I comandi mostrati nell'esempio seguente determinano se i contatti per l'\\utente litwareinc kenmyer possono essere trovati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="c03f6-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="c03f6-125">A questo scopo, il primo comando nell'esempio usa il cmdlet **Get-Credential** per creare un oggetto credenziali dell'interfaccia della riga di comando di Windows PowerShell per l'\\utente litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="c03f6-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="c03f6-126">Tieni presente che devi specificare la password per questo account per creare un oggetto credenziali valido e per verificare che il cmdlet **Test-CsUnifiedContactStore** possa eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="c03f6-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="c03f6-127">Il secondo comando nell'esempio usa l'oggetto credentials fornito ($x) e l'indirizzo SIP dell'utente litwareinc\\kenmyer per determinare se i contatti sono disponibili nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="c03f6-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c03f6-128">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="c03f6-128">Determining success or failure</span></span>

<span data-ttu-id="c03f6-129">Se l'accesso all'archivio contatti è configurato correttamente, si riceverà un output simile al seguente, con la proprietà Result contrassegnata come **riuscita:**</span><span class="sxs-lookup"><span data-stu-id="c03f6-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c03f6-130">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c03f6-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c03f6-131">Risultato: successo</span><span class="sxs-lookup"><span data-stu-id="c03f6-131">Result : Success</span></span>

<span data-ttu-id="c03f6-132">Latenza: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="c03f6-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="c03f6-133">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="c03f6-133">Error Message :</span></span>

<span data-ttu-id="c03f6-134">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="c03f6-134">Diagnosis :</span></span>

<span data-ttu-id="c03f6-135">Se l'accesso all'archivio contatti non è configurato correttamente, il risultato verrà visualizzato come **errore**e verranno registrate altre informazioni nelle proprietà errore e diagnosi:</span><span class="sxs-lookup"><span data-stu-id="c03f6-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c03f6-136">AVVISO: non è stato possibile leggere il numero di porta del registrar per l'elenco completo</span><span class="sxs-lookup"><span data-stu-id="c03f6-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c03f6-137">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="c03f6-137">domain name (FQDN).</span></span> <span data-ttu-id="c03f6-138">Uso del numero di porta registrar predefinito.</span><span class="sxs-lookup"><span data-stu-id="c03f6-138">Using default Registrar port number.</span></span> <span data-ttu-id="c03f6-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="c03f6-139">Exception:</span></span>

<span data-ttu-id="c03f6-140">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="c03f6-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c03f6-141">a</span><span class="sxs-lookup"><span data-stu-id="c03f6-141">at</span></span>

<span data-ttu-id="c03f6-142">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="c03f6-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c03f6-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c03f6-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c03f6-144">Nome di dominio completo di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c03f6-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c03f6-145">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="c03f6-145">Result : Failure</span></span>

<span data-ttu-id="c03f6-146">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c03f6-146">Latency : 00:00:00</span></span>

<span data-ttu-id="c03f6-147">Messaggio di errore: 10060, il tentativo di connessione non è riuscito perché l'entità connessa</span><span class="sxs-lookup"><span data-stu-id="c03f6-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c03f6-148">non ha risposto correttamente dopo un periodo di tempo o</span><span class="sxs-lookup"><span data-stu-id="c03f6-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c03f6-149">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="c03f6-149">established connection failed because connected host has</span></span>

<span data-ttu-id="c03f6-150">Impossibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c03f6-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c03f6-151">Eccezione interna: tentativo di connessione non riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="c03f6-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c03f6-152">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="c03f6-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c03f6-153">l'ora o la connessione stabilita non è riuscita perché l'host connesso</span><span class="sxs-lookup"><span data-stu-id="c03f6-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c03f6-154">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c03f6-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c03f6-155">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="c03f6-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c03f6-156">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="c03f6-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="c03f6-157">Ecco alcuni motivi comuni per cui **Test-CsUnifiedContactStore** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="c03f6-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="c03f6-158">È stato specificato un valore di parametro errato.</span><span class="sxs-lookup"><span data-stu-id="c03f6-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c03f6-159">Se usato, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c03f6-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c03f6-160">Rieseguire il comando senza i parametri facoltativi e verificare se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="c03f6-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c03f6-161">Connettersi all'archivio contatti unificato non riuscito e il tentativo di recuperare un contatto per l'utente non è stato possibile.</span><span class="sxs-lookup"><span data-stu-id="c03f6-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="c03f6-162">Potrebbero verificarsi problemi di connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="c03f6-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c03f6-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c03f6-163">See Also</span></span>


[<span data-ttu-id="c03f6-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="c03f6-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="c03f6-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="c03f6-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

