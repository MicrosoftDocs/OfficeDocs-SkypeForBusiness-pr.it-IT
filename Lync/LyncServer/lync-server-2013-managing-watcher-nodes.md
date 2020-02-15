---
title: 'Lync Server 2013: gestione dei nodi Watcher'
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
ms.openlocfilehash: 7fd7a9a2aa3152e64a48fb87670280259b082677
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="ddff4-102">Gestione dei nodi Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddff4-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddff4-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ddff4-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ddff4-104">Oltre a poter modificare le transazioni sintetiche eseguite su un nodo Watcher, gli amministratori possono utilizzare il cmdlet **Set-CsWatcherNodeConfiguration** per eseguire due attività importanti, ovvero abilitare e disabilitare il nodo Watcher, nonché configurarlo per utilizzare URL interni o esterni durante l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="ddff4-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="ddff4-105">Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="ddff4-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="ddff4-106">In alcuni casi, tuttavia, potrebbe risultare necessario sospendere tali transazioni.</span><span class="sxs-lookup"><span data-stu-id="ddff4-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="ddff4-107">Se il nodo Watcher è temporaneamente disconnesso dalla rete, ad esempio, non vi è alcun motivo per eseguire le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ddff4-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="ddff4-108">Senza connettività di rete, tali transazioni hanno necessariamente esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ddff4-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="ddff4-109">Se si desidera disabilitare temporaneamente un nodo Watcher, eseguire un comando simile al seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="ddff4-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="ddff4-p102">Questo comando consente di disabilitare l'esecuzione delle transazioni sintetiche nel nodo Watcher atl-watcher- 001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, reimpostare la proprietà Enabled su True ($True):</span><span class="sxs-lookup"><span data-stu-id="ddff4-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="ddff4-112">È possibile utilizzare la proprietà Enabled per attivare o disattivare i nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="ddff4-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="ddff4-113">Per eliminare in modo definitivo un nodo Watcher, utilizzare il cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="ddff4-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="ddff4-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="ddff4-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="ddff4-115">Questo comando consente di rimuovere tutte le impostazioni di configurazione del nodo Watcher dal computer specificato e ciò impedisce l'esecuzione automatica delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ddff4-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="ddff4-116">Tuttavia, il comando non disinstalla i file dell'agente centro System o i file di sistema di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ddff4-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="ddff4-p105">Per impostazione predefinita, i nodi Watcher utilizzano gli URL esterni di un'organizzazione per l'esecuzione dei test. È comunque possibile configurare i nodi Watcher anche per l'utilizzo degli URL interni. Ciò consente agli amministratori di verificare l'accesso agli URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'utilizzo degli URL interni anziché di quelli esterni, impostare la proprietà UseInternalWebUrls su True ($True):</span><span class="sxs-lookup"><span data-stu-id="ddff4-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="ddff4-121">Se si reimposta la proprietà sul valore predefinito False ($False), il nodo Watcher utilizzerà gli URL esterni:</span><span class="sxs-lookup"><span data-stu-id="ddff4-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

