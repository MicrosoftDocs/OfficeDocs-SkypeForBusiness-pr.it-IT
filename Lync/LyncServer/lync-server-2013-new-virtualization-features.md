---
title: 'Lync Server 2013: nuove funzionalità di virtualizzazione'
description: 'Lync Server 2013: nuove funzionalità di virtualizzazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac15b8592d158d84807ff9e665dd6da50b699059
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579222"
---
# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="28185-103">Nuove funzionalità di virtualizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28185-103">New virtualization features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28185-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="28185-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="28185-105">Lync Server 2013 supporta la virtualizzazione sia su Windows Server 2012, Windows Server 2012 R2 che su Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="28185-105">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="28185-106">Il supporto su Windows Server 2012 e Windows Server 2012 R2 include il supporto per le funzionalità di virtualizzazione di I/O (SR-IOV) radice singola.</span><span class="sxs-lookup"><span data-stu-id="28185-106">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="28185-107">Con SR-IOV, la funzione virtuale di una scheda di rete fisica è assegnata direttamente a una macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="28185-107">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="28185-108">Questo aumenta la larghezza di banda della rete e ne riduce la latenza, riducendo al contempo anche il carico che grava sulla CPU dell'host per l'elaborazione del traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="28185-108">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="28185-109">Per beneficiare delle funzionalità SR-IOV, è necessario utilizzare un server host il cui BIOS supporti SR-IOV e schede di rete che supportino SR-IOV.</span><span class="sxs-lookup"><span data-stu-id="28185-109">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

