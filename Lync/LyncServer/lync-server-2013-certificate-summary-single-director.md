---
title: 'Lync Server 2013: Riepilogo dei certificati - singolo server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="1cf9d-102">Riepilogo dei certificati - singolo server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cf9d-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cf9d-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1cf9d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1cf9d-104">I requisiti di certificato per un singolo amministratore sono costituiti da un certificato predefinito con un nome soggetto e un oggetto alternativo per i servizi che il Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="1cf9d-105">È inoltre disponibile un certificato OAuth per gli scopi di autenticazione server-server.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="1cf9d-106">Certificati per Director</span><span class="sxs-lookup"><span data-stu-id="1cf9d-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1cf9d-107">Componente</span><span class="sxs-lookup"><span data-stu-id="1cf9d-107">Component</span></span></th>
<th><span data-ttu-id="1cf9d-108">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="1cf9d-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="1cf9d-109">Nomi alternativi oggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="1cf9d-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="1cf9d-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="1cf9d-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cf9d-111">Predefinita</span><span class="sxs-lookup"><span data-stu-id="1cf9d-111">Default</span></span></p></td>
<td><p><span data-ttu-id="1cf9d-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1cf9d-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1cf9d-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1cf9d-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="1cf9d-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf9d-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="1cf9d-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf9d-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="1cf9d-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf9d-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="1cf9d-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf9d-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="1cf9d-118">(Facoltativamente) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf9d-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1cf9d-119">I certificati Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="1cf9d-120">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dall'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="1cf9d-121">I client interni non useranno il Director.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="1cf9d-122">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="1cf9d-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf9d-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="1cf9d-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="1cf9d-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1cf9d-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1cf9d-125">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="1cf9d-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="1cf9d-126">Tieni presente che la lunghezza della chiave minima è 1024, ma potresti ricevere un avviso che indica che la lunghezza della chiave minima consigliata è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="1cf9d-127">Il certificato OAuthTokenIssuer è un certificato a scopo unico per l'autenticazione dei server in un ambiente su larga scala e può essere richiesto da una CA interna o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="1cf9d-128">Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

