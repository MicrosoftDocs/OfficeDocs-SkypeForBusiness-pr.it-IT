---
title: Compatibilità di Lync Server 2013 con la resilienza di siti metropolitani di Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3079f05d9860fd659d19df7b71ee633c0cea3fe2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="f8344-102">Resilienza di siti metropolitani di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f8344-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8344-103">_**Argomento Ultima modifica:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="f8344-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="f8344-104">La soluzione di resilienza del sito metropolitano supportata per Lync Server 2010 non è supportata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8344-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="f8344-105">Questa soluzione implicava un unico pool Front-end tra due centri dati della stessa area metropolitana.</span><span class="sxs-lookup"><span data-stu-id="f8344-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="f8344-106">La soluzione di resilienza del sito metropolitano è stata progettata per il ripristino dalla perdita di un data center completo.</span><span class="sxs-lookup"><span data-stu-id="f8344-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="f8344-107">Quando si estende il pool in due centri dati, in genere si colloca la metà delle estremità anteriori in un centro dati e l'altra metà nel secondo Data Center.</span><span class="sxs-lookup"><span data-stu-id="f8344-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="f8344-108">Se si perde un intero centro dati, è stato perso metà dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="f8344-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="f8344-109">Ciò può causare problemi con il nuovo modello di sistema distribuito per i pool Front-end in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8344-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="f8344-110">Per altre informazioni, vedere [topologie e componenti per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="f8344-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

