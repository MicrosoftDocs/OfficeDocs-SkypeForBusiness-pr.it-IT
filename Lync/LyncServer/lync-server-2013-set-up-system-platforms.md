---
title: 'Lync Server 2013: configurare le piattaforme di sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59aafcda7cbe94401cdbd77479eecf38e3e9e351
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="d1895-102">Configurare le piattaforme di sistema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1895-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d1895-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d1895-104">Prima di avviare la distribuzione del server Chat persistente, è necessario installare il sistema operativo necessario sull'hardware che soddisfi i requisiti di sistema nei server:</span><span class="sxs-lookup"><span data-stu-id="d1895-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="d1895-105">Per informazioni dettagliate sull'hardware supportato per i server che eseguono Lync Server 2013, i server di database e i file server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d1895-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="d1895-106">Per informazioni dettagliate sui sistemi operativi e il software di database supportati, vedere [Server software and Infrastructure Support in Lync server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d1895-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="d1895-107">Per informazioni dettagliate sui requisiti di Windows Update, vedere [additional server support and requirements in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d1895-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d1895-108">Il server front-end di Persistent Chat Server, **PersistentChatService**, può essere distribuito su uno o più computer autonomi in un pool Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d1895-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="d1895-109">Non possono essere collocati nei server front end di Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d1895-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="d1895-110">Il server Chat persistente può essere distribuito dal programma di avvio automatico, proprio come gli altri ruoli di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1895-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="d1895-111">I **servizi Web di chat persistente per il caricamento o il download di file**e i **servizi Web di chat persistente per la gestione delle chat room** sono componenti Web distribuiti nei server front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1895-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="d1895-112">Un singolo server front end del server di chat persistente può supportare 20.000 utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="d1895-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="d1895-113">È possibile disporre di un pool di server Chat persistente con un massimo di 4 front-end attivi che supportano un totale di 80.000 utenti simultanei.</span><span class="sxs-lookup"><span data-stu-id="d1895-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="d1895-114">Il server back-end della chat persistente, **PersistentChatStore**, archivia le chat room e le categorie.</span><span class="sxs-lookup"><span data-stu-id="d1895-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="d1895-115">È consigliabile installare **PersistentChatStore** in un server back-end SQL Server dedicato nel pool Enterprise Edition. anche se è supportata la collocazione del server back-end Lync Server 2013 e **PersistentChatStore** nella stessa istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1895-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="d1895-116">Se nell'organizzazione è necessario il supporto della conformità, è possibile installarlo tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d1895-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="d1895-117">Il servizio di conformità del server Chat persistente è installato nello stesso computer del server front end server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1895-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="d1895-118">Per motivi di conformità è richiesto un database separato.</span><span class="sxs-lookup"><span data-stu-id="d1895-118">A separate database is required for compliance.</span></span> <span data-ttu-id="d1895-119">Per informazioni dettagliate sui requisiti di conformità per il server Chat persistente, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d1895-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="d1895-120">Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato.</span><span class="sxs-lookup"><span data-stu-id="d1895-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="d1895-121">Generatore di topologie supporta più pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1895-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="d1895-122">Seguire le stesse istruzioni per la distribuzione per la distribuzione di più pool di server Chat persistente come si farebbe per qualsiasi pool dalla [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d1895-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="d1895-123">È inoltre possibile distribuire il server Chat persistente con Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d1895-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="d1895-124">In questo caso, il server front end di **PersistentChatService** è collocato nel server Standard Edition ed è possibile distribuire il server back-end di **PersistentChatStore** nell'istanza locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="d1895-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1895-125">Non è supportato il server&nbsp;di chat persistente Standard Edition per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="d1895-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="d1895-126">Le prestazioni e la scala saranno limitate.</span><span class="sxs-lookup"><span data-stu-id="d1895-126">Performance and scale will be limited.</span></span> <span data-ttu-id="d1895-127">Inoltre, vengono supportate solo le nuove distribuzioni&nbsp;del server Standard Edition di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="d1895-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="d1895-128">Non è supportato un aggiornamento di Lync Server 2010, Group Chat Server a un server&nbsp;&nbsp;Standard Edition di Lync Server 2013 Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="d1895-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1895-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1895-129">See Also</span></span>


[<span data-ttu-id="d1895-130">Requisiti e supporto per i server aggiuntivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="d1895-131">Hardware supportato per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="d1895-132">Supporto dell'infrastruttura e del software server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="d1895-133">Pianificazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="d1895-134">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

