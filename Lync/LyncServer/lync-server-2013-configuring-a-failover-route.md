---
title: 'Lync Server 2013: Configurazione di una route di failover'
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="655e4-102">Configurazione di una route di failover in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="655e4-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="655e4-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="655e4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="655e4-104">L'esempio seguente mostra il modo in cui un amministratore può definire una route di failover da usare se Dallas-GW1 è in calo per la manutenzione o altrimenti non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="655e4-104">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable.</span></span> <span data-ttu-id="655e4-105">Le tabelle seguenti illustrano la modifica della configurazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="655e4-105">The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="655e4-106">Tabella 1.</span><span class="sxs-lookup"><span data-stu-id="655e4-106">Table 1.</span></span> <span data-ttu-id="655e4-107">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="655e4-107">User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="655e4-108">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="655e4-108">User policy</span></span></th>
<th><span data-ttu-id="655e4-109">Uso del telefono</span><span class="sxs-lookup"><span data-stu-id="655e4-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="655e4-110">Criteri di chiamata predefiniti</span><span class="sxs-lookup"><span data-stu-id="655e4-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="655e4-111">Locale</span><span class="sxs-lookup"><span data-stu-id="655e4-111">Local</span></span></p>
<p><span data-ttu-id="655e4-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="655e4-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="655e4-113">Criteri locali Redmond</span><span class="sxs-lookup"><span data-stu-id="655e4-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="655e4-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="655e4-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="655e4-115">Criteri di chiamata Dallas</span><span class="sxs-lookup"><span data-stu-id="655e4-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="655e4-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="655e4-116">DallasUsers</span></span></p>
<p><span data-ttu-id="655e4-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="655e4-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="655e4-118">Tabella 2.</span><span class="sxs-lookup"><span data-stu-id="655e4-118">Table 2.</span></span> <span data-ttu-id="655e4-119">Indirizza</span><span class="sxs-lookup"><span data-stu-id="655e4-119">Routes</span></span>

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
<th><span data-ttu-id="655e4-120">Nome Route</span><span class="sxs-lookup"><span data-stu-id="655e4-120">Route name</span></span></th>
<th><span data-ttu-id="655e4-121">Schema numerico</span><span class="sxs-lookup"><span data-stu-id="655e4-121">Number pattern</span></span></th>
<th><span data-ttu-id="655e4-122">Uso del telefono</span><span class="sxs-lookup"><span data-stu-id="655e4-122">Phone usage</span></span></th>
<th><span data-ttu-id="655e4-123">Tronco</span><span class="sxs-lookup"><span data-stu-id="655e4-123">Trunk</span></span></th>
<th><span data-ttu-id="655e4-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="655e4-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="655e4-125">Route locale Redmond</span><span class="sxs-lookup"><span data-stu-id="655e4-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="655e4-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="655e4-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="655e4-127">Locale</span><span class="sxs-lookup"><span data-stu-id="655e4-127">Local</span></span></p>
<p><span data-ttu-id="655e4-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="655e4-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="655e4-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="655e4-129">Trunk1</span></span></p>
<p><span data-ttu-id="655e4-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="655e4-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="655e4-131">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="655e4-131">Red-GW1</span></span></p>
<p><span data-ttu-id="655e4-132">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="655e4-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="655e4-133">Route locale di Dallas</span><span class="sxs-lookup"><span data-stu-id="655e4-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="655e4-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="655e4-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="655e4-135">Locale</span><span class="sxs-lookup"><span data-stu-id="655e4-135">Local</span></span></p></td>
<td><p><span data-ttu-id="655e4-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="655e4-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="655e4-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="655e4-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="655e4-138">Route universale</span><span class="sxs-lookup"><span data-stu-id="655e4-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="655e4-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="655e4-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="655e4-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="655e4-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="655e4-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="655e4-141">Trunk1</span></span></p>
<p><span data-ttu-id="655e4-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="655e4-142">Trunk2</span></span></p>
<p><span data-ttu-id="655e4-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="655e4-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="655e4-144">Rosso-GW1</span><span class="sxs-lookup"><span data-stu-id="655e4-144">Red-GW1</span></span></p>
<p><span data-ttu-id="655e4-145">Rosso-GW2</span><span class="sxs-lookup"><span data-stu-id="655e4-145">Red-GW2</span></span></p>
<p><span data-ttu-id="655e4-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="655e4-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="655e4-147">Route utenti Dallas</span><span class="sxs-lookup"><span data-stu-id="655e4-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="655e4-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="655e4-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="655e4-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="655e4-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="655e4-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="655e4-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="655e4-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="655e4-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="655e4-152">Nella tabella 1 viene aggiunto un uso telefonico di GlobalPSTNHopoff dopo l'uso del telefono DallasUsers nei criteri di chiamata di Dallas.</span><span class="sxs-lookup"><span data-stu-id="655e4-152">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy.</span></span> <span data-ttu-id="655e4-153">In questo modo, le chiamate con i criteri di chiamata di Dallas possono usare le route configurate per l'utilizzo di GlobalPSTNHopoff Phone se non è disponibile una route per l'utilizzo del telefono DallasUsers.</span><span class="sxs-lookup"><span data-stu-id="655e4-153">This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

