---
title: 'Lync Server 2013: progettazione della topologia tramite lo strumento pianificazione'
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
ms.openlocfilehash: 590bfae33e12cca2e2305eab9d842f0e2f105838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="a0e2e-102">Progettazione della topologia di Lync Server 2013 tramite lo strumento pianificazione</span><span class="sxs-lookup"><span data-stu-id="a0e2e-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0e2e-103">_**Argomento Ultima modifica:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="a0e2e-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="a0e2e-104">Microsoft Lync Server 2013, strumento di pianificazione è uno strumento basato su una procedura guidata, con un'intervista che pone domande sulla topologia di Lync Server 2013 che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="a0e2e-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="a0e2e-105">Lo strumento di pianificazione usa le informazioni fornite, insieme alle procedure consigliate per la progettazione e la capacità della topologia, per presentare una topologia consigliata in base alle risposte fornite.</span><span class="sxs-lookup"><span data-stu-id="a0e2e-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="a0e2e-106">È possibile scaricare lo strumento di pianificazione dall'area download Microsoft ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span><span class="sxs-lookup"><span data-stu-id="a0e2e-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="a0e2e-107">In definitiva, l'obiettivo dello strumento di pianificazione è quello di semplificare la complessità della progettazione di una topologia completa di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0e2e-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="a0e2e-108">Lo strumento fornisce inoltre riferimenti contestuali alla documentazione relativa alla pianificazione e alla distribuzione all'interno dello strumento, a condizione che sia disponibile una connessione Internet per la connessione al sito Web Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="a0e2e-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="a0e2e-109">Dopo la personalizzazione della topologia con gli indirizzi TCP/IP dell'infrastruttura e i nomi di dominio completi (FQDN), lo strumento di pianificazione rende disponibile una serie di report che includono la denominazione DNS (Domain Name System), le regole del firewall, i certificati e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="a0e2e-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="a0e2e-110">Lo strumento di pianificazione offre anche la possibilità di esportare informazioni in due formati:</span><span class="sxs-lookup"><span data-stu-id="a0e2e-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="a0e2e-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a0e2e-111">Microsoft Excel</span></span>

  - <span data-ttu-id="a0e2e-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="a0e2e-112">Microsoft Visio</span></span>

<span data-ttu-id="a0e2e-113">Gli argomenti seguenti introducono e dettagliano lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a0e2e-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0e2e-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a0e2e-114">In This Section</span></span>

  - [<span data-ttu-id="a0e2e-115">Installazione dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="a0e2e-116">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="a0e2e-117">Spostamento nello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="a0e2e-118">Creare la struttura della topologia iniziale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="a0e2e-119">Esame dei rapporti amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0e2e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0e2e-120">See Also</span></span>


[<span data-ttu-id="a0e2e-121">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="a0e2e-122">Pianificazione di Front End Server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e2e-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

