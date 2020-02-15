---
title: 'Lync Server 2013: impostazioni di negoziazione per i partner federati XMPP'
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="2daee-102">Impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daee-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2daee-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2daee-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2daee-104">Le impostazioni per i tipi di negoziazione nella configurazione di un Partner XMPP offrono un'ampia gamma di possibili combinazioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="2daee-105">Non tutte le combinazioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="2daee-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="2daee-106">Nella tabella illustrata in questo argomento vengono elencate le impostazioni valide e quelle non valide.</span><span class="sxs-lookup"><span data-stu-id="2daee-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="2daee-107">Le configurazioni più comuni sono presentate nella prima tabella, mentre la seconda tabella contiene tutte le possibili combinazioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="2daee-108">Si noti che non è possibile disporre *di Simple Authentication and Security Layer* (SASL), **a meno che non** sia disponibile anche TLS ( *Transport Layer Security* ).</span><span class="sxs-lookup"><span data-stu-id="2daee-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="2daee-109">SASL viene inviato in un formato non crittografato (leggibile) e non dovrebbe mai essere trasmesso se non viene protetto in altro modo, ad esempio con TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="2daee-110">Metodi comuni di negoziazione per la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="2daee-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="2daee-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="2daee-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="2daee-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="2daee-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="2daee-113">Autenticazione dialback</span><span class="sxs-lookup"><span data-stu-id="2daee-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="2daee-114">Metodi di autenticazione previsti</span><span class="sxs-lookup"><span data-stu-id="2daee-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="2daee-115">Notes</span><span class="sxs-lookup"><span data-stu-id="2daee-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2daee-116">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-116">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-117">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-117">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-118">False</span><span class="sxs-lookup"><span data-stu-id="2daee-118">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-119">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="2daee-p102">L'obbligatorietà di TLS e SASL aiuta ad assicurare la protezione del flusso di messaggi SASL. Il dialback non è disponibile e non può essere utilizzato come metodo di fallback se il partner federato XMPP non ha impostato TLS su obbligatorio o facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2daee-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-122">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-122">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-123">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-124">True</span><span class="sxs-lookup"><span data-stu-id="2daee-124">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-125">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2daee-p103">Impostando TLS come obbligatorio, se il partner federato XMPP ha impostato SASL su facoltativo o su obbligatorio, viene utilizzato SASL. Se SASL non è disponibile, verrà utilizzato il dialback su TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-128">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-130">True</span><span class="sxs-lookup"><span data-stu-id="2daee-130">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-131">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2daee-p104">Molto flessibili nel metodo di negoziazione offerto, queste impostazioni si avvalgono delle impostazioni dei partner della federazione XMPP. Se TLS è facoltativo o obbligatorio per il partner ma SASL non è supportato, sarà disponibile il dialback TLS. Se TLS e SASL sono impostati su facoltativo o obbligatorio per il partner, viene utilizzata la selezione ottimale di TLS su SASL.</span><span class="sxs-lookup"><span data-stu-id="2daee-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-135">Non supportato</span><span class="sxs-lookup"><span data-stu-id="2daee-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-136">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-137">True</span><span class="sxs-lookup"><span data-stu-id="2daee-137">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-138">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2daee-p105">In molti casi il dialback TCP è l'unica soluzione possibile. Meno desiderabile di altre opzioni, offre comunque un buon grado di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="2daee-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="2daee-141">Matrice dei metodi di negoziazione per la federazione XMPP - Completa</span><span class="sxs-lookup"><span data-stu-id="2daee-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="2daee-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="2daee-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="2daee-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="2daee-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="2daee-144">Autenticazione dialback</span><span class="sxs-lookup"><span data-stu-id="2daee-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="2daee-145">Metodo di autenticazione previsto</span><span class="sxs-lookup"><span data-stu-id="2daee-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="2daee-146">Note, avvisi o errori di configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="2daee-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2daee-147">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-147">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-148">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-148">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-149">True</span><span class="sxs-lookup"><span data-stu-id="2daee-149">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-150">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-151">Se SASL e TSL sono entrambi obbligatori, il dialback non verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2daee-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-152">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-152">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-153">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-153">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-154">False</span><span class="sxs-lookup"><span data-stu-id="2daee-154">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-155">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-156">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-157">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-157">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-158">True</span><span class="sxs-lookup"><span data-stu-id="2daee-158">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-159">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-160">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-160">SASL requires TLS.</span></span> <span data-ttu-id="2daee-161">Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-162">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-163">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-163">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-164">False</span><span class="sxs-lookup"><span data-stu-id="2daee-164">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-165">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-166">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-166">SASL requires TLS.</span></span> <span data-ttu-id="2daee-167">Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-168">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-169">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-169">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-170">True</span><span class="sxs-lookup"><span data-stu-id="2daee-170">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-171">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-172">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-172">SASL requires TLS.</span></span> <span data-ttu-id="2daee-173">Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-174">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-175">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-175">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-176">False</span><span class="sxs-lookup"><span data-stu-id="2daee-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-177">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="2daee-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-p109">Poiché SASL richiede TLS, ma TLS non è disponibile, SASL/TLS ha esito negativo. Il dialback TCP è impostato su false e non può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2daee-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-180">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-180">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-181">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-182">True</span><span class="sxs-lookup"><span data-stu-id="2daee-182">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-183">SASL su TLS, dialback TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-184">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-184">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-185">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-186">False</span><span class="sxs-lookup"><span data-stu-id="2daee-186">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-187">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-188">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-189">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-190">True</span><span class="sxs-lookup"><span data-stu-id="2daee-190">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-191">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-192">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-192">SASL requires TLS.</span></span> <span data-ttu-id="2daee-193">Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-194">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-195">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-196">False</span><span class="sxs-lookup"><span data-stu-id="2daee-196">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-197">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-198">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-198">SASL requires TLS.</span></span> <span data-ttu-id="2daee-199">Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-200">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-201">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-202">True</span><span class="sxs-lookup"><span data-stu-id="2daee-202">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-203">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-204">SASL richiede TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-204">SASL requires TLS.</span></span> <span data-ttu-id="2daee-205">Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-206">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-207">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-208">False</span><span class="sxs-lookup"><span data-stu-id="2daee-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-209">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="2daee-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-p113">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="2daee-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-212">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-212">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-213">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-214">True</span><span class="sxs-lookup"><span data-stu-id="2daee-214">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-215">Dialback TLS</span><span class="sxs-lookup"><span data-stu-id="2daee-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="2daee-216">La configurazione consente il dialback TLS.</span><span class="sxs-lookup"><span data-stu-id="2daee-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-217">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="2daee-217">Required</span></span></p></td>
<td><p><span data-ttu-id="2daee-218">Non supportato</span><span class="sxs-lookup"><span data-stu-id="2daee-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-219">False</span><span class="sxs-lookup"><span data-stu-id="2daee-219">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-220">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="2daee-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-221">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="2daee-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-222">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-223">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-224">True</span><span class="sxs-lookup"><span data-stu-id="2daee-224">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-225">Dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2daee-226">Basato sulle scelte di negoziazione dell'altro endpoint, il dialback TCP o TLS verrà accettato.</span><span class="sxs-lookup"><span data-stu-id="2daee-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-227">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2daee-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="2daee-228">Non supportato</span><span class="sxs-lookup"><span data-stu-id="2daee-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-229">False</span><span class="sxs-lookup"><span data-stu-id="2daee-229">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-230">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="2daee-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-231">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="2daee-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daee-232">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-233">Non supportata</span><span class="sxs-lookup"><span data-stu-id="2daee-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-234">True</span><span class="sxs-lookup"><span data-stu-id="2daee-234">True</span></span></p></td>
<td><p><span data-ttu-id="2daee-235">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="2daee-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2daee-236">Il dialback TCP è l'unico metodo di negoziazione disponibile</span><span class="sxs-lookup"><span data-stu-id="2daee-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daee-237">Non supportato</span><span class="sxs-lookup"><span data-stu-id="2daee-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-238">Non supportato</span><span class="sxs-lookup"><span data-stu-id="2daee-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2daee-239">False</span><span class="sxs-lookup"><span data-stu-id="2daee-239">False</span></span></p></td>
<td><p><span data-ttu-id="2daee-240">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="2daee-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2daee-241">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="2daee-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

