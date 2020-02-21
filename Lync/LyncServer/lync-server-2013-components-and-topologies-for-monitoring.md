---
title: 'Lync Server 2013: componenti e topologie per il monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 072dbc882940bc0f28217bcf7c41663bf9ed3708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="967e1-102">Componenti e topologie per il monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="967e1-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="967e1-103">_**Ultimo argomento modificato:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="967e1-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="967e1-104">Poiché gli agenti di raccolta dati unificati vengono installati e attivati automaticamente su ogni Front End Server, non è necessario configurare un server per agire come Monitoring Server. ogni Front End Server funziona già come Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="967e1-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="967e1-105">Tuttavia, è necessario installare e configurare un database in modo che funga da archivio dati back-end per i dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="967e1-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="967e1-106">Microsoft Lync Server 2013 può utilizzare uno dei database seguenti come archivio back-end per il monitoraggio:</span><span class="sxs-lookup"><span data-stu-id="967e1-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="967e1-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="967e1-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="967e1-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="967e1-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="967e1-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="967e1-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="967e1-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="967e1-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="967e1-111">Tenere presente che è necessario utilizzare le edizioni a 64 bit di questi database; le versioni a 32 bit di SQL Server non possono essere utilizzate come archivio back-end per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="967e1-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="967e1-112">Analogamente, Lync Server 2013 non supporta le edizioni Express di SQL Server 2008 o SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="967e1-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="967e1-113">Per ulteriori informazioni sui requisiti di database per Lync Server 2013, vedere l'argomento [supporto software per database in Lync server 2013](lync-server-2013-database-software-support.md) nella Guida alla supportabilità di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="967e1-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="967e1-114">Tenere presente che SQL Server deve essere installato e configurato prima di distribuire e configurare il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="967e1-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="967e1-115">Tuttavia, è necessario solo distribuire SQL Server stesso. non è necessario configurare i database di monitoraggio in anticipo.</span><span class="sxs-lookup"><span data-stu-id="967e1-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="967e1-116">Al contrario, i database verranno creati automaticamente quando si pubblica la topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="967e1-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="967e1-117">I dati di monitoraggio possono condividere un'istanza di SQL Server con altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="967e1-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="967e1-118">In genere, il database di registrazione dettagli chiamata (LcsCdr) e il database Quality of Experience (QoEMetrics) condividono la stessa istanza SQL. è inoltre comune che i due database di monitoraggio si trovino nella stessa istanza di SQL del database di archiviazione (LcsLog).</span><span class="sxs-lookup"><span data-stu-id="967e1-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="967e1-119">Informazioni sull'unico requisito reale con le istanze di SQL Server è che una qualsiasi istanza di SQL Server è limitata alla seguente:</span><span class="sxs-lookup"><span data-stu-id="967e1-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="967e1-120">Un'istanza del database back-end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="967e1-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="967e1-121">(Come regola generale, non è consigliabile che il database di monitoraggio sia collocato nella stessa istanza SQL o anche nello stesso computer, come database back-end.</span><span class="sxs-lookup"><span data-stu-id="967e1-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="967e1-122">Anche se tecnicamente possibile, si corre il rischio che il database di monitoraggio utilizzi lo spazio su disco necessario per il database back-end.</span><span class="sxs-lookup"><span data-stu-id="967e1-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="967e1-123">Un'istanza del database di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="967e1-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="967e1-124">Un'istanza del database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="967e1-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="967e1-125">Un'istanza del database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="967e1-125">One instance of the archiving database.</span></span>

<span data-ttu-id="967e1-126">In altre parole, non è possibile avere due istanze del database di LcsCdr nella stessa istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="967e1-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="967e1-127">Se sono necessarie più istanze del database di LcsCdr, sarà necessario configurare più istanze di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="967e1-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="967e1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="967e1-128">See Also</span></span>


[<span data-ttu-id="967e1-129">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="967e1-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

