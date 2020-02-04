---
title: 'Lync Server 2013: trasferimenti di routing e di chiamata consultiva basati sulla posizione'
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
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="7001d-102">Trasferimenti di routing e chiamate consultive basati sulla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7001d-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7001d-103">_**Argomento Ultima modifica:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="7001d-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="7001d-104">Oltre a applicare il routing basato sulla posizione alle riunioni Lync, l'applicazione per le conferenze di routing basata sulla posizione impone restrizioni di routing basate sulla posizione per i trasferimenti di chiamate consultive in uscita agli endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="7001d-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="7001d-105">Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="7001d-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="7001d-106">Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Lync).</span><span class="sxs-lookup"><span data-stu-id="7001d-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="7001d-107">L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (utente di Lync).</span><span class="sxs-lookup"><span data-stu-id="7001d-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="7001d-108">L'utente A inserisce la chiamata con l'utente PSTN in attesa e chiama l'utente B. l'utente B accetta di parlare con l'utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="7001d-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="7001d-109">L'utente A trasferisce la chiamata in attesa all'utente B.</span><span class="sxs-lookup"><span data-stu-id="7001d-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="7001d-110">**Flusso delle chiamate di trasferimento chiamate consultive**</span><span class="sxs-lookup"><span data-stu-id="7001d-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="7001d-111">![Diagramma del routing in base alla posizione per le conferenze](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Diagramma del routing in base alla posizione per le conferenze")</span><span class="sxs-lookup"><span data-stu-id="7001d-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="7001d-112">Quando un utente abilitato per il routing basato sulla posizione avvia un trasferimento di chiamata consultiva di un endpoint PSTN (come illustrato nella figura precedente), vengono create due chiamate attive, una chiamata tra l'utente PSTN e l'utente di Lync A e l'altra tra l'utente di Lync e l'utente di Lync B. il comportamento seguente viene applicato dall'applicazione di conferenza di routing basata sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="7001d-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="7001d-113">Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente di Lync B (vale a dire destinazione di trasferimento), il trasferimento della chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="7001d-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="7001d-114">Questa autorizzazione viene eseguita in base alla posizione dell'entità trasferita che si trova nello stesso sito di rete del trunk SIP che sta instradando la chiamata attiva all'endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="7001d-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="7001d-115">Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova l'entità trasferita (utente di Lync B) o che l'entità trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva alla PSTN endpoint (ad esempio destinazione trasferimento chiamate) verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="7001d-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="7001d-116">La tabella seguente descrive il modo in cui le restrizioni di routing basate sulla posizione vengono applicate dall'applicazione di conferenza di routing basata sulla posizione per i trasferimenti di chiamate consultive.</span><span class="sxs-lookup"><span data-stu-id="7001d-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="7001d-117">Anche se gli endpoint PBX non sono associati direttamente a un sito di rete, il trunk SIP a cui è connesso il PBX può essere assegnato a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="7001d-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="7001d-118">Di conseguenza, l'endpoint PBX può essere associato indirettamente a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="7001d-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7001d-119">Sito di rete della festa trasferita dalla chiamata</span><span class="sxs-lookup"><span data-stu-id="7001d-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="7001d-120">Sito di rete della destinazione del trasferimento delle chiamate</span><span class="sxs-lookup"><span data-stu-id="7001d-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="7001d-121">Comportamento</span><span class="sxs-lookup"><span data-stu-id="7001d-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7001d-122">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-123">Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="7001d-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7001d-124">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7001d-125">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-126">Utenti di Lync in siti di rete diversi (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="7001d-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7001d-127">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7001d-128">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-129">Utenti di Lync in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="7001d-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="7001d-130">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7001d-131">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-132">Utenti Lync federati</span><span class="sxs-lookup"><span data-stu-id="7001d-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="7001d-133">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7001d-134">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-135">Endpoint PBX nello stesso sito (ad esempio il sito 1)</span><span class="sxs-lookup"><span data-stu-id="7001d-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7001d-136">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7001d-137">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-138">Endpoint PBX in siti diversi (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="7001d-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7001d-139">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7001d-140">Endpoint PBX nello stesso sito (ad esempio il sito 1)</span><span class="sxs-lookup"><span data-stu-id="7001d-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7001d-141">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-142">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7001d-143">Endpoint PBX in un sito diverso (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="7001d-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7001d-144">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="7001d-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7001d-145">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7001d-146">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="7001d-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7001d-147">Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="7001d-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7001d-148">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7001d-149">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="7001d-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7001d-150">Utenti di Lync in siti di rete diversi (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="7001d-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7001d-151">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7001d-152">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="7001d-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7001d-153">Utenti di Lync in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="7001d-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="7001d-154">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7001d-155">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="7001d-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7001d-156">Utenti Lync federati</span><span class="sxs-lookup"><span data-stu-id="7001d-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="7001d-157">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="7001d-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

