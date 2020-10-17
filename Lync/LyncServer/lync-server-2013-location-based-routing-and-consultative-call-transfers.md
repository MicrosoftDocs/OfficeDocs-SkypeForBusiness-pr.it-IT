---
title: 'Lync Server 2013: trasferimenti di chiamate di routing e di chiamata consultiva Location-Based'
description: 'Lync Server 2013: Location-Based trasferimenti di routing e di chiamata consultiva.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567672"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="894da-103">Location-Based trasferimenti di chiamate di routing e consultivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894da-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="894da-104">_**Ultimo argomento modificato:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="894da-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="894da-105">Oltre a applicare il routing Location-Based alle riunioni di Lync, l'applicazione Location-Based routing Conferencing applica Location-Based limitazioni del routing per i trasferimenti di chiamata consultiva che vengono esportati negli endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="894da-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="894da-106">Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="894da-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="894da-107">Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Lync).</span><span class="sxs-lookup"><span data-stu-id="894da-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="894da-108">L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (utente di Lync).</span><span class="sxs-lookup"><span data-stu-id="894da-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="894da-109">Utente A posiziona la chiamata con l'utente PSTN in attesa e chiama l'utente B. User B che accetta di parlare con l'utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="894da-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="894da-110">L'utente A trasferisce la chiamata in attesa all'utente B.</span><span class="sxs-lookup"><span data-stu-id="894da-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="894da-111">**Flusso delle chiamate di trasferimento delle chiamate consultive**</span><span class="sxs-lookup"><span data-stu-id="894da-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="894da-112">![Percorso basato sulla posizione per il diagramma delle conferenze](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Percorso basato sulla posizione per il diagramma delle conferenze")</span><span class="sxs-lookup"><span data-stu-id="894da-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="894da-113">Quando un utente abilitato per il routing Location-Based avvia un trasferimento di chiamata consultivo di un endpoint PSTN (come illustrato nella figura precedente), vengono create due chiamate attive, una chiamata tra l'utente PSTN e l'utente di Lync A e l'altra tra l'utente Lync A e l'utente di Lync B. il comportamento seguente viene applicato dall'applicazione di conferenza di routing Location-Based:</span><span class="sxs-lookup"><span data-stu-id="894da-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="894da-114">Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente di Lync B (ovvero destinazione di trasferimento), il trasferimento di chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="894da-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="894da-115">Questa autorizzazione viene eseguita in base alla posizione della parte trasferita che si trova nello stesso sito di rete del trunk SIP che esegue il routing della chiamata attiva all'endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="894da-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="894da-116">Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova l'entità trasferita (utente di Lync B) oppure che la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva all'endpoint PSTN (ovvero l'obiettivo di trasferimento di chiamata) verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="894da-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="894da-117">Nella tabella seguente viene descritto in che modo Location-Based le restrizioni di routing vengono applicate dall'applicazione di conferenza di routing Location-Based per i trasferimenti di chiamata consultiva.</span><span class="sxs-lookup"><span data-stu-id="894da-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="894da-118">Anche se gli endpoint PBX non sono direttamente associati a un sito di rete, il trunk SIP a cui è connesso il sistema PBX può essere assegnato a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="894da-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="894da-119">Pertanto, l'endpoint PBX può essere associato indirettamente a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="894da-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="894da-120">Sito di rete di una parte di chiamata trasferita</span><span class="sxs-lookup"><span data-stu-id="894da-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="894da-121">Sito di rete di destinazione trasferimento di chiamata</span><span class="sxs-lookup"><span data-stu-id="894da-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="894da-122">Comportamento</span><span class="sxs-lookup"><span data-stu-id="894da-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="894da-123">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-124">Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="894da-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="894da-125">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="894da-126">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-127">Utente di Lync in diversi siti di rete (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="894da-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="894da-128">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="894da-129">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-130">Utente di Lync in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="894da-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="894da-131">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="894da-132">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-133">Utente di Lync federato</span><span class="sxs-lookup"><span data-stu-id="894da-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="894da-134">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="894da-135">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-136">Endpoint PBX nello stesso sito (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="894da-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="894da-137">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="894da-138">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-139">Endpoint PBX in siti diversi (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="894da-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="894da-140">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="894da-141">Endpoint PBX nello stesso sito (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="894da-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="894da-142">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-143">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="894da-144">Endpoint PBX in un sito diverso (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="894da-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="894da-145">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="894da-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="894da-146">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="894da-147">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="894da-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="894da-148">Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="894da-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="894da-149">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="894da-150">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="894da-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="894da-151">Utente di Lync in diversi siti di rete (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="894da-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="894da-152">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="894da-153">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="894da-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="894da-154">Utente di Lync in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="894da-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="894da-155">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="894da-156">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="894da-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="894da-157">Utente di Lync federato</span><span class="sxs-lookup"><span data-stu-id="894da-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="894da-158">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="894da-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

