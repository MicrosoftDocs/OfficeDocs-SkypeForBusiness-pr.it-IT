---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche"
description: "Lync Server 2013: configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche."
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
ms.openlocfilehash: bd5fdb3d1a1499a6ef79e962a41d9eb3ee174c33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567882"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="0c6c2-103">Configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c6c2-103">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c6c2-104">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0c6c2-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="0c6c2-105">Dopo aver installato i file dell'agente System Center, è necessario configurare il nodo Watcher stesso.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-105">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="0c6c2-106">I passaggi da eseguire per configurare un nodo Watcher variano a seconda che il computer del nodo Watcher si trovi all'interno della rete perimetrale o all'esterno della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-106">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="0c6c2-107">Quando si configura un nodo Watcher, è necessario scegliere anche il tipo di metodo di autenticazione da utilizzare per tale nodo.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-107">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="0c6c2-108">Lync Server 2013 consente di scegliere uno dei due metodi di autenticazione: Trusted Server o Authentication Credential.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-108">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="0c6c2-109">Nella tabella seguente vengono descritte le differenze tra i due metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c6c2-109">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c6c2-110">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0c6c2-110">Configuration</span></span></th>
<th><span data-ttu-id="0c6c2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c6c2-111">Description</span></span></th>
<th><span data-ttu-id="0c6c2-112">Posizioni supportate</span><span class="sxs-lookup"><span data-stu-id="0c6c2-112">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c6c2-113">Server attendibile</span><span class="sxs-lookup"><span data-stu-id="0c6c2-113">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="0c6c2-114">Utilizza un certificato per rappresentare un server interno e ignorare i problemi di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-114">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="0c6c2-115">Questa operazione è utile per gli amministratori che preferiscono gestire un singolo certificato anziché molte password utente in ogni nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-115">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="0c6c2-116">All'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-116">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="0c6c2-117">Si noti che, con questo metodo, il nodo Watcher deve trovarsi nello stesso dominio dei pool monitorati.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-117">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="0c6c2-118">Se il nodo Watcher e i pool monitorati sono in domini diversi, utilizzare invece l'autenticazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-118">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c6c2-119">Autenticazione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="0c6c2-119">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="0c6c2-120">Archivia i nomi utente e le password in modo sicuro in Gestione credenziali di Windows su ogni nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-120">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="0c6c2-121">Questa modalità richiede una maggiore gestione delle password, ma è l'unica opzione per i nodi Watcher situati all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-121">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="0c6c2-122">Questi nodi Watcher non possono essere considerati come endpoint attendibili per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-122">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="0c6c2-123">All'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-123">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="0c6c2-124">All'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-124">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0c6c2-125">È inoltre necessario verificare che il firewall disponga di regole in ingresso per MonitoringHost.exe e PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="0c6c2-125">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="0c6c2-126">Se questi processi vengono bloccati dal firewall, le transazioni sintetiche avranno esito negativo con un errore di 504 (timeout del server).</span><span class="sxs-lookup"><span data-stu-id="0c6c2-126">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

