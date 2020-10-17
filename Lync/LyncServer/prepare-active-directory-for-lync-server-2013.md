---
title: Preparare Active Directory per Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server 2013
ms:assetid: d0978eb6-d842-40e9-b475-73197cc34e08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205265(v=OCS.15)
ms:contentKeyID: 48185413
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65881ada1202fe9bc5e1ccdc403973fa95c2d552
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532793"
---
# <a name="prepare-active-directory-for-lync-server-2013"></a><span data-ttu-id="86040-102">Preparare Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86040-102">Prepare Active Directory for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86040-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="86040-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="86040-104">Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Office Communications Server 2007 R2, è necessario eseguire alcune attività di Active Directory aggiuntive per configurare lo schema, la foresta e il dominio per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86040-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="86040-105">Le estensioni dello schema aggiungono le classi e gli attributi di Active Directory richiesti da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86040-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span> <span data-ttu-id="86040-106">Per ulteriori informazioni, vedere l'argomento relativo alla [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="86040-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="86040-107">**Preparare Active Directory per Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="86040-107">**Prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="86040-108">Nel server front end di Lync Server 2013 eseguire il programma di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86040-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="86040-109">Selezionare **prepara Active Directory**</span><span class="sxs-lookup"><span data-stu-id="86040-109">Select **Prepare Active Directory**</span></span>
    
    <span data-ttu-id="86040-110">![Distribuzione guidata di Lync Server 2013, pagina di benvenuto](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Distribuzione guidata di Lync Server 2013, pagina di benvenuto")</span><span class="sxs-lookup"><span data-stu-id="86040-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="86040-111">Eseguire i passaggi da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="86040-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="86040-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span><span class="sxs-lookup"><span data-stu-id="86040-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

