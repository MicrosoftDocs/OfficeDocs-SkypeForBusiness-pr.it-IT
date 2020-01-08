---
title: 'Lync Server 2013: verifica della configurazione del nodo Watcher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d2c79de4f86e490244ef63948c263d8f387fc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="ed269-102">Verifica della configurazione del nodo Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed269-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed269-103">_**Argomento Ultima modifica:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="ed269-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed269-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="ed269-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ed269-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="ed269-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed269-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="ed269-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ed269-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed269-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed269-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="ed269-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ed269-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ed269-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ed269-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="ed269-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="ed269-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ed269-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ed269-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed269-112">Description</span></span>

<span data-ttu-id="ed269-113">Se si usa Microsoft System Center Operations Manager per monitorare Lync Server 2013, è possibile configurare "nodi Watcher": computer che eseguono periodicamente e automaticamente transazioni sintetiche per verificare che Lync Server funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="ed269-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="ed269-114">I nodi Watcher vengono assegnati ai pool e gestiti tramite i cmdlet **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ed269-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="ed269-115">Si noti che non è necessario installare i nodi Watcher se si usa System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ed269-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="ed269-116">È comunque possibile monitorare il sistema senza usare i nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="ed269-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="ed269-117">L'unica differenza è che tutte le transazioni sintetiche che si desidera eseguire devono essere richiamate manualmente anziché richiamate automaticamente da Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ed269-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="ed269-118">Il cmdlet **Test-CsWatcherNodeConfiguration** consente di verificare che un nodo Watcher sia stato configurato correttamente e sia stato assegnato a un pool di Lync Server 2013 valido.</span><span class="sxs-lookup"><span data-stu-id="ed269-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="ed269-119">Tieni presente che il cmdlet **Test-CsWatcherNodeConfiguration** deve essere eseguito nel nodo Watcher stesso.</span><span class="sxs-lookup"><span data-stu-id="ed269-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="ed269-120">Il cmdlet non può essere eseguito in computer remoti.</span><span class="sxs-lookup"><span data-stu-id="ed269-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ed269-121">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="ed269-121">Running the test</span></span>

<span data-ttu-id="ed269-122">Il comando seguente verifica le impostazioni di configurazione per ogni nodo Watcher che viene usato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ed269-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ed269-123">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="ed269-123">Determining success or failure</span></span>

<span data-ttu-id="ed269-124">L'output di esempio riuscito seguente mostra un sistema con quattro server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="ed269-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="ed269-125">Convalida della atl-cs-001.litwareinc.com del pool di destinazione rispetto alla topologia.</span><span class="sxs-lookup"><span data-stu-id="ed269-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="ed269-126">Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com esiste nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ed269-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="ed269-127">Operazione riuscita: pool di destinazione atl-cs-001.litwareinc.com ha installato il ruolo di registrar.</span><span class="sxs-lookup"><span data-stu-id="ed269-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="ed269-128">Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com è supportato.</span><span class="sxs-lookup"><span data-stu-id="ed269-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="ed269-129">Operazione riuscita: numero di porta per il pool di destinazione di 5061 atl-cs-001.litwareinc.com è corretto.</span><span class="sxs-lookup"><span data-stu-id="ed269-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="ed269-130">Viene avviato il controllo dei pool mancanti nella configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="ed269-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="ed269-131">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="ed269-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="ed269-132">Il controllo dei pool mancanti nella configurazione del nodo Watcher è terminato.</span><span class="sxs-lookup"><span data-stu-id="ed269-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="ed269-133">Viene avviato il controllo delle chiavi del registro di sistema di Watcher create dall'installazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="ed269-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="ed269-134">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="ed269-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="ed269-135">Il controllo delle chiavi del registro di sistema di Watcher create dall'installazione di Watcher node è terminato.</span><span class="sxs-lookup"><span data-stu-id="ed269-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="ed269-136">Il tipo di autenticazione rilevata è Negotiate.</span><span class="sxs-lookup"><span data-stu-id="ed269-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="ed269-137">È stata convalidata l'esistenza della credenziale dell'utente di test SIP: user1@ atl-cs-001.litwareinc.com in Credential Management store.</span><span class="sxs-lookup"><span data-stu-id="ed269-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="ed269-138">È stata convalidata l'esistenza della credenziale dell'utente di test SIP: user2@ atl-cs-001.litwareinc.com in Credential Management store.</span><span class="sxs-lookup"><span data-stu-id="ed269-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="ed269-139">Viene avviato il controllo dei pool mancanti nella configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="ed269-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="ed269-140">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="ed269-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="ed269-141">AVVISO: il pool di atl-cs-001.litwareinc.com ha un registrar</span><span class="sxs-lookup"><span data-stu-id="ed269-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="ed269-142">ruolo installato, ma non sono stati configurati utenti di test.</span><span class="sxs-lookup"><span data-stu-id="ed269-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="ed269-143">Il controllo dei pool mancanti nella configurazione del nodo Watcher è terminato.</span><span class="sxs-lookup"><span data-stu-id="ed269-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="ed269-144">Il controllo delle chiavi del registro di sistema di Watcher create dall'installazione di Watcher node è</span><span class="sxs-lookup"><span data-stu-id="ed269-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="ed269-145">Iniziato.</span><span class="sxs-lookup"><span data-stu-id="ed269-145">started.</span></span> <span data-ttu-id="ed269-146">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="ed269-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="ed269-147">Test-CsWatcherNodeConfiguration: Impossibile trovare la chiave del registro di sistema di integrità</span><span class="sxs-lookup"><span data-stu-id="ed269-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="ed269-148">Software\\Microsoft\\per comunicazioni in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ed269-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="ed269-149">Verificare che Watcher node. msi sia</span><span class="sxs-lookup"><span data-stu-id="ed269-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="ed269-150">installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed269-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ed269-151">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="ed269-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="ed269-152">Ecco alcuni motivi comuni per cui **Test-CsWatcherNodeConfiguration** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="ed269-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="ed269-153">Il nodo Watcher non è installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed269-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="ed269-154">Non sono configurati utenti di test.</span><span class="sxs-lookup"><span data-stu-id="ed269-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed269-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed269-155">See Also</span></span>


[<span data-ttu-id="ed269-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed269-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="ed269-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed269-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="ed269-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed269-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="ed269-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed269-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

