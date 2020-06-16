---
title: Preparare Active Directory per Lync Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7342f3f1179a0bd27eb94e8eea66eb4e31411d45
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="4fb3e-102">Preparare Active Directory per Lync Server</span><span class="sxs-lookup"><span data-stu-id="4fb3e-102">Prepare Active Directory for Lync Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fb3e-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="4fb3e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="4fb3e-104">Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Lync Server 2010, è necessario eseguire alcune attività di Active Directory aggiuntive per configurare lo schema, la foresta e il dominio per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fb3e-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="4fb3e-105">Le estensioni dello schema aggiungono le classi e gli attributi di Active Directory richiesti da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fb3e-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="4fb3e-106">Per ulteriori informazioni, vedere l'argomento relativo alla [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="4fb3e-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="4fb3e-107">**Per preparare Active Directory per Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="4fb3e-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="4fb3e-108">Nel server front end di Lync Server 2013 eseguire il programma di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fb3e-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="4fb3e-109">Selezionare **Prepara Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4fb3e-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="4fb3e-110">![Distribuzione guidata di Lync Server 2013, pagina di benvenuto](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Distribuzione guidata di Lync Server 2013, pagina di benvenuto")</span><span class="sxs-lookup"><span data-stu-id="4fb3e-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="4fb3e-111">Eseguire i passaggi da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="4fb3e-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="4fb3e-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span><span class="sxs-lookup"><span data-stu-id="4fb3e-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

