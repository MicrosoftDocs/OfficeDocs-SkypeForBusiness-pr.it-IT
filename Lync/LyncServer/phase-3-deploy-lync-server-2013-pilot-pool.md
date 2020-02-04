---
title: 'Fase 3: distribuire Lync Server 2013 Pilot pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38a9e19ea3d9456a5e6f5b395286d77ed831f6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="354aa-102">Fase 3: distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="354aa-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="354aa-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="354aa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="354aa-104">Questa sezione illustra i passaggi necessari per distribuire un pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="354aa-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="354aa-105">La distribuzione di Lync Server 2013 richiede l'uso di generatore di topologia per definire la topologia e i componenti che si desidera distribuire, preparare l'ambiente per la distribuzione dei componenti di Lync Server 2013, pubblicare la struttura della topologia al primo front-end Server e quindi installazione e configurazione del software Lync Server 2013 per i componenti per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="354aa-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="354aa-106">Al termine, la distribuzione del pool pilota di Lync Server 2013 sarà coesistente con un pool di Lync Server 2010 esistente.</span><span class="sxs-lookup"><span data-stu-id="354aa-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="354aa-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="354aa-107">In This Section</span></span>

  - [<span data-ttu-id="354aa-108">Preparare Active Directory per Lync Server</span><span class="sxs-lookup"><span data-stu-id="354aa-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="354aa-109">Scaricare la topologia dalla distribuzione esistente</span><span class="sxs-lookup"><span data-stu-id="354aa-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="354aa-110">Distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="354aa-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="354aa-111">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="354aa-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="354aa-112">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="354aa-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="354aa-113">Configurare criteri e certificati di accesso al gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="354aa-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

