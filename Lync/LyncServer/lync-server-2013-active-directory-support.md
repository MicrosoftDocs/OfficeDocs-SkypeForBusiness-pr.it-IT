---
title: Lync Server 2013 supporto di Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a7da4487c376ceea4c5c3e41e20a55874b27f06
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="20842-102">Supporto di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20842-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20842-103">_**Ultimo argomento modificato:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="20842-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="20842-104">Di seguito sono riportate le topologie locali dei servizi di dominio Active Directory supportate da Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="20842-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="20842-105">Foresta singola con singolo dominio</span><span class="sxs-lookup"><span data-stu-id="20842-105">Single forest with single domain</span></span>

  - <span data-ttu-id="20842-106">Foresta singola con albero singolo e più domini</span><span class="sxs-lookup"><span data-stu-id="20842-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="20842-107">Foresta singola con più alberi e spazi dei nomi disgiunti</span><span class="sxs-lookup"><span data-stu-id="20842-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="20842-108">Più foreste in una topologia di foreste centralizzate</span><span class="sxs-lookup"><span data-stu-id="20842-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="20842-109">Più foreste in una topologia di foresta di risorse</span><span class="sxs-lookup"><span data-stu-id="20842-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20842-110">Lync Server 2013 non supporta i domini con etichetta singola.</span><span class="sxs-lookup"><span data-stu-id="20842-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="20842-111">Ad esempio, un insieme di strutture con un dominio radice denominato <STRONG>contoso. local</STRONG> è supportato, ma non è supportato un dominio radice con etichetta singola denominato <STRONG>local</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="20842-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="20842-112">Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per domini con nomi DNS con etichetta singola <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="20842-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="20842-113">Lync Server 2013 non supporta la ridenominazione dei domini.</span><span class="sxs-lookup"><span data-stu-id="20842-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="20842-114">Se è necessario rinominare un dominio in cui è distribuito Lync Server, è necessario innanzitutto disinstallare Lync Server, rinominare il dominio e quindi reinstallare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20842-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="20842-115">Per informazioni dettagliate sulle topologie e i requisiti supportati per le distribuzioni locali, vedere [servizi di dominio Active Directory requisiti, supporto e topologie in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="20842-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

