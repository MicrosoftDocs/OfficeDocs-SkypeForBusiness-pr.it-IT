---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-07_

Dopo aver installato i file dell'agente del centro di sistema, è necessario configurare il nodo Watcher. I passaggi da eseguire per configurare un nodo Watcher variano a seconda che il computer del nodo Watcher si trovi all'interno della rete perimetrale o all'esterno della rete perimetrale.

Quando si configura un nodo Watcher, è necessario scegliere anche il tipo di metodo di autenticazione che deve essere impiegato da tale nodo. Lync Server 2013 consente di scegliere uno dei due metodi di autenticazione: Trusted Server o Authentication Credential. Le differenze tra questi due metodi sono descritte nella tabella seguente:


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
<th>Percorsi supportati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server attendibile</p></td>
<td><p>Usa un certificato per rappresentare un server interno e ignorare i problemi di autenticazione.</p>
<p>Questa operazione è utile per gli amministratori che preferiscono gestire un singolo certificato anziché molte password utente in ogni nodo Watcher.</p></td>
<td><p>All'interno dell'organizzazione.</p>
<p>Tieni presente che, con questo metodo, il nodo Watcher deve essere nello stesso dominio dei pool da monitorare. Se il nodo Watcher e i pool monitorati si trovano in domini diversi, usare invece l'autenticazione delle credenziali.</p></td>
</tr>
<tr class="even">
<td><p>Autenticazione delle credenziali</p></td>
<td><p>Archivia i nomi utente e le password in modo sicuro in Gestione credenziali di Windows in ogni nodo Watcher.</p>
<p>Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher situati all'esterno dell'organizzazione. Questi nodi Watcher non possono essere trattati come endpoint attendibili per l'autenticazione.</p></td>
<td><p>All'esterno dell'organizzazione.</p>
<p>All'interno dell'organizzazione.</p></td>
</tr>
</tbody>
</table>


Dovresti anche verificare che il firewall abbia regole in ingresso sia per MonitoringHost. exe che per PowerShell. exe. Se questi processi sono bloccati dal firewall, le transazioni sintetiche non riusciranno con un errore di 504 (timeout del server).

</div>

<span> </span>

</div>

</div>

</div>

