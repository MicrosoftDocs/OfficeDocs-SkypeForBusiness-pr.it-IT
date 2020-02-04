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
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Gestione dei nodi Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Oltre a modificare le transazioni sintetiche eseguite in un nodo Watcher, gli amministratori possono usare anche il cmdlet **set-CsWatcherNodeConfiguration** per eseguire due altre attività importanti: abilitare e disabilitare il nodo Watcher e configurare il nodo Watcher per usare URL interni o URL esterni durante l'esecuzione dei test.

Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate. Talvolta, tuttavia, potrebbe essere necessario sospendere tali transazioni. Ad esempio, se il nodo Watcher è temporaneamente disconnesso dalla rete, non c'è alcun motivo per eseguire le transazioni sintetiche. Senza connettività di rete, le transazioni non riescono. Se si vuole disabilitare temporaneamente un nodo Watcher, eseguire un comando simile a quello di Lync Server Management Shell:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Questo comando Disabilita l'esecuzione delle transazioni sintetiche nel nodo Watcher ATL-watcher-001.litwareinc.com. Per riprendere l'esecuzione delle transazioni sintetiche, impostare di nuovo la proprietà Enabled su true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> La proprietà Enabled può essere usata per attivare o disattivare i nodi Watcher. Se si vuole eliminare definitivamente un nodo Watcher, usare il cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :<BR>Remove-CsWatcherNodeConfiguration – Identity "atl-watcher-001.litwareinc.com"<BR>Questo comando rimuove tutte le impostazioni di configurazione del nodo Watcher dal computer specificato, impedendo al computer di eseguire automaticamente transazioni sintetiche. Tuttavia, il comando non disinstalla i file dell'agente del centro di sistema o i file di sistema di Lync Server 2013.



</div>

Per impostazione predefinita, i nodi Watcher usano gli URL esterni di un'organizzazione durante l'esecuzione dei test. Tuttavia, i nodi Watcher possono essere configurati anche per l'uso degli URL interni dell'organizzazione. Ciò consente agli amministratori di verificare l'accesso URL per gli utenti che si trovano all'interno della rete perimetrale. Per configurare un nodo Watcher per l'uso di URL interni anziché di URL esterni, imposta la proprietà UseInternalWebUrls su true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Se si reimposta questa proprietà sul valore predefinito false ($False), il Watcher utilizzerà quindi gli URL esterni:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

