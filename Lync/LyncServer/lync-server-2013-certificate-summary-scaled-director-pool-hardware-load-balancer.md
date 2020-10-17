---
title: Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware
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
ms.openlocfilehash: 5c08fb5710e25bf4504d7cb2d10020138221b22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507923"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="38a1b-102">Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="38a1b-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38a1b-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="38a1b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="38a1b-104">I requisiti dei certificati per un server Director con un dispositivo di bilanciamento del carico hardware utilizzeranno un certificato predefinito con un nome soggetto e nomi alternativi soggetto per i servizi che il pool di server Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="38a1b-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="38a1b-105">Viene richiesto un certificato per ogni Director del pool.</span><span class="sxs-lookup"><span data-stu-id="38a1b-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="38a1b-106">Inoltre, esiste un certificato rilasciato dal token OAuth installato in ogni server per scopi di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="38a1b-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="38a1b-107">Certificati per un server Director in scala che utilizza un servizio di bilanciamento hardware</span><span class="sxs-lookup"><span data-stu-id="38a1b-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38a1b-108">Componente</span><span class="sxs-lookup"><span data-stu-id="38a1b-108">Component</span></span></th>
<th><span data-ttu-id="38a1b-109">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="38a1b-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="38a1b-110">Nomi alternativi soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="38a1b-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="38a1b-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="38a1b-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38a1b-112">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="38a1b-112">Default</span></span></p></td>
<td><p><span data-ttu-id="38a1b-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="38a1b-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="38a1b-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="38a1b-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="38a1b-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="38a1b-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="38a1b-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38a1b-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="38a1b-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38a1b-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="38a1b-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38a1b-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="38a1b-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38a1b-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="38a1b-120">(Facoltativamente) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38a1b-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="38a1b-121">I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="38a1b-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="38a1b-122">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="38a1b-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="38a1b-123">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="38a1b-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38a1b-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="38a1b-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="38a1b-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="38a1b-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="38a1b-126">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="38a1b-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="38a1b-127">Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="38a1b-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="38a1b-p102">Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="38a1b-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

