---
title: 'Lync Server 2013: distribuzione del server Chat persistente'
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
ms.openlocfilehash: 4eb457dbaee5e91b7b4f408018242384cd8992c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="4a528-102">Distribuzione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a528-103">_**Ultimo argomento modificato:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="4a528-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="4a528-104">Lync Server 2013, il server Chat persistente fa parte dell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a528-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="4a528-105">La distribuzione del server Chat persistente richiede:</span><span class="sxs-lookup"><span data-stu-id="4a528-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="4a528-106">Utilizzare Generatore di topologie per definire o importare e successivamente pubblicare la topologia e i componenti che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="4a528-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="4a528-107">Preparare l'ambiente per la distribuzione dei componenti del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4a528-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="4a528-108">Installare e configurare i componenti del server Chat persistente per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4a528-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="4a528-109">Il server Chat persistente è disponibile con Lync Server 2013 Enterprise Edition come pool separato (non incluso nei server Enterprise Edition front end).</span><span class="sxs-lookup"><span data-stu-id="4a528-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="4a528-110">Il server di chat persistente richiede un server back-end SQL Server nel pool Enterprise Edition per archiviare il contenuto della chat room e altri metadati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="4a528-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="4a528-111">È consigliabile installare **PersistentChatStore** in un server back-end SQL Server dedicato, anche se è supportato il server back-end di Lync Server 2013 e **PersistentChatStore** nella stessa istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a528-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="4a528-112">Il server Chat persistente può anche essere distribuito con Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4a528-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="4a528-113">In questo caso, il server front end di **PersistentChatService** è collocato nel computer Standard Edition e il server back-end di **PersistentChatStore** può essere distribuito nell'istanza locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="4a528-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="4a528-114">Per informazioni dettagliate sulle configurazioni di Colocation supportate, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="4a528-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a528-115">La disponibilità elevata non è supportata per il server&nbsp;Standard Edition di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="4a528-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="4a528-116">Le prestazioni e la scala saranno limitate.</span><span class="sxs-lookup"><span data-stu-id="4a528-116">Performance and scale will be limited.</span></span> <span data-ttu-id="4a528-117">Inoltre, è supportato solo il nuovo server standard&nbsp;Edition di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="4a528-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="4a528-118">Non è supportato l'aggiornamento di Lync Server 2010, Group Chat Server a un server&nbsp;&nbsp;Standard Edition di Lync Server 2013 Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="4a528-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="4a528-119">Se nell'organizzazione è necessario il supporto della conformità, è possibile installare il servizio di conformità del server Chat persistente sul server front end server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4a528-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="4a528-120">Per motivi di conformità è richiesto un database separato.</span><span class="sxs-lookup"><span data-stu-id="4a528-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="4a528-121">Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato.</span><span class="sxs-lookup"><span data-stu-id="4a528-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="4a528-122">Utilizzare Generatore di topologie per aggiungere il server Chat persistente alle distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a528-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="4a528-123">È possibile scegliere di aggiungere uno o più pool di server Chat persistente utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4a528-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="4a528-124">Seguire le stesse istruzioni per la distribuzione per la distribuzione di più pool di server Chat persistente come si farebbe per qualsiasi pool.</span><span class="sxs-lookup"><span data-stu-id="4a528-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="4a528-125">Per informazioni dettagliate, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4a528-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4a528-126">Per informazioni dettagliate sulle topologie disponibili e sui requisiti tecnici e software per l'installazione del server Chat persistente, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione, [come funziona il server Chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni e all' [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="4a528-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="4a528-127">Per informazioni dettagliate sull'acquisizione dei certificati, la creazione del database di SQL Server e la creazione di archivi di file, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4a528-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4a528-128">Un singolo server front end del server di chat persistente può supportare 20.000 utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="4a528-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="4a528-129">È possibile disporre di un pool di server Chat persistente con fino a 4 server front end attivi che supportano un totale di 80.000 utenti simultanei.</span><span class="sxs-lookup"><span data-stu-id="4a528-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="4a528-130">Il server Chat persistente è supportato anche in un server virtuale.</span><span class="sxs-lookup"><span data-stu-id="4a528-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="4a528-131">Quest'ultimo può supportare fino a 20.000 utenti se ha le stesse specifiche del server fisico.</span><span class="sxs-lookup"><span data-stu-id="4a528-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a528-132">Il server Chat persistente deve essere installato in un file system NTFS per consentire di applicare la sicurezza del file System.</span><span class="sxs-lookup"><span data-stu-id="4a528-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="4a528-133">FAT32 non è un file system supportato per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4a528-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4a528-134">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="4a528-134">In This Section</span></span>

  - [<span data-ttu-id="4a528-135">Funzionamento del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="4a528-136">Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="4a528-137">Requisiti tecnici per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="4a528-138">Configurazione dei sistemi e dell'infrastruttura per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="4a528-139">Aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="4a528-140">Installazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="4a528-141">Aggiunta di un amministratore di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="4a528-142">Configurazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="4a528-143">Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a528-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="4a528-144">Risoluzione dei problemi relativi alla configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="4a528-145">Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="4a528-146">Failover e failover del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a528-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

