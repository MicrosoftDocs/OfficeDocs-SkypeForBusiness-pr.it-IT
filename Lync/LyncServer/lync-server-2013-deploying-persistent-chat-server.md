---
title: 'Lync Server 2013: Distribuzione del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c8b25-102">Distribuzione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8b25-103">_**Argomento Ultima modifica:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="c8b25-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="c8b25-104">Lync Server 2013, il server di chat persistente fa parte dell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8b25-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="c8b25-105">La distribuzione di un server di chat persistente richiede:</span><span class="sxs-lookup"><span data-stu-id="c8b25-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="c8b25-106">USA generatore di topologia per definire o importare e successivamente pubblicare la topologia e i componenti che vuoi distribuire.</span><span class="sxs-lookup"><span data-stu-id="c8b25-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="c8b25-107">Preparare l'ambiente per la distribuzione dei componenti del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c8b25-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="c8b25-108">Installare e configurare i componenti del server di chat persistenti per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8b25-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="c8b25-109">Il server di chat persistente è disponibile con Lync Server 2013 Enterprise Edition come pool separato (non collocato con i server front-end Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="c8b25-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="c8b25-110">Il server di chat persistente richiede un server back-end di SQL Server nel pool di Enterprise Edition per archiviare il contenuto della chat room e altri metadati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="c8b25-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="c8b25-111">È consigliabile installare **PersistentChatStore** in un server back-end di SQL Server dedicato, anche se è supportata la collocazione di Lync Server 2013 back end server e **PersistentChatStore** nella stessa istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c8b25-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="c8b25-112">Il server di chat persistente può essere distribuito anche con Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c8b25-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="c8b25-113">In questo caso, il server front-end **PersistentChatService** è collocato nel computer Standard Edition e il server back-end di **PersistentChatStore** può essere distribuito nell'istanza di SQL Server Express locale.</span><span class="sxs-lookup"><span data-stu-id="c8b25-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="c8b25-114">Per informazioni dettagliate sulle configurazioni di Colocation supportate, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="c8b25-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8b25-115">Non è supportata la disponibilità elevata per Persistent Chat&nbsp;Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c8b25-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="c8b25-116">Le prestazioni e la scala saranno limitate.</span><span class="sxs-lookup"><span data-stu-id="c8b25-116">Performance and scale will be limited.</span></span> <span data-ttu-id="c8b25-117">Inoltre, sosteniamo solo il nuovo server&nbsp;standard per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c8b25-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="c8b25-118">Non è supportato l'aggiornamento di Lync Server 2010, Group Chat Server a una versione standard&nbsp;di lync server&nbsp;2013 Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="c8b25-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="c8b25-119">Se l'organizzazione richiede il supporto della conformità, è possibile installare il servizio di conformità del server di chat persistente nel server front end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c8b25-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="c8b25-120">Per la conformità è necessario un database separato.</span><span class="sxs-lookup"><span data-stu-id="c8b25-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="c8b25-121">Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato.</span><span class="sxs-lookup"><span data-stu-id="c8b25-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="c8b25-122">Usare generatore di topologie per aggiungere il server di chat persistente alle distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8b25-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="c8b25-123">È possibile scegliere di aggiungere uno o più pool di server di chat persistenti tramite Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="c8b25-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="c8b25-124">Seguire le stesse istruzioni di distribuzione per la distribuzione di più pool di server di chat persistenti come per qualsiasi pool.</span><span class="sxs-lookup"><span data-stu-id="c8b25-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="c8b25-125">Per informazioni dettagliate, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8b25-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c8b25-126">Per informazioni dettagliate sulle topologie disponibili e sui requisiti tecnici e software per l'installazione del server di chat persistente, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione, funzionamento del [server di chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) nella documentazione di pianificazione, documentazione di distribuzione o documentazione operativa e [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa al supporto.</span><span class="sxs-lookup"><span data-stu-id="c8b25-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c8b25-127">Per informazioni dettagliate sull'acquisizione di certificati, sulla creazione del database di SQL Server e sulla creazione di archivi di file, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8b25-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c8b25-128">Un singolo server front-end di server di chat persistente può supportare utenti attivi di 20.000.</span><span class="sxs-lookup"><span data-stu-id="c8b25-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="c8b25-129">È possibile avere un pool di server di chat persistente con un massimo di 4 server front-end attivi che supportano un totale di 80.000 utenti simultanei.</span><span class="sxs-lookup"><span data-stu-id="c8b25-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="c8b25-130">Il server di chat persistente è supportato anche in un server virtuale.</span><span class="sxs-lookup"><span data-stu-id="c8b25-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="c8b25-131">Il server virtuale può supportare fino a 20.000 utenti simultanei se corrisponde alle specifiche del server fisico.</span><span class="sxs-lookup"><span data-stu-id="c8b25-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8b25-132">Il server di chat persistente deve essere installato in un file system NTFS per facilitare l'applicazione della sicurezza del file System.</span><span class="sxs-lookup"><span data-stu-id="c8b25-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="c8b25-133">FAT32 non è un file system supportato per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c8b25-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8b25-134">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c8b25-134">In This Section</span></span>

  - [<span data-ttu-id="c8b25-135">Funzionamento del server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="c8b25-136">Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="c8b25-137">Requisiti tecnici per il server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="c8b25-138">Configurazione dei sistemi e dell'infrastruttura per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="c8b25-139">Aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="c8b25-140">Installazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="c8b25-141">Aggiunta di un amministratore di Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="c8b25-142">Configurazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="c8b25-143">Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8b25-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="c8b25-144">Risoluzione dei problemi di configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="c8b25-145">Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="c8b25-146">Failover e failback del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8b25-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

