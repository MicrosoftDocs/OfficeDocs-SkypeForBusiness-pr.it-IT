---
title: "Lync Server 2013: verifica dell'accesso all'archivio contatti unificato"
description: "Lync Server 2013: verifica dell'accesso all'archivio contatti unificato."
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
ms.openlocfilehash: 58238685133c51130c414e0d7a8cd761d0233f5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556082"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="19f48-103">Verifica dell'accesso all'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19f48-103">Testing Unified Contact Store access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19f48-104">_**Ultimo argomento modificato:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="19f48-104">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19f48-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="19f48-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="19f48-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="19f48-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19f48-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="19f48-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="19f48-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19f48-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19f48-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="19f48-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="19f48-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="19f48-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="19f48-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="19f48-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="19f48-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="19f48-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="19f48-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19f48-113">Description</span></span>

<span data-ttu-id="19f48-114">L'archivio contatti unificato introdotto in Lync Server 2013 fornisce agli amministratori la possibilità di archiviare i contatti di un utente in Microsoft Exchange Server 2013 anziché in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19f48-114">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="19f48-115">In questo modo l'utente può accedere allo stesso gruppo di contatti in Outlook Web Access oltre che a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="19f48-115">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="19f48-116">In alternativa, è possibile continuare a archiviare i contatti in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19f48-116">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="19f48-117">In tal caso, gli utenti dovranno gestire due gruppi di contatti distinti: uno per l'utilizzo con Outlook e Outlook Web Access e uno per l'utilizzo con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="19f48-117">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="19f48-118">È possibile determinare se i contatti di un utente sono stati spostati nell'archivio contatti unificato eseguendo il cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="19f48-118">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="19f48-119">Il cmdlet **Test-CsUnifiedContactStore** prenderà l'account utente specificato, si connetterà all'archivio contatti unificato e tenterà di recuperare un contatto per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19f48-119">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="19f48-120">Se non è possibile recuperare i contatti, il comando avrà esito negativo insieme al messaggio "non sono stati ricevuti contatti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19f48-120">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="19f48-121">Verificare che esistano contatti per l'utente".</span><span class="sxs-lookup"><span data-stu-id="19f48-121">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="19f48-122">Si noti che il cmdlet **Test-CsUnifiedContactStore** avrà esito negativo se l'utente ha eseguito correttamente la migrazione nell'archivio contatti unificato, ma non ha contatti nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="19f48-122">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="19f48-123">L'utente specificato deve disporre di almeno un contatto per il completamento corretto del cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="19f48-123">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="19f48-124">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="19f48-124">Running the test</span></span>

<span data-ttu-id="19f48-125">I comandi riportati nell'esempio seguente determinano se i contatti per l'utente litwareinc \\ kenmyer possono essere trovati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="19f48-125">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="19f48-126">A tale scopo, nel primo comando dell'esempio viene utilizzato il cmdlet **Get-Credential** per creare un oggetto Credentials dell'interfaccia della riga di comando di Windows PowerShell per l'utente litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="19f48-126">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="19f48-127">Tenere presente che è necessario fornire la password per l'account per creare un oggetto credentials valido e per assicurarsi che il cmdlet **Test-CsUnifiedContactStore** possa eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="19f48-127">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="19f48-128">Il secondo comando dell'esempio utilizza l'oggetto credenziali fornito ($x) e l'indirizzo SIP dell'utente litwareinc \\ kenmyer per determinare se i contatti possono essere trovati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="19f48-128">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="19f48-129">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="19f48-129">Determining success or failure</span></span>

<span data-ttu-id="19f48-130">Se l'accesso all'archivio contatti è configurato in modo corretto, verrà visualizzato un output simile al seguente, con la proprietà Result contrassegnata come **operazione riuscita:**</span><span class="sxs-lookup"><span data-stu-id="19f48-130">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="19f48-131">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="19f48-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="19f48-132">Risultato: esito positivo</span><span class="sxs-lookup"><span data-stu-id="19f48-132">Result : Success</span></span>

