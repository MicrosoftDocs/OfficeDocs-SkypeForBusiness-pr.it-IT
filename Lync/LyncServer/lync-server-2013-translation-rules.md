---
title: 'Lync Server 2013: regole di traduzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="bfd32-102">Regole di traduzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfd32-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfd32-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="bfd32-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bfd32-104">Lync Server 2013 Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL).</span><span class="sxs-lookup"><span data-stu-id="bfd32-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="bfd32-105">In Microsoft Lync Server 2010 le regole di traduzione sono supportate solo per i numeri denominati.</span><span class="sxs-lookup"><span data-stu-id="bfd32-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="bfd32-106">Novità di Microsoft Lync Server 2013 sono supportate anche regole di traduzione per i numeri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfd32-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="bfd32-107">Il *peer trunk* , ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP, può richiedere che i numeri siano in formato di chiamata locale.</span><span class="sxs-lookup"><span data-stu-id="bfd32-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="bfd32-108">Per tradurre i numeri dal formato E. 164 a un formato di chiamata locale, è possibile definire una o più regole di traduzione per modificare l'URI della richiesta prima di instradarlo al peer trunk.</span><span class="sxs-lookup"><span data-stu-id="bfd32-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="bfd32-109">Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.</span><span class="sxs-lookup"><span data-stu-id="bfd32-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="bfd32-110">Eseguendo la conversione della route in uscita sul server, è possibile ridurre i requisiti di configurazione per ogni singolo peer trunk per tradurre i numeri di telefono in un formato di chiamata locale.</span><span class="sxs-lookup"><span data-stu-id="bfd32-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="bfd32-111">Quando si pianificano i gateway e il numero di gateway da associare a un cluster di Mediation Server specifico, potrebbe essere utile raggruppare i peer trunk con requisiti di selezione locali simili.</span><span class="sxs-lookup"><span data-stu-id="bfd32-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="bfd32-112">In questo articolo è possibile ridurre il numero di regole di traduzione necessarie e il tempo necessario per scriverle.</span><span class="sxs-lookup"><span data-stu-id="bfd32-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bfd32-113">L'associazione di una o più regole di traduzione con una configurazione trunk VoIP aziendale dovrebbe essere usata come alternativa alla configurazione delle regole di traduzione nel trunk peer.</span><span class="sxs-lookup"><span data-stu-id="bfd32-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="bfd32-114">Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="bfd32-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="bfd32-115">Esempio di regole di traduzione</span><span class="sxs-lookup"><span data-stu-id="bfd32-115">Example Translation Rules</span></span>

<span data-ttu-id="bfd32-116">Gli esempi seguenti di regole di traduzione mostrano come sviluppare regole nel server per tradurre i numeri dal formato E. 164 a un formato locale per il peer trunk.</span><span class="sxs-lookup"><span data-stu-id="bfd32-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="bfd32-117">Per informazioni dettagliate su come implementare le regole di traduzione, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bfd32-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="bfd32-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfd32-118">Description</span></span></th>
<th><span data-ttu-id="bfd32-119">Cifre iniziali</span><span class="sxs-lookup"><span data-stu-id="bfd32-119">Starting Digits</span></span></th>
<th><span data-ttu-id="bfd32-120">Lunghezza</span><span class="sxs-lookup"><span data-stu-id="bfd32-120">Length</span></span></th>
<th><span data-ttu-id="bfd32-121">Cifre da rimuovere</span><span class="sxs-lookup"><span data-stu-id="bfd32-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="bfd32-122">Cifre da aggiungere</span><span class="sxs-lookup"><span data-stu-id="bfd32-122">Digits to Add</span></span></th>
<th><span data-ttu-id="bfd32-123">Modello di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="bfd32-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="bfd32-124">Conversione</span><span class="sxs-lookup"><span data-stu-id="bfd32-124">Translation</span></span></th>
<th><span data-ttu-id="bfd32-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfd32-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfd32-126">Chiamata a lunga distanza convenzionale negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="bfd32-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="bfd32-127">(Elimina il ' +')</span><span class="sxs-lookup"><span data-stu-id="bfd32-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="bfd32-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="bfd32-128">+1</span></span></p></td>
<td><p><span data-ttu-id="bfd32-129">Esattamente 12</span><span class="sxs-lookup"><span data-stu-id="bfd32-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="bfd32-130">1</span><span class="sxs-lookup"><span data-stu-id="bfd32-130">1</span></span></p></td>
<td><p><span data-ttu-id="bfd32-131">0</span><span class="sxs-lookup"><span data-stu-id="bfd32-131">0</span></span></p></td>
<td><p><span data-ttu-id="bfd32-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="bfd32-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="bfd32-133">$1</span><span class="sxs-lookup"><span data-stu-id="bfd32-133">$1</span></span></p></td>
<td><p><span data-ttu-id="bfd32-134">+ 14255551010 diventa 14255551010</span><span class="sxs-lookup"><span data-stu-id="bfd32-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfd32-135">Chiamate interurbane internazionali degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="bfd32-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="bfd32-136">(Strip out ' +' e Add 011)</span><span class="sxs-lookup"><span data-stu-id="bfd32-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="bfd32-137">Almeno 11</span><span class="sxs-lookup"><span data-stu-id="bfd32-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="bfd32-138">1</span><span class="sxs-lookup"><span data-stu-id="bfd32-138">1</span></span></p></td>
<td><p><span data-ttu-id="bfd32-139">011</span><span class="sxs-lookup"><span data-stu-id="bfd32-139">011</span></span></p></td>
<td><p><span data-ttu-id="bfd32-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="bfd32-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="bfd32-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="bfd32-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="bfd32-142">+ 441235551010 diventa 011441235551010</span><span class="sxs-lookup"><span data-stu-id="bfd32-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

