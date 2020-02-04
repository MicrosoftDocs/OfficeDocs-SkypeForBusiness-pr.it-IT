---
title: Compatibilità di Lync Server 2013 con la resilienza di siti metropolitani di Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="d6fdd-102">Resilienza di siti metropolitani di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d6fdd-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6fdd-103">_**Argomento Ultima modifica:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="d6fdd-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="d6fdd-104">La soluzione di resilienza del sito metropolitano supportata per Lync Server 2010 non è supportata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6fdd-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="d6fdd-105">Questa soluzione implicava un unico pool Front-end tra due centri dati della stessa area metropolitana.</span><span class="sxs-lookup"><span data-stu-id="d6fdd-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="d6fdd-106">La soluzione di resilienza del sito metropolitano è stata progettata per il ripristino dalla perdita di un data center completo.</span><span class="sxs-lookup"><span data-stu-id="d6fdd-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="d6fdd-107">Quando si estende il pool in due centri dati, in genere si colloca la metà delle estremità anteriori in un centro dati e l'altra metà nel secondo Data Center.</span><span class="sxs-lookup"><span data-stu-id="d6fdd-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="d6fdd-108">Se si perde un intero centro dati, è stato perso metà dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="d6fdd-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="d6fdd-109">Ciò può causare problemi con il nuovo modello di sistema distribuito per i pool Front-end in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6fdd-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="d6fdd-110">Per altre informazioni, vedere [topologie e componenti per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="d6fdd-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

