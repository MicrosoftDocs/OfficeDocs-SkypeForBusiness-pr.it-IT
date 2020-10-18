---
title: 'Lync Server 2013: impostazioni di negoziazione per i partner federati XMPP'
description: 'Lync Server 2013: impostazioni di negoziazione per i partner federati XMPP.'
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
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578642"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="eae38-103">Impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae38-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae38-104">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="eae38-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="eae38-105">Le impostazioni per i tipi di negoziazione nella configurazione di un Partner XMPP offrono un'ampia gamma di possibili combinazioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="eae38-106">Non tutte le combinazioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="eae38-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="eae38-107">Nella tabella illustrata in questo argomento vengono elencate le impostazioni valide e quelle non valide.</span><span class="sxs-lookup"><span data-stu-id="eae38-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="eae38-108">Le configurazioni più comuni sono presentate nella prima tabella, mentre la seconda tabella contiene tutte le possibili combinazioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="eae38-109">Si noti che non è possibile disporre *di Simple Authentication and Security Layer* (SASL), **a meno che non** sia disponibile anche TLS ( *Transport Layer Security* ).</span><span class="sxs-lookup"><span data-stu-id="eae38-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="eae38-110">SASL viene inviato in un formato non crittografato (leggibile) e non dovrebbe mai essere trasmesso se non viene protetto in altro modo, ad esempio con TLS.</span><span class="sxs-lookup"><span data-stu-id="eae38-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="eae38-111">Metodi comuni di negoziazione per la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="eae38-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="eae38-112">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="eae38-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="eae38-113">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="eae38-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="eae38-114">Autenticazione dialback</span><span class="sxs-lookup"><span data-stu-id="eae38-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="eae38-115">Metodi di autenticazione previsti</span><span class="sxs-lookup"><span data-stu-id="eae38-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="eae38-116">Note</span><span class="sxs-lookup"><span data-stu-id="eae38-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eae38-117">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-117">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-118">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-118">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-119">False</span><span class="sxs-lookup"><span data-stu-id="eae38-119">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-120">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="eae38-p102">L'obbligatorietà di TLS e SASL aiuta ad assicurare la protezione del flusso di messaggi SASL. Il dialback non è disponibile e non può essere utilizzato come metodo di fallback se il partner federato XMPP non ha impostato TLS su obbligatorio o facoltativo.</span><span class="sxs-lookup"><span data-stu-id="eae38-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-123">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-123">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-125">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-125">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-126">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="eae38-p103">Impostando TLS come obbligatorio, se il partner federato XMPP ha impostato SASL su facoltativo o su obbligatorio, viene utilizzato SASL. Se SASL non è disponibile, verrà utilizzato il dialback su TLS.</span><span class="sxs-lookup"><span data-stu-id="eae38-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-130">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-131">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-131">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-132">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="eae38-p104">Molto flessibili nel metodo di negoziazione offerto, queste impostazioni si avvalgono delle impostazioni dei partner della federazione XMPP. Se TLS è facoltativo o obbligatorio per il partner ma SASL non è supportato, sarà disponibile il dialback TLS. Se TLS e SASL sono impostati su facoltativo o obbligatorio per il partner, viene utilizzata la selezione ottimale di TLS su SASL.</span><span class="sxs-lookup"><span data-stu-id="eae38-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-136">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-137">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-138">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-138">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-139">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="eae38-p105">In molti casi il dialback TCP è l'unica soluzione possibile. Meno desiderabile di altre opzioni, offre comunque un buon grado di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="eae38-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="eae38-142">Matrice dei metodi di negoziazione per la federazione XMPP - Completa</span><span class="sxs-lookup"><span data-stu-id="eae38-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="eae38-143">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="eae38-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="eae38-144">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="eae38-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="eae38-145">Autenticazione dialback</span><span class="sxs-lookup"><span data-stu-id="eae38-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="eae38-146">Metodo di autenticazione previsto</span><span class="sxs-lookup"><span data-stu-id="eae38-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="eae38-147">Note, avvisi o errori di configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="eae38-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eae38-148">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-148">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-149">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-149">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-150">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-150">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-151">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-152">Se SASL e TSL sono entrambi obbligatori, il dialback non verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="eae38-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-153">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-153">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-154">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-154">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-155">False</span><span class="sxs-lookup"><span data-stu-id="eae38-155">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-156">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-157">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-158">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-158">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-159">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-159">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-160">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p106">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-163">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-164">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-164">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-165">False</span><span class="sxs-lookup"><span data-stu-id="eae38-165">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-166">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p107">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-169">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-170">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-170">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-171">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-171">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-172">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p108">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-175">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-176">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-176">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-177">False</span><span class="sxs-lookup"><span data-stu-id="eae38-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-178">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="eae38-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p109">Poiché SASL richiede TLS, ma TLS non è disponibile, SASL/TLS ha esito negativo. Il dialback TCP è impostato su false e non può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="eae38-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-181">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-181">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-182">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-183">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-183">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-184">SASL su TLS, dialback TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-185">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-185">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-186">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-187">False</span><span class="sxs-lookup"><span data-stu-id="eae38-187">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-188">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-189">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-190">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-191">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-191">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-192">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p110">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-195">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-196">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-197">False</span><span class="sxs-lookup"><span data-stu-id="eae38-197">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-198">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p111">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-201">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-202">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-203">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-203">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-204">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p112">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-207">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-208">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-209">False</span><span class="sxs-lookup"><span data-stu-id="eae38-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-210">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="eae38-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-p113">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="eae38-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-213">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-213">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-214">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-215">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-215">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-216">Dialback TLS</span><span class="sxs-lookup"><span data-stu-id="eae38-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="eae38-217">La configurazione consente il dialback TLS.</span><span class="sxs-lookup"><span data-stu-id="eae38-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-218">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae38-218">Required</span></span></p></td>
<td><p><span data-ttu-id="eae38-219">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-220">False</span><span class="sxs-lookup"><span data-stu-id="eae38-220">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-221">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="eae38-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-222">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="eae38-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-223">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-224">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-225">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-225">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-226">Dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="eae38-227">Basato sulle scelte di negoziazione dell'altro endpoint, il dialback TCP o TLS verrà accettato.</span><span class="sxs-lookup"><span data-stu-id="eae38-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-228">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eae38-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="eae38-229">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-230">False</span><span class="sxs-lookup"><span data-stu-id="eae38-230">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-231">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="eae38-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-232">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="eae38-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae38-233">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-234">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-235">Vero</span><span class="sxs-lookup"><span data-stu-id="eae38-235">True</span></span></p></td>
<td><p><span data-ttu-id="eae38-236">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="eae38-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="eae38-237">Il dialback TCP è l'unico metodo di negoziazione disponibile</span><span class="sxs-lookup"><span data-stu-id="eae38-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae38-238">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-239">Non supportato</span><span class="sxs-lookup"><span data-stu-id="eae38-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="eae38-240">False</span><span class="sxs-lookup"><span data-stu-id="eae38-240">False</span></span></p></td>
<td><p><span data-ttu-id="eae38-241">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="eae38-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="eae38-242">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="eae38-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

