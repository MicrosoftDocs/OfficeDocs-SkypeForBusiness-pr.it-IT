---
title: 'Lync Server 2013: esecuzione di un failover del pool Front End ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 705593f95c17e4f0fc213eaa284532bca2effb63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536743"
---
# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="91e11-102">Esecuzione di un failover del pool ABC front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e11-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91e11-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="91e11-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="91e11-104">Nei due argomenti di questa sezione viene descritta la procedura per l'esecuzione di un failover del pool ABC in Lync Server 2013, in cui sono associati pool di Lync Server front end A e B e il pool A diventa irrecuperabile.</span><span class="sxs-lookup"><span data-stu-id="91e11-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="91e11-105">Tramite questa procedura, è possibile creare un nuovo pool Front End C con un nuovo nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="91e11-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="91e11-106">Il pool C è costruito dalle informazioni del pool A. La procedura include anche la combinazione di pool B e C.</span><span class="sxs-lookup"><span data-stu-id="91e11-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="91e11-107">Prerequisiti di backup per il failover del pool ABC in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e11-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="91e11-108">Procedura di failover del pool ABC front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e11-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

