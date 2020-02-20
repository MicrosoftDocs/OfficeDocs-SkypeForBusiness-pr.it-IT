---
title: 'Lync Server 2013: Guida alle operazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1e6a07b881968f22b9ba36fc217002ea59032d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="41a44-102">Guida alle operazioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a44-103">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="41a44-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="41a44-104">In questo documento vengono descritti i processi operativi, le attività e gli strumenti necessari per la gestione di un ambiente software di comunicazione Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41a44-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="41a44-105">In questo articolo viene spiegato come gestire Lync Server 2013 in base al modello Microsoft Operations Framework (MOF) e viene illustrato come creare un ambiente di gestione operativo efficiente, che prevede l'implementazione di pianificazioni, processi e procedure per mantenere un ambiente di lavoro efficiente.</span><span class="sxs-lookup"><span data-stu-id="41a44-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="41a44-106">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="41a44-106">In This Section</span></span>

<span data-ttu-id="41a44-107">Sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a44-107">The following sections are included:</span></span>

  - [<span data-ttu-id="41a44-108">Procedure consigliate per gli ambienti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="41a44-109">Attività quotidiane in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="41a44-110">Attività settimanali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="41a44-111">Attività mensili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="41a44-112">Attività necessarie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="41a44-113">Elenchi di controllo delle operazioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="41a44-114">Monitoraggio di Lync Server 2013 con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="41a44-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="41a44-115">Dipendenze operative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="41a44-116">Risoluzione dei problemi e indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="41a44-117">Si presuppone che la distribuzione di Microsoft Lync Server 2013 sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="41a44-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="41a44-118">In caso contrario, fare riferimento al contenuto per la pianificazione e la distribuzione di Microsoft Lync Server 2013 prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="41a44-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41a44-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41a44-119">See Also</span></span>


[<span data-ttu-id="41a44-120">Guida introduttiva a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="41a44-121">Planning for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="41a44-122">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a44-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="41a44-123">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="41a44-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

