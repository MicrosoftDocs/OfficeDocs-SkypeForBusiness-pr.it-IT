---
title: 'Lync Server 2013: gestione dei nodi Watcher'
description: 'Lync Server 2013: gestione dei nodi Watcher.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556612"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="1cda1-103">Gestione dei nodi Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cda1-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cda1-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1cda1-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1cda1-105">Oltre a poter modificare le transazioni sintetiche eseguite su un nodo Watcher, gli amministratori possono utilizzare il cmdlet **Set-CsWatcherNodeConfiguration** per eseguire due attività importanti, ovvero abilitare e disabilitare il nodo Watcher, nonché configurarlo per utilizzare URL interni o esterni durante l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="1cda1-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="1cda1-106">Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="1cda1-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="1cda1-107">In alcuni casi, tuttavia, potrebbe risultare necessario sospendere tali transazioni.</span><span class="sxs-lookup"><span data-stu-id="1cda1-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="1cda1-108">Se il nodo Watcher è temporaneamente disconnesso dalla rete, ad esempio, non vi è alcun motivo per eseguire le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="1cda1-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="1cda1-109">Senza connettività di rete, tali transazioni hanno necessariamente esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1cda1-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="1cda1-110">Se si desidera disabilitare temporaneamente un nodo Watcher, eseguire un comando simile al seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1cda1-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="1cda1-p102">Questo comando consente di disabilitare l'esecuzione delle transazioni sintetiche nel nodo Watcher atl-watcher- 001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, reimpostare la proprietà Enabled su True ($True):</span><span class="sxs-lookup"><span data-stu-id="1cda1-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="1cda1-113">È possibile utilizzare la proprietà Enabled per attivare o disattivare i nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="1cda1-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="1cda1-114">Per eliminare in modo definitivo un nodo Watcher, utilizzare il cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="1cda1-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="1cda1-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="1cda1-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="1cda1-116">Questo comando consente di rimuovere tutte le impostazioni di configurazione del nodo Watcher dal computer specificato e ciò impedisce l'esecuzione automatica delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="1cda1-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="1cda1-117">Tuttavia, il comando non disinstalla i file dell'agente centro System o i file di sistema di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cda1-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="1cda1-p105">Per impostazione predefinita, i nodi Watcher utilizzano gli URL esterni di un'organizzazione per l'esecuzione dei test. È comunque possibile configurare i nodi Watcher anche per l'utilizzo degli URL interni. Ciò consente agli amministratori di verificare l'accesso agli URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'utilizzo degli URL interni anziché di quelli esterni, impostare la proprietà UseInternalWebUrls su True ($True):</span><span class="sxs-lookup"><span data-stu-id="1cda1-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="1cda1-122">Se si reimposta la proprietà sul valore predefinito False ($False), il nodo Watcher utilizzerà gli URL esterni:</span><span class="sxs-lookup"><span data-stu-id="1cda1-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

