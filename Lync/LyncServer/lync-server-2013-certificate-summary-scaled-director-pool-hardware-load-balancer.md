---
title: Riepilogo dei certificati - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware
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
ms.openlocfilehash: efcecbd1ec0c486e888a8c7303e450f75abf05bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="cb6c6-102">Riepilogo dei certificati - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb6c6-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb6c6-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cb6c6-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cb6c6-104">I requisiti di certificato per un amministratore con un servizio di bilanciamento del carico hardware utilizzeranno un certificato predefinito con nome soggetto e nomi alternativi oggetto per i servizi che il pool di Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="cb6c6-105">Viene richiesto un certificato per ogni amministratore del pool.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="cb6c6-106">È inoltre disponibile un certificato OAuth per gli scopi di autenticazione server-server installati in ogni server.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="cb6c6-107">Certificati per un amministratore in scala con un bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="cb6c6-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb6c6-108">Componente</span><span class="sxs-lookup"><span data-stu-id="cb6c6-108">Component</span></span></th>
<th><span data-ttu-id="cb6c6-109">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="cb6c6-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="cb6c6-110">Nomi alternativi oggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="cb6c6-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="cb6c6-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="cb6c6-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb6c6-112">Predefinita</span><span class="sxs-lookup"><span data-stu-id="cb6c6-112">Default</span></span></p></td>
<td><p><span data-ttu-id="cb6c6-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cb6c6-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="cb6c6-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cb6c6-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="cb6c6-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cb6c6-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="cb6c6-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb6c6-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="cb6c6-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb6c6-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="cb6c6-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb6c6-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="cb6c6-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb6c6-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="cb6c6-120">(Facoltativamente) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb6c6-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cb6c6-121">I certificati Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="cb6c6-122">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dall'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="cb6c6-123">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="cb6c6-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb6c6-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="cb6c6-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="cb6c6-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cb6c6-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="cb6c6-126">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="cb6c6-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="cb6c6-127">Tieni presente che la lunghezza della chiave minima è 1024, ma potresti ricevere un avviso che indica che la lunghezza della chiave minima consigliata è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="cb6c6-128">Il certificato OAuthTokenIssuer è un certificato a scopo unico per l'autenticazione dei server in un ambiente su larga scala e può essere richiesto da una CA interna o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-128">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="cb6c6-129">Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cb6c6-129">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

