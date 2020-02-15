---
title: 'Lync Server 2013: progettazione della topologia mediante lo strumento di pianificazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bca2871acdaf67e318e7e402d78f34748de4b722
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="65a5d-102">Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="65a5d-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65a5d-103">_**Ultimo argomento modificato:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="65a5d-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="65a5d-104">Microsoft Lync Server 2013, Planning Tool è uno strumento basato su procedure guidate, che consente di fare domande sulla topologia di Lync Server 2013 che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="65a5d-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="65a5d-105">Lo strumento di pianificazione utilizza le informazioni fornite, unitamente alle procedure consigliate per la progettazione e la capacità della topologia, per presentare una topologia consigliata in base alle risposte fornite.</span><span class="sxs-lookup"><span data-stu-id="65a5d-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="65a5d-106">È possibile scaricare lo strumento di pianificazione dall'area download Microsoft ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span><span class="sxs-lookup"><span data-stu-id="65a5d-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="65a5d-107">Infine, l'obiettivo dello strumento di pianificazione è facilitare la complessità potenziale della progettazione di una topologia Lync Server 2013 completa.</span><span class="sxs-lookup"><span data-stu-id="65a5d-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="65a5d-108">All'interno di questo strumento vengono forniti inoltre riferimenti contestuali alla documentazione relativa alla pianificazione e alla distribuzione, purché sia disponibile una connessione Internet per l'accesso ai siti Web di Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="65a5d-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="65a5d-109">Dopo aver personalizzato la topologia con gli indirizzi TCP/IP e i nomi di dominio completi (FQDN) dell'infrastruttura, lo strumento di pianificazione rende disponibili una serie di report che comprendono la denominazione DNS (Domain Name System), le regole del firewall, i certificati e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="65a5d-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="65a5d-110">Lo strumento di pianificazione consente inoltre di esportare le informazioni in due formati:</span><span class="sxs-lookup"><span data-stu-id="65a5d-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="65a5d-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="65a5d-111">Microsoft Excel</span></span>

  - <span data-ttu-id="65a5d-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="65a5d-112">Microsoft Visio</span></span>

<span data-ttu-id="65a5d-113">Negli argomenti seguenti vengono introdotti e dettagliati lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="65a5d-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="65a5d-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="65a5d-114">In This Section</span></span>

  - [<span data-ttu-id="65a5d-115">Installazione dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="65a5d-116">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="65a5d-117">Esplorazione dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="65a5d-118">Creare la progettazione della topologia iniziale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="65a5d-119">Revisione dei rapporti dell'amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65a5d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65a5d-120">See Also</span></span>


[<span data-ttu-id="65a5d-121">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="65a5d-122">Pianificazione di front end server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a5d-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

