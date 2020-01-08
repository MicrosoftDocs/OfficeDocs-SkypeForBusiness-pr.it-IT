---
title: 'Lync Server 2013: Guida alle operazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1259a66c4f7471538939a51610018e19231104c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="2ae00-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae00-103">_**Argomento Ultima modifica:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="2ae00-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="2ae00-104">Questo documento descrive i processi operativi, le attività e gli strumenti necessari per gestire un ambiente software di comunicazione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ae00-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="2ae00-105">Spiega come gestire Lync Server 2013 in base al modello MOF (Microsoft Operations Framework) e consente di progettare un ambiente di gestione operativa efficiente, che include l'implementazione di pianificazioni, processi e procedure per mantenere un ambiente di lavoro efficiente.</span><span class="sxs-lookup"><span data-stu-id="2ae00-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2ae00-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2ae00-106">In This Section</span></span>

<span data-ttu-id="2ae00-107">Sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ae00-107">The following sections are included:</span></span>

  - [<span data-ttu-id="2ae00-108">Procedure consigliate per gli ambienti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="2ae00-109">Attività quotidiane in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="2ae00-110">Attività settimanali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="2ae00-111">Attività mensili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="2ae00-112">Attività necessarie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="2ae00-113">Elenchi di controllo delle operazioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="2ae00-114">Monitoraggio di Lync Server 2013 con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="2ae00-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="2ae00-115">Dipendenze operative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="2ae00-116">Risoluzione dei problemi e indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="2ae00-117">Si presuppone che la distribuzione di Microsoft Lync Server 2013 sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="2ae00-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="2ae00-118">In caso contrario, vedere il contenuto della pianificazione e della distribuzione per Microsoft Lync Server 2013 prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2ae00-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ae00-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ae00-119">See Also</span></span>


[<span data-ttu-id="2ae00-120">Introduzione a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="2ae00-121">Pianificazione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="2ae00-122">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae00-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="2ae00-123">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="2ae00-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

