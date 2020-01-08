---
title: 'Lync Server 2013: aggiungere o rimuovere un server front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="e230c-102">Aggiungere o rimuovere un server front-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e230c-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e230c-103">_**Argomento Ultima modifica:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="e230c-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="e230c-104">Quando si aggiunge un server front-end a un pool o si rimuove un server front-end da un pool, è necessario riavviare il pool.</span><span class="sxs-lookup"><span data-stu-id="e230c-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="e230c-105">Per impedire l'interruzione del servizio agli utenti, usare la procedura seguente per aggiungere o rimuovere un server front-end.</span><span class="sxs-lookup"><span data-stu-id="e230c-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e230c-106">Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che si trovino nello stesso livello di aggiornamento cumulativo dei server esistenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="e230c-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="e230c-107">Per aggiungere o rimuovere i server front-end</span><span class="sxs-lookup"><span data-stu-id="e230c-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="e230c-108">Se si stanno rimuovendo i server front-end, arrestare prima le nuove connessioni a tali server.</span><span class="sxs-lookup"><span data-stu-id="e230c-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="e230c-109">A questo scopo, puoi usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e230c-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="e230c-110">Quando i server rimossi non hanno sessioni correnti, arrestare i servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e230c-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="e230c-111">Aprire Generatore di topologia e aggiungere o rimuovere i server necessari.</span><span class="sxs-lookup"><span data-stu-id="e230c-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="e230c-112">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="e230c-112">Publish the topology.</span></span>

5.  <span data-ttu-id="e230c-113">Se il pool è stato rimosso da due server front-end a più di due o se è stato superato da più di due server a due, è necessario digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e230c-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="e230c-114">Se il pool include tre o più server, è necessario che almeno tre di questi server vengano eseguiti quando si digita questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e230c-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="e230c-115">Riavviare tutti i server front-end nel pool, uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="e230c-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

