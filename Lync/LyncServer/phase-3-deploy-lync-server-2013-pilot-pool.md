---
title: 'Fase 3: distribuire il pool pilota di Lync Server 2013'
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
ms.openlocfilehash: 8b0a36b86c8d0c90ed0799c7e1acbe76b75c7630
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533723"
---
# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="09cfa-102">Fase 3: distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09cfa-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09cfa-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="09cfa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="09cfa-104">In questa sezione vengono illustrati i passaggi necessari per distribuire un pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09cfa-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="09cfa-105">La distribuzione di Lync Server 2013 richiede l'utilizzo di generatore di topologie per definire la topologia e i componenti che si desidera distribuire, preparare l'ambiente per la distribuzione dei componenti di Lync Server 2013, pubblicare la progettazione della topologia nel primo front end server e quindi installare e configurare il software Lync Server 2013 per i componenti per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09cfa-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="09cfa-106">Al termine, la distribuzione del pool pilota di Lync Server 2013 coesisterà con un pool Lync Server 2010 esistente.</span><span class="sxs-lookup"><span data-stu-id="09cfa-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09cfa-107">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="09cfa-107">In This Section</span></span>

  - [<span data-ttu-id="09cfa-108">Preparare Active Directory per Lync Server</span><span class="sxs-lookup"><span data-stu-id="09cfa-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="09cfa-109">Scaricare la topologia dalla distribuzione esistente</span><span class="sxs-lookup"><span data-stu-id="09cfa-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="09cfa-110">Distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09cfa-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="09cfa-111">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="09cfa-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="09cfa-112">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="09cfa-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="09cfa-113">Configurare criteri e certificati di accesso al gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="09cfa-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

