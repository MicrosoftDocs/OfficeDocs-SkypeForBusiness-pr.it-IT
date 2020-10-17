---
title: 'Lync Server 2013: configurazione di una route di failover'
description: 'Lync Server 2013: configurazione di una route di failover.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560492"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="2d892-103">Configurazione di una route di failover in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d892-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d892-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2d892-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2d892-p101">Nell'esempio seguente viene illustrato il modo in cui un amministratore può definire una route di failover da utilizzare se Dallas-GW1 viene disconnesso per la manutenzione o è altrimenti non disponibile. Nelle tabelle seguenti viene illustrata la modifica di configurazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="2d892-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="2d892-p102">Tabella 1. Criteri utente</span><span class="sxs-lookup"><span data-stu-id="2d892-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d892-109">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="2d892-109">User policy</span></span></th>
<th><span data-ttu-id="2d892-110">Utilizzo telefono</span><span class="sxs-lookup"><span data-stu-id="2d892-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d892-111">Criteri di chiamata predefiniti</span><span class="sxs-lookup"><span data-stu-id="2d892-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="2d892-112">Locale</span><span class="sxs-lookup"><span data-stu-id="2d892-112">Local</span></span></p>
<p><span data-ttu-id="2d892-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="2d892-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d892-114">Criteri locali Redmond</span><span class="sxs-lookup"><span data-stu-id="2d892-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="2d892-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="2d892-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d892-116">Criteri di chiamata Dallas</span><span class="sxs-lookup"><span data-stu-id="2d892-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="2d892-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="2d892-117">DallasUsers</span></span></p>
<p><span data-ttu-id="2d892-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="2d892-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="2d892-p103">Tabella 2. Route</span><span class="sxs-lookup"><span data-stu-id="2d892-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d892-121">Nome route</span><span class="sxs-lookup"><span data-stu-id="2d892-121">Route name</span></span></th>
<th><span data-ttu-id="2d892-122">Formato numero</span><span class="sxs-lookup"><span data-stu-id="2d892-122">Number pattern</span></span></th>
<th><span data-ttu-id="2d892-123">Utilizzo telefono</span><span class="sxs-lookup"><span data-stu-id="2d892-123">Phone usage</span></span></th>
<th><span data-ttu-id="2d892-124">Trunk</span><span class="sxs-lookup"><span data-stu-id="2d892-124">Trunk</span></span></th>
<th><span data-ttu-id="2d892-125">Gateway</span><span class="sxs-lookup"><span data-stu-id="2d892-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d892-126">Route locale Redmond</span><span class="sxs-lookup"><span data-stu-id="2d892-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="2d892-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="2d892-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="2d892-128">Locale</span><span class="sxs-lookup"><span data-stu-id="2d892-128">Local</span></span></p>
<p><span data-ttu-id="2d892-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="2d892-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="2d892-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="2d892-130">Trunk1</span></span></p>
<p><span data-ttu-id="2d892-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="2d892-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="2d892-132">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="2d892-132">Red-GW1</span></span></p>
<p><span data-ttu-id="2d892-133">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="2d892-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d892-134">Route locale Dallas</span><span class="sxs-lookup"><span data-stu-id="2d892-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="2d892-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="2d892-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="2d892-136">Locale</span><span class="sxs-lookup"><span data-stu-id="2d892-136">Local</span></span></p></td>
<td><p><span data-ttu-id="2d892-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="2d892-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="2d892-138">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="2d892-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d892-139">Universal Route</span><span class="sxs-lookup"><span data-stu-id="2d892-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="2d892-140">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="2d892-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="2d892-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="2d892-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="2d892-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="2d892-142">Trunk1</span></span></p>
<p><span data-ttu-id="2d892-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="2d892-143">Trunk2</span></span></p>
<p><span data-ttu-id="2d892-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="2d892-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="2d892-145">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="2d892-145">Red-GW1</span></span></p>
<p><span data-ttu-id="2d892-146">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="2d892-146">Red-GW2</span></span></p>
<p><span data-ttu-id="2d892-147">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="2d892-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d892-148">Route utenti Dallas</span><span class="sxs-lookup"><span data-stu-id="2d892-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="2d892-149">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="2d892-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="2d892-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="2d892-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="2d892-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="2d892-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="2d892-152">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="2d892-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2d892-p104">Nella tabella 1, è stato aggiunto l'utilizzo telefono GlobalPSTNHopoff dopo l'utilizzo telefono DallasUsers nei criteri di chiamata Dallas. In questo modo, le chiamate con i criteri di chiamata Dallas possono utilizzare le route configurate per l'utilizzo telefono GlobalPSTNHopoff se non è disponibile una route per l'utilizzo telefono DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="2d892-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

