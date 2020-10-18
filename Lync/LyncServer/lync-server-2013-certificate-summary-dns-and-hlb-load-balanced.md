---
title: 'Lync Server 2013: riepilogo del certificato-bilanciamento del carico DNS e bilancio di HLB'
description: 'Lync Server 2013: riepilogo del certificato-bilanciamento del carico DNS e bilancio di HLB.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a89975af16b6e39625677f787d3726f00c76c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575972"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="d4587-103">Riepilogo del certificato-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4587-103">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4587-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d4587-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d4587-105">I requisiti dei certificati per un server Director con bilanciamento del carico DNS e un dispositivo di bilanciamento del carico hardware utilizzeranno un certificato predefinito che ha un nome soggetto e i nomi alternativi del soggetto per i servizi che il Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="d4587-105">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="d4587-106">Viene richiesto un certificato per ogni Director del pool.</span><span class="sxs-lookup"><span data-stu-id="d4587-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="d4587-107">È importante ricordare che il bilanciamento del carico hardware bilancia soltanto il traffic proveniente dal proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d4587-107">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="d4587-108">Inoltre, esiste un certificato OAuth Token a fini di autenticazione server-to-server, installato su ciascun server.</span><span class="sxs-lookup"><span data-stu-id="d4587-108">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="d4587-109">Certificati per il Director</span><span class="sxs-lookup"><span data-stu-id="d4587-109">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4587-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d4587-110">Component</span></span></th>
<th><span data-ttu-id="d4587-111">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="d4587-111">Subject name (SN)</span></span></th>
<th><span data-ttu-id="d4587-112">Nomi alternativi soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="d4587-112">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="d4587-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="d4587-113">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4587-114">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="d4587-114">Default</span></span></p></td>
<td><p><span data-ttu-id="d4587-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d4587-115">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d4587-116">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d4587-116">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="d4587-117">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d4587-117">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="d4587-118">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4587-118">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d4587-119">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4587-119">meet.contoso.com</span></span></p>
<p><span data-ttu-id="d4587-120">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4587-120">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="d4587-121">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4587-121">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="d4587-122">(Facoltativamente) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4587-122">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d4587-123">I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="d4587-123">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="d4587-124">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d4587-124">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="d4587-125">I client interni non utilizzeranno il server Director.</span><span class="sxs-lookup"><span data-stu-id="d4587-125">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="d4587-126">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="d4587-126">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4587-127">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="d4587-127">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="d4587-128">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d4587-128">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d4587-129">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="d4587-129">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="d4587-130">Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="d4587-130">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="d4587-p103">Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4587-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

