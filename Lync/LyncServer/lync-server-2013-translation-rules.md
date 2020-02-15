---
title: 'Lync Server 2013: regole di conversione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16623d863e9ca4a252ad7249ba1933cfa6934b08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="d06ee-102">Regole di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d06ee-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d06ee-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d06ee-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d06ee-104">Lync Server 2013 Enterprise Voice richiede che tutte le stringhe di composizione vengano normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa).</span><span class="sxs-lookup"><span data-stu-id="d06ee-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="d06ee-105">In Microsoft Lync Server 2010, le regole di conversione sono supportate solo per i numeri denominati.</span><span class="sxs-lookup"><span data-stu-id="d06ee-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="d06ee-106">Nuovo in Microsoft Lync Server 2013, le regole di conversione sono supportate anche per i numeri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d06ee-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="d06ee-107">Il *trunk peer* ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere l'utilizzo del formato di composizione locale per i numeri.</span><span class="sxs-lookup"><span data-stu-id="d06ee-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="d06ee-108">Per convertire i numeri dal formato E.164 a quello locale, è possibile definire una o più regole di conversione per modificare l'URI richiesta prima di eseguirne il routing al trunk peer.</span><span class="sxs-lookup"><span data-stu-id="d06ee-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="d06ee-109">È possibile, ad esempio, scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.</span><span class="sxs-lookup"><span data-stu-id="d06ee-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="d06ee-110">Eseguendo la conversione delle route in uscita sul server, è possibile ridurre i requisiti di configurazione per ogni singolo peer trunk per tradurre i numeri di telefono in un formato di composizione locale.</span><span class="sxs-lookup"><span data-stu-id="d06ee-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="d06ee-111">Quando si pianificano i gateway e il numero di gateway da associare a un cluster di Mediation Server specifico, potrebbe essere utile raggruppare i peer trunk con requisiti di composizione locali simili.</span><span class="sxs-lookup"><span data-stu-id="d06ee-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="d06ee-112">In questo modo è possibile ridurre il numero di regole di conversione necessarie e il tempo necessario per scriverle.</span><span class="sxs-lookup"><span data-stu-id="d06ee-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d06ee-113">L'associazione di una o più regole di conversione a una configurazione trunk VoIP aziendale deve essere utilizzata come alternativa alla configurazione delle regole di conversione nel peer trunk.</span><span class="sxs-lookup"><span data-stu-id="d06ee-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="d06ee-114">Non associare regole di conversione a una configurazione trunk VoIP aziendale se sono state configurate regole di conversione nel peer trunk, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="d06ee-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="d06ee-115">Esempi di regole di traduzione</span><span class="sxs-lookup"><span data-stu-id="d06ee-115">Example Translation Rules</span></span>

<span data-ttu-id="d06ee-116">Gli esempi di regole di traduzione seguenti indicano come sviluppare regole nel server per convertire numeri dal formato E.164 a un formato locale per il trunk peer.</span><span class="sxs-lookup"><span data-stu-id="d06ee-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="d06ee-117">Per informazioni dettagliate sull'implementazione delle regole di conversione, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d06ee-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d06ee-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d06ee-118">Description</span></span></th>
<th><span data-ttu-id="d06ee-119">Cifre iniziali</span><span class="sxs-lookup"><span data-stu-id="d06ee-119">Starting Digits</span></span></th>
<th><span data-ttu-id="d06ee-120">Lunghezza</span><span class="sxs-lookup"><span data-stu-id="d06ee-120">Length</span></span></th>
<th><span data-ttu-id="d06ee-121">Cifre da rimuovere</span><span class="sxs-lookup"><span data-stu-id="d06ee-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="d06ee-122">Cifre da aggiungere</span><span class="sxs-lookup"><span data-stu-id="d06ee-122">Digits to Add</span></span></th>
<th><span data-ttu-id="d06ee-123">Formato corrispondente</span><span class="sxs-lookup"><span data-stu-id="d06ee-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="d06ee-124">Translation</span><span class="sxs-lookup"><span data-stu-id="d06ee-124">Translation</span></span></th>
<th><span data-ttu-id="d06ee-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d06ee-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d06ee-126">Composizione convenzionale di interurbane negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="d06ee-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="d06ee-127">(rimuovere il '+')</span><span class="sxs-lookup"><span data-stu-id="d06ee-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="d06ee-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="d06ee-128">+1</span></span></p></td>
<td><p><span data-ttu-id="d06ee-129">Esattamente 12</span><span class="sxs-lookup"><span data-stu-id="d06ee-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="d06ee-130">1 </span><span class="sxs-lookup"><span data-stu-id="d06ee-130">1</span></span></p></td>
<td><p><span data-ttu-id="d06ee-131">0</span><span class="sxs-lookup"><span data-stu-id="d06ee-131">0</span></span></p></td>
<td><p><span data-ttu-id="d06ee-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="d06ee-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="d06ee-133">$1</span><span class="sxs-lookup"><span data-stu-id="d06ee-133">$1</span></span></p></td>
<td><p><span data-ttu-id="d06ee-134">+14255551010 diventa 14255551010</span><span class="sxs-lookup"><span data-stu-id="d06ee-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d06ee-135">Composizione di interurbane internazionali negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="d06ee-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="d06ee-136">(rimuovere il '+' e aggiungere 011)</span><span class="sxs-lookup"><span data-stu-id="d06ee-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="d06ee-137">Almeno 11</span><span class="sxs-lookup"><span data-stu-id="d06ee-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="d06ee-138">1 </span><span class="sxs-lookup"><span data-stu-id="d06ee-138">1</span></span></p></td>
<td><p><span data-ttu-id="d06ee-139">011</span><span class="sxs-lookup"><span data-stu-id="d06ee-139">011</span></span></p></td>
<td><p><span data-ttu-id="d06ee-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="d06ee-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="d06ee-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="d06ee-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="d06ee-142">+441235551010 diventa 011441235551010</span><span class="sxs-lookup"><span data-stu-id="d06ee-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