<span data-ttu-id="19f48-133">Latenza: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="19f48-133">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="19f48-134">Messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="19f48-134">Error Message :</span></span>

<span data-ttu-id="19f48-135">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="19f48-135">Diagnosis :</span></span>

<span data-ttu-id="19f48-136">Se l'accesso all'archivio contatti non è configurato correttamente, il risultato verrà visualizzato come **errore**e verranno registrate informazioni aggiuntive nelle proprietà Error and Diagnostic:</span><span class="sxs-lookup"><span data-stu-id="19f48-136">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="19f48-137">AVVISO: Impossibile leggere il numero di porta del servizio di registrazione per il dato completo</span><span class="sxs-lookup"><span data-stu-id="19f48-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="19f48-138">nome di dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="19f48-138">domain name (FQDN).</span></span> <span data-ttu-id="19f48-139">Utilizzo del numero di porta di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="19f48-139">Using default Registrar port number.</span></span> <span data-ttu-id="19f48-140">Eccezione</span><span class="sxs-lookup"><span data-stu-id="19f48-140">Exception:</span></span>

<span data-ttu-id="19f48-141">System. InvalidOperationException: nessun cluster corrispondente trovato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="19f48-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="19f48-142">a</span><span class="sxs-lookup"><span data-stu-id="19f48-142">at</span></span>

<span data-ttu-id="19f48-143">Microsoft. Rtc. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="19f48-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="19f48-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="19f48-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="19f48-145">FQDN di destinazione: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="19f48-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="19f48-146">Risultato: errore</span><span class="sxs-lookup"><span data-stu-id="19f48-146">Result : Failure</span></span>

<span data-ttu-id="19f48-147">Latenza: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="19f48-147">Latency : 00:00:00</span></span>

<span data-ttu-id="19f48-148">Messaggio di errore: 10060, un tentativo di connessione non è riuscito perché la parte connessa</span><span class="sxs-lookup"><span data-stu-id="19f48-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="19f48-149">non ha risposto correttamente dopo un determinato periodo di tempo oppure</span><span class="sxs-lookup"><span data-stu-id="19f48-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="19f48-150">connessione stabilita non riuscita perché l'host connesso ha</span><span class="sxs-lookup"><span data-stu-id="19f48-150">established connection failed because connected host has</span></span>

<span data-ttu-id="19f48-151">non è stato possibile rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="19f48-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="19f48-152">Eccezione interna: un tentativo di connessione non è riuscito perché il</span><span class="sxs-lookup"><span data-stu-id="19f48-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="19f48-153">la parte connessa non ha risposto correttamente dopo un periodo di</span><span class="sxs-lookup"><span data-stu-id="19f48-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="19f48-154">Data/ora o connessione stabilita non riuscita perché host connesso</span><span class="sxs-lookup"><span data-stu-id="19f48-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="19f48-155">non è riuscito a rispondere 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="19f48-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="19f48-156">Diagnosi</span><span class="sxs-lookup"><span data-stu-id="19f48-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="19f48-157">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="19f48-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="19f48-158">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsUnifiedContactStore** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="19f48-158">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="19f48-159">È stato specificato un valore di parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="19f48-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="19f48-160">Se si utilizza questo parametro, i parametri facoltativi devono essere configurati correttamente o il test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="19f48-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="19f48-161">Rieseguire il comando senza i parametri facoltativi e verificare se tale operazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="19f48-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="19f48-162">La connessione all'archivio contatti unificato ha avuto esito negativo e non è stato possibile eseguire il tentativo di recupero di un contatto per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19f48-162">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="19f48-163">Potrebbero verificarsi problemi di connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="19f48-163">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19f48-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19f48-164">See Also</span></span>


[<span data-ttu-id="19f48-165">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="19f48-165">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="19f48-166">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="19f48-166">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

