---
title: 'Lync Server 2013: verifica della configurazione del nodo Watcher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a52b251f238b8d79602e5fe1bf2803902cbae23f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503813"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="a2177-102">Test della configurazione del nodo Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2177-102">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2177-103">_**Ultimo argomento modificato:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a2177-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2177-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="a2177-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a2177-105">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="a2177-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2177-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="a2177-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a2177-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2177-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2177-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="a2177-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a2177-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a2177-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a2177-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="a2177-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="a2177-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2177-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a2177-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2177-112">Description</span></span>

<span data-ttu-id="a2177-113">Se si utilizza Microsoft System Center Operations Manager per monitorare Lync Server 2013, è possibile impostare "nodi Watcher": computer che periodicamente e automaticamente eseguono transazioni sintetiche per verificare che Lync Server funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="a2177-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="a2177-114">I nodi Watcher sono assegnati ai pool e vengono gestiti utilizzando i cmdlet di **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a2177-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="a2177-115">Si noti che non è necessario installare nodi Watcher se si utilizza System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a2177-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="a2177-116">È comunque possibile monitorare il sistema senza utilizzare i nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="a2177-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="a2177-117">L'unica differenza è che tutte le transazioni sintetiche che si desidera eseguire devono essere richiamate manualmente anziché richiamate automaticamente da Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a2177-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="a2177-118">Il cmdlet **Test-CsWatcherNodeConfiguration** consente di verificare che un nodo Watcher sia stato configurato correttamente e che sia assegnato a un pool Lync Server 2013 valido.</span><span class="sxs-lookup"><span data-stu-id="a2177-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="a2177-119">Si noti che il cmdlet **Test-CsWatcherNodeConfiguration** deve essere eseguito nel nodo Watcher stesso.</span><span class="sxs-lookup"><span data-stu-id="a2177-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="a2177-120">Non è possibile eseguire il cmdlet nei computer remoti.</span><span class="sxs-lookup"><span data-stu-id="a2177-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a2177-121">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="a2177-121">Running the test</span></span>

<span data-ttu-id="a2177-122">Con il comando seguente vengono verificate le impostazioni di configurazione per ogni nodo Watcher utilizzato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2177-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a2177-123">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="a2177-123">Determining success or failure</span></span>

<span data-ttu-id="a2177-124">Nell'output di esempio riportato di seguito viene illustrato un sistema con quattro server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2177-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="a2177-125">Convalida del pool di destinazione atl-cs-001.litwareinc.com rispetto alla topologia.</span><span class="sxs-lookup"><span data-stu-id="a2177-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="a2177-126">Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com esiste nella topologia.</span><span class="sxs-lookup"><span data-stu-id="a2177-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="a2177-127">Success: pool di destinazione in cui è installato il ruolo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a2177-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="a2177-128">Operazione riuscita: il pool di destinazione atl-cs-001.litwareinc.com è supportato.</span><span class="sxs-lookup"><span data-stu-id="a2177-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="a2177-129">Esito positivo: numero di porta per il pool di destinazione 5061 atl-cs-001.litwareinc.com è corretto.</span><span class="sxs-lookup"><span data-stu-id="a2177-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="a2177-130">È stato avviato il controllo dei pool mancanti nella configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="a2177-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="a2177-131">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="a2177-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a2177-132">La verifica dei pool mancanti nella configurazione del nodo Watcher è terminata.</span><span class="sxs-lookup"><span data-stu-id="a2177-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="a2177-133">Viene avviata la verifica delle chiavi del registro di sistema dei nodi Watcher create dall'installazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="a2177-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="a2177-134">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="a2177-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a2177-135">È stato completato il controllo delle chiavi del registro di sistema del nodo Watcher create dall'installazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="a2177-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="a2177-136">Il tipo di autenticazione rilevato è Negotiate.</span><span class="sxs-lookup"><span data-stu-id="a2177-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="a2177-137">Esito positivo della convalida della credenziale SIP dell'utente di test: user1@ atl-cs-001.litwareinc.com nell'archivio di gestione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="a2177-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="a2177-138">Esito positivo della convalida della credenziale SIP dell'utente di test: user2@ atl-cs-001.litwareinc.com nell'archivio di gestione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="a2177-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="a2177-139">È stato avviato il controllo dei pool mancanti nella configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="a2177-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="a2177-140">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="a2177-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a2177-141">AVVISO: pool atl-cs-001.litwareinc.com has registrar</span><span class="sxs-lookup"><span data-stu-id="a2177-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="a2177-142">ruolo installato, ma non sono stati configurati gli utenti di test.</span><span class="sxs-lookup"><span data-stu-id="a2177-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="a2177-143">La verifica dei pool mancanti nella configurazione del nodo Watcher è terminata.</span><span class="sxs-lookup"><span data-stu-id="a2177-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="a2177-144">Verifica delle chiavi del registro di sistema dei nodi Watcher create dall'installazione del nodo Watcher, è</span><span class="sxs-lookup"><span data-stu-id="a2177-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="a2177-145">iniziare.</span><span class="sxs-lookup"><span data-stu-id="a2177-145">started.</span></span> <span data-ttu-id="a2177-146">Se viene rilevato un errore, verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="a2177-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a2177-147">Test-CsWatcherNodeConfiguration: Impossibile trovare la chiave del registro di sistema di integrità in</span><span class="sxs-lookup"><span data-stu-id="a2177-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="a2177-148">\\Comunicazione software Microsoft \\ Real-Time.</span><span class="sxs-lookup"><span data-stu-id="a2177-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="a2177-149">Verificare che il nodo Watcher. msi sia</span><span class="sxs-lookup"><span data-stu-id="a2177-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="a2177-150">installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a2177-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a2177-151">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="a2177-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="a2177-152">Di seguito sono riportate alcune ragioni comuni per cui **Test-CsWatcherNodeConfiguration** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="a2177-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="a2177-153">Il nodo Watcher non è installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a2177-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="a2177-154">Non sono configurati utenti di test.</span><span class="sxs-lookup"><span data-stu-id="a2177-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2177-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2177-155">See Also</span></span>


[<span data-ttu-id="a2177-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2177-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="a2177-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2177-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="a2177-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2177-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="a2177-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2177-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

