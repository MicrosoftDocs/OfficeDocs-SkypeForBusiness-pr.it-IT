---
title: 'Lync Server 2013: configurazione di front end server e pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9af600e6c95a33aa743d518c654f3abfe4275d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="4518b-102">Configurazione di front end server e pool Front end per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4518b-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4518b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4518b-104">In questa sezione viene illustrata l'installazione di Lync Server 2013 e la configurazione dei ruoli del server per il server Standard Edition e il pool Front End, inclusi i Front End Server e i ruoli del server collocati con i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="4518b-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="4518b-105">Per installare e configurare i ruoli del server, è possibile eseguire la distribuzione guidata di Lync Server in ogni computer in cui si sta installando un ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="4518b-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="4518b-106">È possibile utilizzare la distribuzione guidata per completare tutti e quattro i passaggi di distribuzione, tra cui l'installazione dell'archivio di configurazione locale, l'installazione dei Front End Server, la configurazione di certificati e l'avvio dei servizi.</span><span class="sxs-lookup"><span data-stu-id="4518b-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4518b-107">Per impostare i ruoli del server, è innanzitutto necessario aver pubblicato correttamente una topologia.</span><span class="sxs-lookup"><span data-stu-id="4518b-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="4518b-108">Per informazioni dettagliate sulla pubblicazione di una topologia, vedere <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">finalizzazione e implementazione della progettazione della topologia in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4518b-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4518b-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="4518b-109">In This Section</span></span>

  - [<span data-ttu-id="4518b-110">Installare l'archivio di configurazione locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="4518b-111">Installare componenti server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="4518b-112">Configurare i certificati per i server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="4518b-113">Avviare servizi nei server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="4518b-114">Testare la distribuzione del pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="4518b-115">Testare il server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4518b-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

