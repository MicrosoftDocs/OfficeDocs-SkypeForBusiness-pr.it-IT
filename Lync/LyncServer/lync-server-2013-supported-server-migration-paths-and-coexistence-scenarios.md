---
title: 'Lync Server 2013: percorsi di migrazione del server supportati e scenari di coesistenza'
description: 'Lync Server 2013: percorsi di migrazione del server supportati e scenari di coesistenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d0a40ac6cc6570cf79b56dc896277c83909b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560232"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="810b0-103">Percorsi di migrazione del server supportati e scenari di coesistenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="810b0-103">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="810b0-104">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="810b0-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="810b0-105">Lync Server 2013 supporta la migrazione da una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="810b0-105">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="810b0-106">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="810b0-106">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="810b0-107">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="810b0-107">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="810b0-108">La migrazione da un ambiente che esegue entrambe le versioni precedenti non è supportata.</span><span class="sxs-lookup"><span data-stu-id="810b0-108">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="810b0-109">La migrazione da versioni precedenti, ad esempio Microsoft Office Communications Server 2007 o Live Communications Server 2005, non è supportata.</span><span class="sxs-lookup"><span data-stu-id="810b0-109">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="810b0-110">Se la distribuzione precedente includeva Group Chat, è necessario eseguirne la migrazione separatamente.</span><span class="sxs-lookup"><span data-stu-id="810b0-110">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="810b0-111">Metodi di migrazione</span><span class="sxs-lookup"><span data-stu-id="810b0-111">Migration Methods</span></span>

<span data-ttu-id="810b0-112">È supportata la migrazione di tutte le topologie di Lync Server e i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="810b0-112">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="810b0-113">È possibile eseguire la migrazione da una topologia a un'altra, incluso da un server Standard Edition a un server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="810b0-113">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="810b0-114">Lync Server 2013 supporta solo il metodo di migrazione seguente:</span><span class="sxs-lookup"><span data-stu-id="810b0-114">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="810b0-115">**Migrazione side-by-side**</span><span class="sxs-lookup"><span data-stu-id="810b0-115">**Side-by-side migration.**</span></span> <span data-ttu-id="810b0-116">Nella migrazione affiancata, Lync Server 2013 viene distribuito insieme a una distribuzione di Microsoft Lync Server 2010 o Office Communications Server 2007 R2 esistente e quindi si trasferiscono le operazioni nei nuovi server e si spostano gli utenti in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="810b0-116">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="810b0-117">Questo metodo richiede l'uso di ulteriori piattaforme server, inclusi hardware e software, durante la migrazione e i nomi dei sistemi e dei pool sono diversi nella nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="810b0-117">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="810b0-118">Se è necessario ripristinare la versione precedente, è possibile spostare di nuovo le operazioni nei server precedenti.</span><span class="sxs-lookup"><span data-stu-id="810b0-118">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="810b0-119">La migrazione tra foreste di servizi di dominio Active Directory non è supportata.</span><span class="sxs-lookup"><span data-stu-id="810b0-119">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="810b0-p104">Il metodo di migrazione consigliato è di tipo incrementale. Per informazioni dettagliate sulla migrazione da una versione precedente, inclusa la tempistica appropriata per la distribuzione dei componenti, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:</span><span class="sxs-lookup"><span data-stu-id="810b0-p104">The recommended migration path is a phased approach. For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="810b0-122">Migrazione da Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="810b0-122">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="810b0-123">Migrazione da Office Communications Server 2007 R2 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="810b0-123">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="810b0-124">Migrazione da Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat al server chat persistente di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="810b0-124">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="810b0-125">Scenari di coesistenza</span><span class="sxs-lookup"><span data-stu-id="810b0-125">Coexistence Scenarios</span></span>

<span data-ttu-id="810b0-126">Lync Server 2013 può coesistere con i componenti di una distribuzione di Lync Server 2010 o di una distribuzione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="810b0-126">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="810b0-127">La distribuzione simultanea di Lync Server 2013 con Lync Server 2010 e Office Communications Server 2007 R2 (distribuzione simultanea di tutte e tre le versioni) non è supportata.</span><span class="sxs-lookup"><span data-stu-id="810b0-127">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="810b0-128">Durante una migrazione in fasi in cui una distribuzione di Lync Server 2010 o Office Communications Server 2007 R2 precedente coesiste temporaneamente con la nuova distribuzione di Lync Server 2013, il supporto per il routing di versioni miste è limitato.</span><span class="sxs-lookup"><span data-stu-id="810b0-128">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="810b0-129">Per informazioni dettagliate, vedere la documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="810b0-129">For details, see the Migration documentation.</span></span>

<span data-ttu-id="810b0-130">È necessario utilizzare computer separati e distinti che eseguono Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 per le istanze di database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="810b0-130">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="810b0-131">Non è possibile utilizzare la stessa istanza di SQL Server per un pool Front End di Lync Server 2013 utilizzato per un pool Front End di Lync Server 2010 o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="810b0-131">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="810b0-132">Se si definisce e si configura Lync Server 2013 in Generatore di topologie per una distribuzione che dispone già di Lync Server 2010 o Office Communications Server 2007 R2 distribuito, generatore di topologie non consentirà di definire un'istanza di Lync Server 2013 già in uso nella topologia.</span><span class="sxs-lookup"><span data-stu-id="810b0-132">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="810b0-133">Il generatore di topologie visualizzerà il seguente messaggio per informare l'utente del problema: "l' \[ FQDN di SQL Server del server \] contiene già un ruolo di hosting dell'istanza di SQL" archivio utenti ".</span><span class="sxs-lookup"><span data-stu-id="810b0-133">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="810b0-134">Se si intende distribuire i ruoli del server nuovi per la distribuzione di Lync Server 2013, è consigliabile prima aggiornare la distribuzione esistente come descritto nella documentazione relativa alla migrazione e la documentazione relativa alla distribuzione e quindi distribuire i nuovi ruoli del server come descritto nella documentazione relativa alla pianificazione e alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="810b0-134">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="810b0-135">Se si esegue la migrazione di una versione precedente di Group Chat, eseguirne la migrazione per ultima, dopo aver completato il processo di migrazione di tutti gli altri componenti da Lync Server 2010 o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="810b0-135">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="810b0-136">Per i requisiti specifici di coesistenza e altri dettagli sulla coesistenza e la migrazione dei componenti di Lync Server 2010 o Office Communications Server 2007 R2 e Lync Server 2013, vedere [Migration from Lync server 2010 to Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) nella documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="810b0-136">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="810b0-137">Per informazioni dettagliate sul supporto di versioni miste per i client, vedere [client supportati dalle distribuzioni precedenti in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="810b0-137">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

