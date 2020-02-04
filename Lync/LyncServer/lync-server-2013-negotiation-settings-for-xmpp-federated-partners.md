---
title: 'Lync Server 2013: Impostazioni di negoziazione per i partner federati XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="99d50-102">Impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99d50-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d50-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="99d50-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="99d50-104">Le impostazioni per i tipi di negoziazione nella configurazione di un partner XMPP hanno un'ampia varietà di combinazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="99d50-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="99d50-105">Non tutte le combinazioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="99d50-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="99d50-106">La tabella dettagliata in questo argomento definirà le impostazioni valide e non valide.</span><span class="sxs-lookup"><span data-stu-id="99d50-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="99d50-107">Le configurazioni comuni sono presentate nella prima tabella, la seconda tabella che descrive tutte le combinazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="99d50-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="99d50-108">Tieni presente che non puoi avere un protocollo SASL ( *Simple Authentication and Security Layer* ) **a meno che non** sia disponibile anche *Transport Layer Security* (TLS).</span><span class="sxs-lookup"><span data-stu-id="99d50-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="99d50-109">SASL viene inviato in formato non crittografato e non deve mai essere trasmesso a meno che non sia protetto da un altro mezzo, ad esempio TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="99d50-110">Metodi di negoziazione federativi comuni XMPP</span><span class="sxs-lookup"><span data-stu-id="99d50-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="99d50-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="99d50-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="99d50-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="99d50-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="99d50-113">Autenticazione richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="99d50-114">Metodo di autenticazione previsto (s)</span><span class="sxs-lookup"><span data-stu-id="99d50-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="99d50-115">Note</span><span class="sxs-lookup"><span data-stu-id="99d50-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d50-116">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-116">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-117">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-117">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-118">False</span><span class="sxs-lookup"><span data-stu-id="99d50-118">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-119">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="99d50-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="99d50-120">TLS e SASL necessari aiutano a garantire che il flusso di messaggi SASL sia sicuro.</span><span class="sxs-lookup"><span data-stu-id="99d50-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="99d50-121">Richiamata non è disponibile e non può essere usato per un metodo di fallback se il partner federato XMPP non ha impostato TLS su obbligatorio o facoltativo.</span><span class="sxs-lookup"><span data-stu-id="99d50-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-122">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-122">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-123">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-124">True</span><span class="sxs-lookup"><span data-stu-id="99d50-124">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-125">SASL su TLS, TLS richiamata, TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="99d50-126">Richiedendo TLS, se è usato il partner federato XMPP che ha impostato SASL su SASL facoltativo o richiesto.</span><span class="sxs-lookup"><span data-stu-id="99d50-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="99d50-127">Se SASL non è disponibile, verrà usato richiamata su TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-128">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-130">True</span><span class="sxs-lookup"><span data-stu-id="99d50-130">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-131">SASL su TLS, TLS richiamata, TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="99d50-132">Sebbene sia molto flessibile nei metodi di negoziazione offerti, queste impostazioni si basano sulle impostazioni del partner federativo XMPP.</span><span class="sxs-lookup"><span data-stu-id="99d50-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="99d50-133">Se il partner ha TLS facoltativo o obbligatorio, ma SASL non è supportato, TLS richiamata sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="99d50-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="99d50-134">Se il partner ha impostato TLS e SASL su facoltativo o obbligatorio, viene usata la selezione ottimale di TLS su SASL.</span><span class="sxs-lookup"><span data-stu-id="99d50-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-135">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-136">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-137">True</span><span class="sxs-lookup"><span data-stu-id="99d50-137">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-138">TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="99d50-139">In molti casi, TCP richiamata è l'unica soluzione possibile.</span><span class="sxs-lookup"><span data-stu-id="99d50-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="99d50-140">Meno auspicabile rispetto ad altre opzioni, offre un certo livello di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="99d50-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="99d50-141">Matrice del metodo di negoziazione della Federazione XMPP-completamento</span><span class="sxs-lookup"><span data-stu-id="99d50-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="99d50-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="99d50-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="99d50-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="99d50-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="99d50-144">Autenticazione richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="99d50-145">Metodo di autenticazione previsto</span><span class="sxs-lookup"><span data-stu-id="99d50-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="99d50-146">Note, avvisi o errori per la configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="99d50-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d50-147">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-147">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-148">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-148">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-149">True</span><span class="sxs-lookup"><span data-stu-id="99d50-149">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-150">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="99d50-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-151">Richiamata non funzionerà se sono necessari sia SASL che TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-152">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-152">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-153">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-153">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-154">False</span><span class="sxs-lookup"><span data-stu-id="99d50-154">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-155">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="99d50-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-156">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-157">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-157">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-158">True</span><span class="sxs-lookup"><span data-stu-id="99d50-158">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-159">SASL su TLS, TLS richiamata, TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-160">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-160">SASL requires TLS.</span></span> <span data-ttu-id="99d50-161">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-162">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-163">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-163">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-164">False</span><span class="sxs-lookup"><span data-stu-id="99d50-164">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-165">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="99d50-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-166">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-166">SASL requires TLS.</span></span> <span data-ttu-id="99d50-167">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-168">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-169">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-169">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-170">True</span><span class="sxs-lookup"><span data-stu-id="99d50-170">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-171">TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-172">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-172">SASL requires TLS.</span></span> <span data-ttu-id="99d50-173">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-174">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-175">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-175">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-176">False</span><span class="sxs-lookup"><span data-stu-id="99d50-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-177">Configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="99d50-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-178">Poiché SASL richiede TLS e TLS non è disponibile, SASL/TLS non riesce.</span><span class="sxs-lookup"><span data-stu-id="99d50-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="99d50-179">TCP richiamata è impostato su false e non può essere usato.</span><span class="sxs-lookup"><span data-stu-id="99d50-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-180">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-180">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-181">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-182">True</span><span class="sxs-lookup"><span data-stu-id="99d50-182">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-183">SASL su TLS, TLS richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-184">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-184">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-185">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-186">False</span><span class="sxs-lookup"><span data-stu-id="99d50-186">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-187">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="99d50-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-188">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-189">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-190">True</span><span class="sxs-lookup"><span data-stu-id="99d50-190">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-191">SASL su TLS, TLS richiamata, TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-192">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-192">SASL requires TLS.</span></span> <span data-ttu-id="99d50-193">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-194">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-195">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-196">False</span><span class="sxs-lookup"><span data-stu-id="99d50-196">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-197">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="99d50-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-198">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-198">SASL requires TLS.</span></span> <span data-ttu-id="99d50-199">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-200">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-201">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-202">True</span><span class="sxs-lookup"><span data-stu-id="99d50-202">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-203">TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-204">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-204">SASL requires TLS.</span></span> <span data-ttu-id="99d50-205">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-206">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-207">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-208">False</span><span class="sxs-lookup"><span data-stu-id="99d50-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-209">Configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="99d50-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-210">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-210">SASL requires TLS.</span></span> <span data-ttu-id="99d50-211">La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="99d50-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-212">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-212">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-213">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-214">True</span><span class="sxs-lookup"><span data-stu-id="99d50-214">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-215">TLS richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="99d50-216">La configurazione consente la richiamata TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-217">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="99d50-217">Required</span></span></p></td>
<td><p><span data-ttu-id="99d50-218">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-219">False</span><span class="sxs-lookup"><span data-stu-id="99d50-219">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-220">Configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="99d50-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-221">La funzionalità SASL o richiamata deve essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="99d50-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-222">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-223">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-224">True</span><span class="sxs-lookup"><span data-stu-id="99d50-224">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-225">TLS richiamata, TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="99d50-226">In base alle scelte di negoziazione dell'altro punto finale, verranno accettate le richiamata TCP o TLS.</span><span class="sxs-lookup"><span data-stu-id="99d50-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-227">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="99d50-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="99d50-228">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-229">False</span><span class="sxs-lookup"><span data-stu-id="99d50-229">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-230">Configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="99d50-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-231">La funzionalità SASL o richiamata deve essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="99d50-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d50-232">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-233">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-234">True</span><span class="sxs-lookup"><span data-stu-id="99d50-234">True</span></span></p></td>
<td><p><span data-ttu-id="99d50-235">TCP richiamata</span><span class="sxs-lookup"><span data-stu-id="99d50-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="99d50-236">TCP richiamata è l'unico metodo di negoziazione disponibile</span><span class="sxs-lookup"><span data-stu-id="99d50-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d50-237">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-238">Non supportato</span><span class="sxs-lookup"><span data-stu-id="99d50-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="99d50-239">False</span><span class="sxs-lookup"><span data-stu-id="99d50-239">False</span></span></p></td>
<td><p><span data-ttu-id="99d50-240">Configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="99d50-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="99d50-241">La funzionalità SASL o richiamata deve essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="99d50-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

