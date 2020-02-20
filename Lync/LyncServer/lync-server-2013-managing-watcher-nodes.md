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
ms.openlocfilehash: c6422754da81aa17d6a746f6539258b3f6ae0d2c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Gestione dei nodi Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Oltre a poter modificare le transazioni sintetiche eseguite su un nodo Watcher, gli amministratori possono utilizzare il cmdlet **Set-CsWatcherNodeConfiguration** per eseguire due attività importanti, ovvero abilitare e disabilitare il nodo Watcher, nonché configurarlo per utilizzare URL interni o esterni durante l'esecuzione dei test.

Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate. In alcuni casi, tuttavia, potrebbe risultare necessario sospendere tali transazioni. Se il nodo Watcher è temporaneamente disconnesso dalla rete, ad esempio, non vi è alcun motivo per eseguire le transazioni sintetiche. Senza connettività di rete, tali transazioni hanno necessariamente esito negativo. Se si desidera disabilitare temporaneamente un nodo Watcher, eseguire un comando simile al seguente da Lync Server Management Shell:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Questo comando consente di disabilitare l'esecuzione delle transazioni sintetiche nel nodo Watcher atl-watcher- 001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, reimpostare la proprietà Enabled su True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> È possibile utilizzare la proprietà Enabled per attivare o disattivare i nodi Watcher. Per eliminare in modo definitivo un nodo Watcher, utilizzare il cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:<BR>Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"<BR>Questo comando consente di rimuovere tutte le impostazioni di configurazione del nodo Watcher dal computer specificato e ciò impedisce l'esecuzione automatica delle transazioni sintetiche. Tuttavia, il comando non disinstalla i file dell'agente centro System o i file di sistema di Lync Server 2013.



</div>

Per impostazione predefinita, i nodi Watcher utilizzano gli URL esterni di un'organizzazione per l'esecuzione dei test. È comunque possibile configurare i nodi Watcher anche per l'utilizzo degli URL interni. Ciò consente agli amministratori di verificare l'accesso agli URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'utilizzo degli URL interni anziché di quelli esterni, impostare la proprietà UseInternalWebUrls su True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Se si reimposta la proprietà sul valore predefinito False ($False), il nodo Watcher utilizzerà gli URL esterni:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

