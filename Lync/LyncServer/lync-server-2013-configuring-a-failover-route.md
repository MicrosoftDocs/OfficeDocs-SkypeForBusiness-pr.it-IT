---
title: 'Lync Server 2013: Configurazione di una route di failover'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="768d5-102">Configurazione di una route di failover in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="768d5-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="768d5-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="768d5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="768d5-104">L'esempio seguente mostra il modo in cui un amministratore può definire una route di failover da usare se Dallas-GW1 è in calo per la manutenzione o altrimenti non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="768d5-104">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable.</span></span> <span data-ttu-id="768d5-105">Le tabelle seguenti illustrano la modifica della configurazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="768d5-105">The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="768d5-106">Tabella 1.</span><span class="sxs-lookup"><span data-stu-id="768d5-106">Table 1.</span></span> <span data-ttu-id="768d5-107">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="768d5-107">User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="768d5-108">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="768d5-108">User policy</span></span></th>
<th><span data-ttu-id="768d5-109">Uso del telefono</span><span class="sxs-lookup"><span data-stu-id="768d5-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="768d5-110">Criteri di chiamata predefiniti</span><span class="sxs-lookup"><span data-stu-id="768d5-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="768d5-111">Locale</span><span class="sxs-lookup"><span data-stu-id="768d5-111">Local</span></span></p>
<p><span data-ttu-id="768d5-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="768d5-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="768d5-113">Criteri locali Redmond</span><span class="sxs-lookup"><span data-stu-id="768d5-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="768d5-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="768d5-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="768d5-115">Criteri di chiamata Dallas</span><span class="sxs-lookup"><span data-stu-id="768d5-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="768d5-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="768d5-116">DallasUsers</span></span></p>
<p><span data-ttu-id="768d5-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="768d5-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="768d5-118">Tabella 2.</span><span class="sxs-lookup"><span data-stu-id="768d5-118">Table 2.</span></span> <span data-ttu-id="768d5-119">Indirizza</span><span class="sxs-lookup"><span data-stu-id="768d5-119">Routes</span></span>

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
<th><span data-ttu-id="768d5-120">Nome Route</span><span class="sxs-lookup"><span data-stu-id="768d5-120">Route name</span></span></th>
<th><span data-ttu-id="768d5-121">Schema numerico</span><span class="sxs-lookup"><span data-stu-id="768d5-121">Number pattern</span></span></th>
<th><span data-ttu-id="768d5-122">Uso del telefono</span><span class="sxs-lookup"><span data-stu-id="768d5-122">Phone usage</span></span></th>
<th><span data-ttu-id="768d5-123">Tronco</span><span class="sxs-lookup"><span data-stu-id="768d5-123">Trunk</span></span></th>
<th><span data-ttu-id="768d5-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="768d5-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="768d5-125">Route locale Redmond</span><span class="sxs-lookup"><span data-stu-id="768d5-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="768d5-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="768d5-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="768d5-127">Locale</span><span class="sxs-lookup"><span data-stu-id="768d5-127">Local</span></span></p>
<p><span data-ttu-id="768d5-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="768d5-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="768d5-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="768d5-129">Trunk1</span></span></p>
<p><span data-ttu-id="768d5-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="768d5-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="768d5-131">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="768d5-131">Red-GW1</span></span></p>
<p><span data-ttu-id="768d5-132">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="768d5-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="768d5-133">Route locale di Dallas</span><span class="sxs-lookup"><span data-stu-id="768d5-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="768d5-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="768d5-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="768d5-135">Locale</span><span class="sxs-lookup"><span data-stu-id="768d5-135">Local</span></span></p></td>
<td><p><span data-ttu-id="768d5-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="768d5-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="768d5-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="768d5-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="768d5-138">Route universale</span><span class="sxs-lookup"><span data-stu-id="768d5-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="768d5-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="768d5-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="768d5-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="768d5-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="768d5-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="768d5-141">Trunk1</span></span></p>
<p><span data-ttu-id="768d5-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="768d5-142">Trunk2</span></span></p>
<p><span data-ttu-id="768d5-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="768d5-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="768d5-144">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="768d5-144">Red-GW1</span></span></p>
<p><span data-ttu-id="768d5-145">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="768d5-145">Red-GW2</span></span></p>
<p><span data-ttu-id="768d5-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="768d5-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="768d5-147">Route utenti Dallas</span><span class="sxs-lookup"><span data-stu-id="768d5-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="768d5-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="768d5-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="768d5-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="768d5-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="768d5-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="768d5-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="768d5-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="768d5-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="768d5-152">Nella tabella 1 viene aggiunto un uso telefonico di GlobalPSTNHopoff dopo l'uso del telefono DallasUsers nei criteri di chiamata di Dallas.</span><span class="sxs-lookup"><span data-stu-id="768d5-152">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy.</span></span> <span data-ttu-id="768d5-153">In questo modo, le chiamate con i criteri di chiamata di Dallas possono usare le route configurate per l'utilizzo di GlobalPSTNHopoff Phone se non è disponibile una route per l'utilizzo del telefono DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="768d5-153">This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

