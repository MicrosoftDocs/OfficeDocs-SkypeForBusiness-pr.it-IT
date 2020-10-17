---
title: Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware
description: Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08abc37940cd41a29d6620cfc0a2a801de4a8e38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572232"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="14061-103">Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="14061-103">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14061-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="14061-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="14061-105">I requisiti dei certificati per un server Director con un dispositivo di bilanciamento del carico hardware utilizzeranno un certificato predefinito con un nome soggetto e nomi alternativi soggetto per i servizi che il pool di server Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="14061-105">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="14061-106">Viene richiesto un certificato per ogni Director del pool.</span><span class="sxs-lookup"><span data-stu-id="14061-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="14061-107">Inoltre, esiste un certificato rilasciato dal token OAuth installato in ogni server per scopi di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="14061-107">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="14061-108">Certificati per un server Director in scala che utilizza un servizio di bilanciamento hardware</span><span class="sxs-lookup"><span data-stu-id="14061-108">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14061-109">Componente</span><span class="sxs-lookup"><span data-stu-id="14061-109">Component</span></span></th>
<th><span data-ttu-id="14061-110">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="14061-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="14061-111">Nomi alternativi soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="14061-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="14061-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="14061-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14061-113">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="14061-113">Default</span></span></p></td>
<td><p><span data-ttu-id="14061-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14061-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="14061-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14061-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="14061-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14061-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="14061-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14061-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="14061-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14061-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="14061-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14061-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="14061-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14061-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="14061-121">(Facoltativamente) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14061-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14061-122">I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="14061-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="14061-123">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="14061-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="14061-124">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="14061-124">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14061-125">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="14061-125">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="14061-126">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14061-126">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="14061-127">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="14061-127">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="14061-128">Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="14061-128">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="14061-p102">Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="14061-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

