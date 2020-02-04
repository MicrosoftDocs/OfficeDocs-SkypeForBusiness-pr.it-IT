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
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="46a59-102">Configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46a59-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46a59-103">_**Argomento Ultima modifica:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="46a59-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="46a59-104">Dopo aver installato i file dell'agente del centro di sistema, è necessario configurare il nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="46a59-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="46a59-105">I passaggi da eseguire per configurare un nodo Watcher variano a seconda che il computer del nodo Watcher si trovi all'interno della rete perimetrale o all'esterno della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="46a59-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="46a59-106">Quando si configura un nodo Watcher, è necessario scegliere anche il tipo di metodo di autenticazione che deve essere impiegato da tale nodo.</span><span class="sxs-lookup"><span data-stu-id="46a59-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="46a59-107">Lync Server 2013 consente di scegliere uno dei due metodi di autenticazione: Trusted Server o Authentication Credential.</span><span class="sxs-lookup"><span data-stu-id="46a59-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="46a59-108">Le differenze tra questi due metodi sono descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="46a59-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46a59-109">Configurazione</span><span class="sxs-lookup"><span data-stu-id="46a59-109">Configuration</span></span></th>
<th><span data-ttu-id="46a59-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46a59-110">Description</span></span></th>
<th><span data-ttu-id="46a59-111">Percorsi supportati</span><span class="sxs-lookup"><span data-stu-id="46a59-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46a59-112">Server attendibile</span><span class="sxs-lookup"><span data-stu-id="46a59-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="46a59-113">Usa un certificato per rappresentare un server interno e ignorare i problemi di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="46a59-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="46a59-114">Questa operazione è utile per gli amministratori che preferiscono gestire un singolo certificato anziché molte password utente in ogni nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="46a59-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="46a59-115">All'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46a59-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="46a59-116">Tieni presente che, con questo metodo, il nodo Watcher deve essere nello stesso dominio dei pool da monitorare.</span><span class="sxs-lookup"><span data-stu-id="46a59-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="46a59-117">Se il nodo Watcher e i pool monitorati si trovano in domini diversi, usare invece l'autenticazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="46a59-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46a59-118">Autenticazione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="46a59-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="46a59-119">Archivia i nomi utente e le password in modo sicuro in Gestione credenziali di Windows in ogni nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="46a59-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="46a59-120">Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher situati all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46a59-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="46a59-121">Questi nodi Watcher non possono essere trattati come endpoint attendibili per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="46a59-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="46a59-122">All'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46a59-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="46a59-123">All'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46a59-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46a59-124">Dovresti anche verificare che il firewall abbia regole in ingresso sia per MonitoringHost. exe che per PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="46a59-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="46a59-125">Se questi processi sono bloccati dal firewall, le transazioni sintetiche non riusciranno con un errore di 504 (timeout del server).</span><span class="sxs-lookup"><span data-stu-id="46a59-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

