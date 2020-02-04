---
title: Preparare Active Directory per Lync Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bface3b7e2515ed7ec8a8f3d78f21e867a6d6c00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="e61ff-102">Preparare Active Directory per Lync Server</span><span class="sxs-lookup"><span data-stu-id="e61ff-102">Prepare Active Directory for Lync Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e61ff-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e61ff-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e61ff-104">Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Lync Server 2010, è necessario eseguire alcune attività di Active Directory aggiuntive per configurare lo schema, la foresta e il dominio per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e61ff-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="e61ff-105">Le estensioni dello schema aggiungono le classi e gli attributi di Active Directory richiesti da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e61ff-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="e61ff-106">Per altre informazioni, vedere l'argomento [preparazione dei servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="e61ff-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="e61ff-107">**Per preparare Active Directory per Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="e61ff-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="e61ff-108">Nel server front end di Lync Server 2013 eseguire l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e61ff-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="e61ff-109">Selezionare **prepara Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e61ff-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="e61ff-110">![Distribuzione guidata di Lync Server 2013 - Pagina iniziale](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Distribuzione guidata di Lync Server 2013 - Pagina iniziale")</span><span class="sxs-lookup"><span data-stu-id="e61ff-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="e61ff-111">Completare i passaggi da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="e61ff-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="e61ff-112">![Distribuzione guidata - Preparazione di Active Directory](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Distribuzione guidata - Preparazione di Active Directory")</span><span class="sxs-lookup"><span data-stu-id="e61ff-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

