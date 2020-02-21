---
title: 'Lync Server 2013: informazioni sui requisiti del firewall per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f32d84e4cd08c40f95a47af7c988599678c972
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="6a62f-102">Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a62f-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a62f-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6a62f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6a62f-104">Per una distribuzione di Standard Edition, le eccezioni del firewall vengono create automaticamente durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a62f-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="6a62f-105">Per le distribuzioni di Enterprise Edition, tuttavia, è necessario configurare manualmente le eccezioni del firewall sul server back-end di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a62f-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="6a62f-106">Il protocollo TCP/IP consente un solo utilizzo di una determinata porta per un determinato indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="6a62f-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="6a62f-107">Per il server basato su SQL Server, è pertanto possibile assegnare all'istanza di database predefinita la porta TCP predefinita 1433.</span><span class="sxs-lookup"><span data-stu-id="6a62f-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="6a62f-108">Per qualsiasi altra istanza, sarà necessario utilizzare Gestione configurazione SQL Server per assegnare porte univoche e inutilizzate.</span><span class="sxs-lookup"><span data-stu-id="6a62f-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="6a62f-109">In questo argomento vengono trattati i temi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a62f-109">This topic covers:</span></span>

  - <span data-ttu-id="6a62f-110">Requisiti per un'eccezione del firewall nei casi in cui viene utilizzata l'istanza predefinita</span><span class="sxs-lookup"><span data-stu-id="6a62f-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="6a62f-111">Requisiti per un'eccezione del firewall per il servizio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="6a62f-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="6a62f-112">Requisiti per le porte di attesa statiche nei casi in cui vengono utilizzate istanze denominate</span><span class="sxs-lookup"><span data-stu-id="6a62f-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="6a62f-113">Requisiti per un'eccezione del firewall nei casi in cui viene utilizzata l'istanza predefinita</span><span class="sxs-lookup"><span data-stu-id="6a62f-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="6a62f-114">Se si utilizza l'istanza predefinita di SQL Server per qualsiasi database durante la distribuzione di Lync Server 2013, vengono utilizzati i requisiti di regola del firewall riportati di seguito per garantire la comunicazione dal pool Front end all'istanza predefinita di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a62f-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a62f-115">Protocol</span><span class="sxs-lookup"><span data-stu-id="6a62f-115">Protocol</span></span></th>
<th><span data-ttu-id="6a62f-116">Porta</span><span class="sxs-lookup"><span data-stu-id="6a62f-116">Port</span></span></th>
<th><span data-ttu-id="6a62f-117">Direction</span><span class="sxs-lookup"><span data-stu-id="6a62f-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a62f-118">TCP</span><span class="sxs-lookup"><span data-stu-id="6a62f-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="6a62f-119">1433</span><span class="sxs-lookup"><span data-stu-id="6a62f-119">1433</span></span></p></td>
<td><p><span data-ttu-id="6a62f-120">In ingresso-SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a62f-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="6a62f-121">Requisiti per un'eccezione del firewall per il servizio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="6a62f-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="6a62f-122">Il servizio SQL Server Browser individuerà le istanze di database e comunicherà la porta configurata per l'istanza (denominata o predefinita).</span><span class="sxs-lookup"><span data-stu-id="6a62f-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a62f-123">Protocol</span><span class="sxs-lookup"><span data-stu-id="6a62f-123">Protocol</span></span></th>
<th><span data-ttu-id="6a62f-124">Porta</span><span class="sxs-lookup"><span data-stu-id="6a62f-124">Port</span></span></th>
<th><span data-ttu-id="6a62f-125">Direction</span><span class="sxs-lookup"><span data-stu-id="6a62f-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a62f-126">UDP</span><span class="sxs-lookup"><span data-stu-id="6a62f-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="6a62f-127">1434</span><span class="sxs-lookup"><span data-stu-id="6a62f-127">1434</span></span></p></td>
<td><p><span data-ttu-id="6a62f-128">Inbound</span><span class="sxs-lookup"><span data-stu-id="6a62f-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="6a62f-129">Requisiti per le porte di attesa statiche nei casi in cui vengono utilizzate istanze denominate</span><span class="sxs-lookup"><span data-stu-id="6a62f-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="6a62f-130">Quando si utilizzano le istanze denominate nella configurazione di SQL Server per i database che supportano Lync Server 2013, è necessario configurare le porte statiche mediante Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a62f-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="6a62f-131">Dopo l'assegnazione delle porte statiche a ogni istanza denominata, creare eccezioni per ogni porta statica nel firewall.</span><span class="sxs-lookup"><span data-stu-id="6a62f-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a62f-132">Protocol</span><span class="sxs-lookup"><span data-stu-id="6a62f-132">Protocol</span></span></th>
<th><span data-ttu-id="6a62f-133">Porta</span><span class="sxs-lookup"><span data-stu-id="6a62f-133">Port</span></span></th>
<th><span data-ttu-id="6a62f-134">Direction</span><span class="sxs-lookup"><span data-stu-id="6a62f-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a62f-135">TCP</span><span class="sxs-lookup"><span data-stu-id="6a62f-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="6a62f-136">Definita in modo statico</span><span class="sxs-lookup"><span data-stu-id="6a62f-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="6a62f-137">Inbound</span><span class="sxs-lookup"><span data-stu-id="6a62f-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="6a62f-138">Documentazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a62f-138">SQL Server Documentation</span></span>

<span data-ttu-id="6a62f-139">La documentazione di Microsoft SQL Server 2012 fornisce informazioni dettagliate su come configurare l'accesso del firewall per i database.</span><span class="sxs-lookup"><span data-stu-id="6a62f-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="6a62f-140">Per informazioni dettagliate su Microsoft SQL Server 2012, vedere la sezione relativa alla configurazione di Windows Firewall per consentire l' [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031)accesso a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a62f-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

