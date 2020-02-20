---
title: 'Lync Server 2013: aggiungere o rimuovere un front end server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29c1b3800b05ac4318f853ece95b935c6e65c16c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="4dd1f-102">Aggiungere o rimuovere un front end server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dd1f-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dd1f-103">_**Ultimo argomento modificato:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="4dd1f-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="4dd1f-p101">Quando si aggiunge un Front End Server a un pool oppure si rimuove un Front End Server da un pool, è quindi necessario riavviare il pool. Per evitare un'interruzione del servizio per gli utenti, eseguire la procedura seguente quando si aggiunge o si rimuove un Front End Server.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4dd1f-106">Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che siano allo stesso livello di aggiornamento cumulativo dei server esistenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="4dd1f-107">Per aggiungere o rimuovere front end server</span><span class="sxs-lookup"><span data-stu-id="4dd1f-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="4dd1f-p102">Se si desidera rimuovere uno o più Front End Server, innanzitutto interrompere le nuove connessioni a questi server. A tale scopo, è possibile utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4dd1f-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="4dd1f-110">Quando nei server da rimuovere non vi sono sessioni correnti, arrestare i servizi di Lync Server in esecuzione su di essi.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="4dd1f-111">Aprire Generatore di topologie e aggiungere o rimuovere i server necessari.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="4dd1f-112">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-112">Publish the topology.</span></span>

5.  <span data-ttu-id="4dd1f-113">Se il pool è passato dall'avere due front end server a più di due o se è passato da più di due server a due esattamente, è necessario digitare il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4dd1f-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="4dd1f-114">Se il pool dispone di tre o più server, almeno tre di questi server devono essere in esecuzione quando si digita questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="4dd1f-115">Riavviare tutti i Front End Server nel pool, uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="4dd1f-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

