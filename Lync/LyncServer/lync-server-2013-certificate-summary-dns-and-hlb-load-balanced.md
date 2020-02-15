---
title: 'Lync Server 2013: riepilogo del certificato-bilanciamento del carico DNS e bilancio di HLB'
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
ms.openlocfilehash: 44b89f1b305b99d86fd1843ac61625083a5fb51b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="f3669-102">Riepilogo del certificato-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3669-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3669-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f3669-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f3669-104">I requisiti dei certificati per un server Director con bilanciamento del carico DNS e un dispositivo di bilanciamento del carico hardware utilizzeranno un certificato predefinito che ha un nome soggetto e i nomi alternativi del soggetto per i servizi che il Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="f3669-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="f3669-105">Viene richiesto un certificato per ogni Director del pool.</span><span class="sxs-lookup"><span data-stu-id="f3669-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="f3669-106">È importante ricordare che il bilanciamento del carico hardware bilancia soltanto il traffic proveniente dal proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f3669-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="f3669-107">Inoltre, esiste un certificato OAuth Token a fini di autenticazione server-to-server, installato su ciascun server.</span><span class="sxs-lookup"><span data-stu-id="f3669-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="f3669-108">Certificati per il Director</span><span class="sxs-lookup"><span data-stu-id="f3669-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3669-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f3669-109">Component</span></span></th>
<th><span data-ttu-id="f3669-110">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="f3669-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="f3669-111">Nomi alternativi soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="f3669-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="f3669-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="f3669-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3669-113">Predefinita</span><span class="sxs-lookup"><span data-stu-id="f3669-113">Default</span></span></p></td>
<td><p><span data-ttu-id="f3669-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f3669-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f3669-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f3669-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="f3669-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f3669-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="f3669-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f3669-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f3669-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f3669-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="f3669-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f3669-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="f3669-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f3669-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="f3669-121">(Facoltativamente) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f3669-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f3669-122">I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="f3669-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="f3669-123">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f3669-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="f3669-124">I client interni non utilizzeranno il server Director.</span><span class="sxs-lookup"><span data-stu-id="f3669-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="f3669-125">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="f3669-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3669-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="f3669-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="f3669-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f3669-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f3669-128">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="f3669-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="f3669-129">Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="f3669-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="f3669-p103">Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f3669-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

