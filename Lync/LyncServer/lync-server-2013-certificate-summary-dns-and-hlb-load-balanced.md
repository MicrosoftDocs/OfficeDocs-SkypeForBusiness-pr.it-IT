---
title: 'Lync Server 2013: Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="30190-102">Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30190-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30190-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="30190-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="30190-104">I requisiti di certificato per un amministratore con bilanciamento del carico DNS e un servizio di bilanciamento del carico hardware utilizzeranno un certificato predefinito con un nome soggetto e un oggetto alternativo per i servizi che il Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="30190-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="30190-105">Viene richiesto un certificato per ogni amministratore del pool.</span><span class="sxs-lookup"><span data-stu-id="30190-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="30190-106">È importante ricordare che il bilanciamento del carico hardware è il bilanciamento del carico solo del traffico proveniente dal proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="30190-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="30190-107">È inoltre disponibile un certificato OAuth per gli scopi di autenticazione server-server installati in ogni server.</span><span class="sxs-lookup"><span data-stu-id="30190-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="30190-108">Certificati per Director</span><span class="sxs-lookup"><span data-stu-id="30190-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30190-109">Componente</span><span class="sxs-lookup"><span data-stu-id="30190-109">Component</span></span></th>
<th><span data-ttu-id="30190-110">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="30190-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="30190-111">Nomi alternativi oggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="30190-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="30190-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="30190-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30190-113">Predefinita</span><span class="sxs-lookup"><span data-stu-id="30190-113">Default</span></span></p></td>
<td><p><span data-ttu-id="30190-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="30190-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="30190-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="30190-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="30190-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="30190-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="30190-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30190-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="30190-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30190-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="30190-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30190-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="30190-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30190-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="30190-121">(Facoltativamente) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="30190-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30190-122">I certificati Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="30190-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="30190-123">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dall'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="30190-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="30190-124">I client interni non useranno il Director.</span><span class="sxs-lookup"><span data-stu-id="30190-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="30190-125">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="30190-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30190-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="30190-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="30190-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="30190-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="30190-128">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="30190-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="30190-129">Tieni presente che la lunghezza della chiave minima è 1024, ma potresti ricevere un avviso che indica che la lunghezza della chiave minima consigliata è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="30190-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="30190-130">Il certificato OAuthTokenIssuer è un certificato a scopo unico per l'autenticazione dei server in un ambiente su larga scala e può essere richiesto da una CA interna o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="30190-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="30190-131">Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30190-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

