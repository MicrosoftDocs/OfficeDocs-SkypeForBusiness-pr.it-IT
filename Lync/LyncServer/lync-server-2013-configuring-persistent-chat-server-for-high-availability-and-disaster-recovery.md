---
title: Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86d0c3b9a35a138e3aadac8cc6ffcd4e808b2dca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f944b-102">Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f944b-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f944b-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f944b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f944b-104">I servizi server di chat persistenti di Lync Server 2013 usano una configurazione di *pool allungata* per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f944b-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="f944b-105">Un pool allungato è un pool che include computer distribuiti tra due centri dati fisici, ma che si trovano all'interno di un singolo sito logico di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f944b-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f944b-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f944b-106">In This Section</span></span>

  - [<span data-ttu-id="f944b-107">Risorse necessarie per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f944b-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="f944b-108">Utilizzo di Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f944b-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="f944b-109">Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f944b-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="f944b-110">Mirroring di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f944b-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="f944b-111">Configurazione del log shipping di SQL Server in Lync Server 2013 per il database primario del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="f944b-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="f944b-112">Configurazione del log shipping di SQL Server tra il mirror primario e il database secondario di log shipping in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f944b-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

