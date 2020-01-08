---
title: 'Lync Server 2013: Informazioni sui requisiti del firewall per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="9b33d-102">Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b33d-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b33d-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9b33d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9b33d-104">Per una distribuzione Standard Edition, le eccezioni del firewall vengono create automaticamente durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b33d-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="9b33d-105">Per le distribuzioni di Enterprise Edition, tuttavia, è necessario configurare manualmente le eccezioni del firewall nel server back-end di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b33d-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="9b33d-106">Il protocollo TCP/IP consente di usare una determinata porta per un indirizzo IP specifico.</span><span class="sxs-lookup"><span data-stu-id="9b33d-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="9b33d-107">Questo significa che per il server basato su SQL Server è possibile assegnare l'istanza di database predefinita la porta TCP predefinita 1433.</span><span class="sxs-lookup"><span data-stu-id="9b33d-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="9b33d-108">Per qualsiasi altra istanza sarà necessario usare Gestione configurazione SQL Server per assegnare porte univoche e inutilizzate.</span><span class="sxs-lookup"><span data-stu-id="9b33d-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="9b33d-109">Questo argomento illustra:</span><span class="sxs-lookup"><span data-stu-id="9b33d-109">This topic covers:</span></span>

  - <span data-ttu-id="9b33d-110">Requisiti per un'eccezione del firewall quando si usa l'istanza predefinita</span><span class="sxs-lookup"><span data-stu-id="9b33d-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="9b33d-111">Requisiti per un'eccezione del firewall per il servizio SQL Server browser</span><span class="sxs-lookup"><span data-stu-id="9b33d-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="9b33d-112">Requisiti per le porte di ascolto statiche quando si usano istanze denominate</span><span class="sxs-lookup"><span data-stu-id="9b33d-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="9b33d-113">Requisiti per un'eccezione del firewall quando si usa l'istanza predefinita</span><span class="sxs-lookup"><span data-stu-id="9b33d-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="9b33d-114">Se si usa l'istanza predefinita di SQL Server per qualsiasi database durante la distribuzione di Lync Server 2013, vengono usati i requisiti di regola del firewall seguenti per garantire la comunicazione dal pool Front-end all'istanza predefinita di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b33d-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b33d-115">Protocollo</span><span class="sxs-lookup"><span data-stu-id="9b33d-115">Protocol</span></span></th>
<th><span data-ttu-id="9b33d-116">Porta</span><span class="sxs-lookup"><span data-stu-id="9b33d-116">Port</span></span></th>
<th><span data-ttu-id="9b33d-117">Direzione</span><span class="sxs-lookup"><span data-stu-id="9b33d-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b33d-118">TCP</span><span class="sxs-lookup"><span data-stu-id="9b33d-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="9b33d-119">1433</span><span class="sxs-lookup"><span data-stu-id="9b33d-119">1433</span></span></p></td>
<td><p><span data-ttu-id="9b33d-120">In ingresso a SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b33d-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="9b33d-121">Requisiti per un'eccezione del firewall per il servizio SQL Server browser</span><span class="sxs-lookup"><span data-stu-id="9b33d-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="9b33d-122">Il servizio SQL Server browser individuerà le istanze di database e comunicherà la porta che l'istanza (denominata o predefinita) è configurata per l'uso.</span><span class="sxs-lookup"><span data-stu-id="9b33d-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b33d-123">Protocollo</span><span class="sxs-lookup"><span data-stu-id="9b33d-123">Protocol</span></span></th>
<th><span data-ttu-id="9b33d-124">Porta</span><span class="sxs-lookup"><span data-stu-id="9b33d-124">Port</span></span></th>
<th><span data-ttu-id="9b33d-125">Direzione</span><span class="sxs-lookup"><span data-stu-id="9b33d-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b33d-126">UDP</span><span class="sxs-lookup"><span data-stu-id="9b33d-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="9b33d-127">1434</span><span class="sxs-lookup"><span data-stu-id="9b33d-127">1434</span></span></p></td>
<td><p><span data-ttu-id="9b33d-128">In ingresso</span><span class="sxs-lookup"><span data-stu-id="9b33d-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="9b33d-129">Requisiti per le porte di ascolto statiche quando si usano istanze denominate</span><span class="sxs-lookup"><span data-stu-id="9b33d-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="9b33d-130">Quando si usano istanze denominate nella configurazione di SQL Server per i database che supportano Lync Server 2013, è possibile configurare le porte statiche tramite Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b33d-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="9b33d-131">Dopo aver assegnato le porte statiche a ogni istanza denominata, è possibile creare eccezioni per ogni porta statica nel firewall.</span><span class="sxs-lookup"><span data-stu-id="9b33d-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b33d-132">Protocollo</span><span class="sxs-lookup"><span data-stu-id="9b33d-132">Protocol</span></span></th>
<th><span data-ttu-id="9b33d-133">Porta</span><span class="sxs-lookup"><span data-stu-id="9b33d-133">Port</span></span></th>
<th><span data-ttu-id="9b33d-134">Direzione</span><span class="sxs-lookup"><span data-stu-id="9b33d-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b33d-135">TCP</span><span class="sxs-lookup"><span data-stu-id="9b33d-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="9b33d-136">Staticamente definiti</span><span class="sxs-lookup"><span data-stu-id="9b33d-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="9b33d-137">In ingresso</span><span class="sxs-lookup"><span data-stu-id="9b33d-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="9b33d-138">Documentazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b33d-138">SQL Server Documentation</span></span>

<span data-ttu-id="9b33d-139">La documentazione di Microsoft SQL Server 2012 fornisce indicazioni dettagliate su come configurare l'accesso tramite firewall per i database.</span><span class="sxs-lookup"><span data-stu-id="9b33d-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="9b33d-140">Per informazioni dettagliate su Microsoft SQL Server 2012, vedere la pagina relativa alla configurazione di Windows Firewall per consentire l' [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)accesso a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b33d-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

