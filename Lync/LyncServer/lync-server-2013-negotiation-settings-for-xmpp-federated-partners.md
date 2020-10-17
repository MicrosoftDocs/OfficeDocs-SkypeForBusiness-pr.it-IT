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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505593"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="292cd-102">Impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="292cd-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="292cd-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="292cd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="292cd-104">Le impostazioni per i tipi di negoziazione nella configurazione di un Partner XMPP offrono un'ampia gamma di possibili combinazioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="292cd-105">Non tutte le combinazioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="292cd-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="292cd-106">Nella tabella illustrata in questo argomento vengono elencate le impostazioni valide e quelle non valide.</span><span class="sxs-lookup"><span data-stu-id="292cd-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="292cd-107">Le configurazioni più comuni sono presentate nella prima tabella, mentre la seconda tabella contiene tutte le possibili combinazioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="292cd-108">Si noti che non è possibile disporre *di Simple Authentication and Security Layer* (SASL), **a meno che non** sia disponibile anche TLS ( *Transport Layer Security* ).</span><span class="sxs-lookup"><span data-stu-id="292cd-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="292cd-109">SASL viene inviato in un formato non crittografato (leggibile) e non dovrebbe mai essere trasmesso se non viene protetto in altro modo, ad esempio con TLS.</span><span class="sxs-lookup"><span data-stu-id="292cd-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="292cd-110">Metodi comuni di negoziazione per la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="292cd-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="292cd-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="292cd-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="292cd-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="292cd-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="292cd-113">Autenticazione dialback</span><span class="sxs-lookup"><span data-stu-id="292cd-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="292cd-114">Metodi di autenticazione previsti</span><span class="sxs-lookup"><span data-stu-id="292cd-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="292cd-115">Note</span><span class="sxs-lookup"><span data-stu-id="292cd-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292cd-116">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-116">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-117">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-117">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-118">False</span><span class="sxs-lookup"><span data-stu-id="292cd-118">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-119">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="292cd-p102">L'obbligatorietà di TLS e SASL aiuta ad assicurare la protezione del flusso di messaggi SASL. Il dialback non è disponibile e non può essere utilizzato come metodo di fallback se il partner federato XMPP non ha impostato TLS su obbligatorio o facoltativo.</span><span class="sxs-lookup"><span data-stu-id="292cd-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-122">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-122">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-123">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-124">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-124">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-125">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="292cd-p103">Impostando TLS come obbligatorio, se il partner federato XMPP ha impostato SASL su facoltativo o su obbligatorio, viene utilizzato SASL. Se SASL non è disponibile, verrà utilizzato il dialback su TLS.</span><span class="sxs-lookup"><span data-stu-id="292cd-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-128">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-130">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-130">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-131">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="292cd-p104">Molto flessibili nel metodo di negoziazione offerto, queste impostazioni si avvalgono delle impostazioni dei partner della federazione XMPP. Se TLS è facoltativo o obbligatorio per il partner ma SASL non è supportato, sarà disponibile il dialback TLS. Se TLS e SASL sono impostati su facoltativo o obbligatorio per il partner, viene utilizzata la selezione ottimale di TLS su SASL.</span><span class="sxs-lookup"><span data-stu-id="292cd-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-135">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-136">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-137">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-137">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-138">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="292cd-p105">In molti casi il dialback TCP è l'unica soluzione possibile. Meno desiderabile di altre opzioni, offre comunque un buon grado di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="292cd-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="292cd-141">Matrice dei metodi di negoziazione per la federazione XMPP - Completa</span><span class="sxs-lookup"><span data-stu-id="292cd-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="292cd-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="292cd-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="292cd-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="292cd-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="292cd-144">Autenticazione dialback</span><span class="sxs-lookup"><span data-stu-id="292cd-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="292cd-145">Metodo di autenticazione previsto</span><span class="sxs-lookup"><span data-stu-id="292cd-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="292cd-146">Note, avvisi o errori di configurazione non valida</span><span class="sxs-lookup"><span data-stu-id="292cd-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292cd-147">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-147">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-148">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-148">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-149">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-149">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-150">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-151">Se SASL e TSL sono entrambi obbligatori, il dialback non verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="292cd-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-152">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-152">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-153">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-153">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-154">False</span><span class="sxs-lookup"><span data-stu-id="292cd-154">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-155">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-156">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-157">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-157">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-158">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-158">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-159">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p106">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-162">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-163">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-163">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-164">False</span><span class="sxs-lookup"><span data-stu-id="292cd-164">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-165">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p107">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-168">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-169">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-169">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-170">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-170">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-171">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p108">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-174">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-175">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-175">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-176">False</span><span class="sxs-lookup"><span data-stu-id="292cd-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-177">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="292cd-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p109">Poiché SASL richiede TLS, ma TLS non è disponibile, SASL/TLS ha esito negativo. Il dialback TCP è impostato su false e non può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="292cd-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-180">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-180">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-181">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-182">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-182">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-183">SASL su TLS, dialback TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-184">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-184">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-185">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-186">False</span><span class="sxs-lookup"><span data-stu-id="292cd-186">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-187">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-188">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-189">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-190">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-190">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-191">SASL su TLS, dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p110">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-194">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-195">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-196">False</span><span class="sxs-lookup"><span data-stu-id="292cd-196">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-197">SASL su TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p111">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-200">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-201">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-202">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-202">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-203">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p112">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-206">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-207">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-208">False</span><span class="sxs-lookup"><span data-stu-id="292cd-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-209">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="292cd-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-p113">SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="292cd-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-212">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-212">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-213">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-214">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-214">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-215">Dialback TLS</span><span class="sxs-lookup"><span data-stu-id="292cd-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="292cd-216">La configurazione consente il dialback TLS.</span><span class="sxs-lookup"><span data-stu-id="292cd-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-217">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="292cd-217">Required</span></span></p></td>
<td><p><span data-ttu-id="292cd-218">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-219">False</span><span class="sxs-lookup"><span data-stu-id="292cd-219">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-220">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="292cd-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-221">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="292cd-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-222">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-223">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-224">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-224">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-225">Dialback TLS, dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="292cd-226">Basato sulle scelte di negoziazione dell'altro endpoint, il dialback TCP o TLS verrà accettato.</span><span class="sxs-lookup"><span data-stu-id="292cd-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-227">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="292cd-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="292cd-228">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-229">False</span><span class="sxs-lookup"><span data-stu-id="292cd-229">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-230">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="292cd-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-231">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="292cd-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292cd-232">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-233">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-234">Vero</span><span class="sxs-lookup"><span data-stu-id="292cd-234">True</span></span></p></td>
<td><p><span data-ttu-id="292cd-235">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="292cd-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="292cd-236">Il dialback TCP è l'unico metodo di negoziazione disponibile</span><span class="sxs-lookup"><span data-stu-id="292cd-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292cd-237">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-238">Non supportato</span><span class="sxs-lookup"><span data-stu-id="292cd-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="292cd-239">False</span><span class="sxs-lookup"><span data-stu-id="292cd-239">False</span></span></p></td>
<td><p><span data-ttu-id="292cd-240">Configurazione non valida.</span><span class="sxs-lookup"><span data-stu-id="292cd-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="292cd-241">È necessario abilitare SASL o Dialback.</span><span class="sxs-lookup"><span data-stu-id="292cd-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

