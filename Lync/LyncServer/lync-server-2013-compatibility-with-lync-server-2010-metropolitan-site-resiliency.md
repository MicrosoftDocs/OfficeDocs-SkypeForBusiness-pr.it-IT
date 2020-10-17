---
title: Compatibilità di Lync Server 2013 con la resilienza del sito metropolitano di Lync Server 2010
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
ms.openlocfilehash: 04b3cca41b0ea7a7060e6349127dc7c7fb1732ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526053"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="42cd0-102">Resilienza del sito metropolitano di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="42cd0-102">Lync Server 2010 metropolitan site resiliency</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42cd0-103">_**Ultimo argomento modificato:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="42cd0-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="42cd0-104">La soluzione di resilienza del sito metropolitano supportata per Lync Server 2010 non è supportata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42cd0-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="42cd0-105">Tale soluzione prevedeva l'estensione di un singolo pool Front End tra due data center situati nella stessa area metropolitana.</span><span class="sxs-lookup"><span data-stu-id="42cd0-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="42cd0-106">La soluzione di resilienza del sito metropolitano è stata progettata per il ripristino dalla perdita di un datacenter completo.</span><span class="sxs-lookup"><span data-stu-id="42cd0-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="42cd0-107">Quando si estende il pool tra due datacenter, in genere si colloca la metà dei front-end in un centro dati e l'altra metà nel secondo centro dati.</span><span class="sxs-lookup"><span data-stu-id="42cd0-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="42cd0-108">In caso di perdita di un intero centro dati, la metà dei server front end è stata persa.</span><span class="sxs-lookup"><span data-stu-id="42cd0-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="42cd0-109">Ciò può causare problemi con il nuovo modello di sistema distribuito per i pool Front end in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42cd0-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="42cd0-110">Per ulteriori informazioni, vedere [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="42cd0-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

