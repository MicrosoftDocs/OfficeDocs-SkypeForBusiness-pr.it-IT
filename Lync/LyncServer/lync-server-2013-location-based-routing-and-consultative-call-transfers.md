---
title: 'Lync Server 2013: trasferimenti di chiamate di routing e di chiamata consultiva Location-Based'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513813"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="334aa-102">Location-Based trasferimenti di chiamate di routing e consultivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="334aa-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="334aa-103">_**Ultimo argomento modificato:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="334aa-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="334aa-104">Oltre a applicare il routing Location-Based alle riunioni di Lync, l'applicazione Location-Based routing Conferencing applica Location-Based limitazioni del routing per i trasferimenti di chiamata consultiva che vengono esportati negli endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="334aa-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="334aa-105">Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="334aa-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="334aa-106">Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Lync).</span><span class="sxs-lookup"><span data-stu-id="334aa-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="334aa-107">L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (utente di Lync).</span><span class="sxs-lookup"><span data-stu-id="334aa-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="334aa-108">Utente A posiziona la chiamata con l'utente PSTN in attesa e chiama l'utente B. User B che accetta di parlare con l'utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="334aa-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="334aa-109">L'utente A trasferisce la chiamata in attesa all'utente B.</span><span class="sxs-lookup"><span data-stu-id="334aa-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="334aa-110">**Flusso delle chiamate di trasferimento delle chiamate consultive**</span><span class="sxs-lookup"><span data-stu-id="334aa-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="334aa-111">![Percorso basato sulla posizione per il diagramma delle conferenze](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Percorso basato sulla posizione per il diagramma delle conferenze")</span><span class="sxs-lookup"><span data-stu-id="334aa-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="334aa-112">Quando un utente abilitato per il routing Location-Based avvia un trasferimento di chiamata consultivo di un endpoint PSTN (come illustrato nella figura precedente), vengono create due chiamate attive, una chiamata tra l'utente PSTN e l'utente di Lync A e l'altra tra l'utente Lync A e l'utente di Lync B. il comportamento seguente viene applicato dall'applicazione di conferenza di routing Location-Based:</span><span class="sxs-lookup"><span data-stu-id="334aa-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="334aa-113">Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente di Lync B (ovvero destinazione di trasferimento), il trasferimento di chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="334aa-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="334aa-114">Questa autorizzazione viene eseguita in base alla posizione della parte trasferita che si trova nello stesso sito di rete del trunk SIP che esegue il routing della chiamata attiva all'endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="334aa-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="334aa-115">Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova l'entità trasferita (utente di Lync B) oppure che la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva all'endpoint PSTN (ovvero l'obiettivo di trasferimento di chiamata) verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="334aa-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="334aa-116">Nella tabella seguente viene descritto in che modo Location-Based le restrizioni di routing vengono applicate dall'applicazione di conferenza di routing Location-Based per i trasferimenti di chiamata consultiva.</span><span class="sxs-lookup"><span data-stu-id="334aa-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="334aa-117">Anche se gli endpoint PBX non sono direttamente associati a un sito di rete, il trunk SIP a cui è connesso il sistema PBX può essere assegnato a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="334aa-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="334aa-118">Pertanto, l'endpoint PBX può essere associato indirettamente a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="334aa-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="334aa-119">Sito di rete di una parte di chiamata trasferita</span><span class="sxs-lookup"><span data-stu-id="334aa-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="334aa-120">Sito di rete di destinazione trasferimento di chiamata</span><span class="sxs-lookup"><span data-stu-id="334aa-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="334aa-121">Comportamento</span><span class="sxs-lookup"><span data-stu-id="334aa-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334aa-122">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-123">Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="334aa-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="334aa-124">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334aa-125">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-126">Utente di Lync in diversi siti di rete (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="334aa-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="334aa-127">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334aa-128">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-129">Utente di Lync in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="334aa-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="334aa-130">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334aa-131">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-132">Utente di Lync federato</span><span class="sxs-lookup"><span data-stu-id="334aa-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="334aa-133">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334aa-134">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-135">Endpoint PBX nello stesso sito (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="334aa-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="334aa-136">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334aa-137">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-138">Endpoint PBX in siti diversi (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="334aa-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="334aa-139">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334aa-140">Endpoint PBX nello stesso sito (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="334aa-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="334aa-141">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-142">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334aa-143">Endpoint PBX in un sito diverso (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="334aa-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="334aa-144">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="334aa-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="334aa-145">Il trasferimento consultivo non sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334aa-146">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="334aa-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="334aa-147">Utente di Lync nello stesso sito di rete (ad esempio, sito 1)</span><span class="sxs-lookup"><span data-stu-id="334aa-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="334aa-148">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334aa-149">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="334aa-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="334aa-150">Utente di Lync in diversi siti di rete (ad esempio, sito 2)</span><span class="sxs-lookup"><span data-stu-id="334aa-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="334aa-151">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334aa-152">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="334aa-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="334aa-153">Utente di Lync in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="334aa-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="334aa-154">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334aa-155">Endpoint PBX in qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="334aa-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="334aa-156">Utente di Lync federato</span><span class="sxs-lookup"><span data-stu-id="334aa-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="334aa-157">Il trasferimento consultivo sarà consentito</span><span class="sxs-lookup"><span data-stu-id="334aa-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

