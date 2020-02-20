---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3314116f150b0bb266f08919746fb61c65bc682
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-07_

Dopo aver installato i file dell'agente System Center, è necessario configurare il nodo Watcher stesso. I passaggi da eseguire per configurare un nodo Watcher variano a seconda che il computer del nodo Watcher si trovi all'interno della rete perimetrale o all'esterno della rete perimetrale.

Quando si configura un nodo Watcher, è necessario scegliere anche il tipo di metodo di autenticazione da utilizzare per tale nodo. Lync Server 2013 consente di scegliere uno dei due metodi di autenticazione: Trusted Server o Authentication Credential. Nella tabella seguente vengono descritte le differenze tra i due metodi seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configurazione</th>
<th>Descrizione</th>
<th>Posizioni supportate</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server attendibile</p></td>
<td><p>Utilizza un certificato per rappresentare un server interno e ignorare i problemi di autenticazione.</p>
<p>Questa operazione è utile per gli amministratori che preferiscono gestire un singolo certificato anziché molte password utente in ogni nodo Watcher.</p></td>
<td><p>All'interno dell'organizzazione.</p>
<p>Si noti che, con questo metodo, il nodo Watcher deve trovarsi nello stesso dominio dei pool monitorati. Se il nodo Watcher e i pool monitorati sono in domini diversi, utilizzare invece l'autenticazione delle credenziali.</p></td>
</tr>
<tr class="even">
<td><p>Autenticazione delle credenziali</p></td>
<td><p>Archivia i nomi utente e le password in modo sicuro in Gestione credenziali di Windows su ogni nodo Watcher.</p>
<p>Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher situati all'esterno dell'organizzazione. Questi nodi Watcher non possono essere considerati come endpoint attendibili per l'autenticazione.</p></td>
<td><p>All'esterno dell'organizzazione.</p>
<p>All'interno dell'organizzazione.</p></td>
</tr>
</tbody>
</table>


È inoltre necessario verificare che il firewall disponga di regole in ingresso per MonitoringHost. exe e PowerShell. exe. Se questi processi vengono bloccati dal firewall, le transazioni sintetiche avranno esito negativo con un errore di 504 (timeout del server).

</div>

<span> </span>

</div>

</div>

</div>

