---
title: 'Lync Server 2013: Configurazione di Front End Server e pool Front End'
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
ms.openlocfilehash: 8b912eca536960bccc09c5e7a14c9adc245fe69e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="ee2d7-102">Configurazione di Front End Server e pool Front End per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee2d7-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ee2d7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ee2d7-104">Questa sezione illustra l'installazione di Lync Server 2013 e la configurazione dei ruoli del server per il server Standard Edition e il pool Front-End, inclusi i server front-end e tutti i ruoli del server che sono collocati con i server front-end.</span><span class="sxs-lookup"><span data-stu-id="ee2d7-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="ee2d7-105">Per installare e configurare i ruoli del server, eseguire la distribuzione guidata di Lync Server in ogni computer in cui si sta installando un ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="ee2d7-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="ee2d7-106">La distribuzione guidata viene usata per completare tutti e quattro i passaggi di distribuzione, incluso l'installazione dell'archivio di configurazione locale, l'installazione dei server front-end, la configurazione di certificati e l'avvio dei servizi.</span><span class="sxs-lookup"><span data-stu-id="ee2d7-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee2d7-107">Prima di configurare i ruoli del server, è necessario avere pubblicato correttamente una topologia.</span><span class="sxs-lookup"><span data-stu-id="ee2d7-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="ee2d7-108">Per informazioni dettagliate sulla pubblicazione di una topologia, vedere <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">finalizzazione e implementazione della progettazione della topologia in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ee2d7-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee2d7-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ee2d7-109">In This Section</span></span>

  - [<span data-ttu-id="ee2d7-110">Installare l'archivio di configurazione locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="ee2d7-111">Installazione dei componenti server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="ee2d7-112">Configurare i certificati per i server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="ee2d7-113">Avviare servizi nei server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="ee2d7-114">Testare la distribuzione di pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="ee2d7-115">Testare il server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2d7-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

