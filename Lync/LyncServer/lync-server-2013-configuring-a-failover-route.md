---
title: 'Lync Server 2013: configurazione di una route di failover'
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
ms.openlocfilehash: e0a3a0d3b2eb2d505ff345af66ae8ccbcc551ee8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520063"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="21a46-102">Configurazione di una route di failover in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21a46-102">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21a46-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="21a46-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="21a46-p101">Nell'esempio seguente viene illustrato il modo in cui un amministratore può definire una route di failover da utilizzare se Dallas-GW1 viene disconnesso per la manutenzione o è altrimenti non disponibile. Nelle tabelle seguenti viene illustrata la modifica di configurazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="21a46-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="21a46-p102">Tabella 1. Criteri utente</span><span class="sxs-lookup"><span data-stu-id="21a46-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21a46-108">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="21a46-108">User policy</span></span></th>
<th><span data-ttu-id="21a46-109">Utilizzo telefono</span><span class="sxs-lookup"><span data-stu-id="21a46-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21a46-110">Criteri di chiamata predefiniti</span><span class="sxs-lookup"><span data-stu-id="21a46-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="21a46-111">Locale</span><span class="sxs-lookup"><span data-stu-id="21a46-111">Local</span></span></p>
<p><span data-ttu-id="21a46-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="21a46-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21a46-113">Criteri locali Redmond</span><span class="sxs-lookup"><span data-stu-id="21a46-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="21a46-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="21a46-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21a46-115">Criteri di chiamata Dallas</span><span class="sxs-lookup"><span data-stu-id="21a46-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="21a46-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="21a46-116">DallasUsers</span></span></p>
<p><span data-ttu-id="21a46-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="21a46-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="21a46-p103">Tabella 2. Route</span><span class="sxs-lookup"><span data-stu-id="21a46-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="21a46-120">Nome route</span><span class="sxs-lookup"><span data-stu-id="21a46-120">Route name</span></span></th>
<th><span data-ttu-id="21a46-121">Formato numero</span><span class="sxs-lookup"><span data-stu-id="21a46-121">Number pattern</span></span></th>
<th><span data-ttu-id="21a46-122">Utilizzo telefono</span><span class="sxs-lookup"><span data-stu-id="21a46-122">Phone usage</span></span></th>
<th><span data-ttu-id="21a46-123">Trunk</span><span class="sxs-lookup"><span data-stu-id="21a46-123">Trunk</span></span></th>
<th><span data-ttu-id="21a46-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="21a46-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21a46-125">Route locale Redmond</span><span class="sxs-lookup"><span data-stu-id="21a46-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="21a46-126">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="21a46-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="21a46-127">Locale</span><span class="sxs-lookup"><span data-stu-id="21a46-127">Local</span></span></p>
<p><span data-ttu-id="21a46-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="21a46-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="21a46-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="21a46-129">Trunk1</span></span></p>
<p><span data-ttu-id="21a46-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="21a46-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="21a46-131">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="21a46-131">Red-GW1</span></span></p>
<p><span data-ttu-id="21a46-132">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="21a46-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21a46-133">Route locale Dallas</span><span class="sxs-lookup"><span data-stu-id="21a46-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="21a46-134">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="21a46-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="21a46-135">Locale</span><span class="sxs-lookup"><span data-stu-id="21a46-135">Local</span></span></p></td>
<td><p><span data-ttu-id="21a46-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="21a46-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="21a46-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="21a46-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21a46-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="21a46-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="21a46-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="21a46-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="21a46-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="21a46-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="21a46-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="21a46-141">Trunk1</span></span></p>
<p><span data-ttu-id="21a46-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="21a46-142">Trunk2</span></span></p>
<p><span data-ttu-id="21a46-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="21a46-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="21a46-144">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="21a46-144">Red-GW1</span></span></p>
<p><span data-ttu-id="21a46-145">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="21a46-145">Red-GW2</span></span></p>
<p><span data-ttu-id="21a46-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="21a46-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21a46-147">Route utenti Dallas</span><span class="sxs-lookup"><span data-stu-id="21a46-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="21a46-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="21a46-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="21a46-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="21a46-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="21a46-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="21a46-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="21a46-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="21a46-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="21a46-p104">Nella tabella 1, è stato aggiunto l'utilizzo telefono GlobalPSTNHopoff dopo l'utilizzo telefono DallasUsers nei criteri di chiamata Dallas. In questo modo, le chiamate con i criteri di chiamata Dallas possono utilizzare le route configurate per l'utilizzo telefono GlobalPSTNHopoff se non è disponibile una route per l'utilizzo telefono DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="21a46-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

