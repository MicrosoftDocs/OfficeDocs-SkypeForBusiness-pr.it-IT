---
title: 'Lync Server 2013: riepilogo del certificato-singolo amministratore'
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
ms.openlocfilehash: 677f9cf6e7cc9d260846598023435f33d2ebd2fc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="b4b99-102">Riepilogo del certificato-singolo amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4b99-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4b99-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b4b99-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b4b99-104">I requisiti dei certificati per un singolo server Director sono costituiti da un certificato predefinito che ha un nome soggetto e nomi alternativi del soggetto per i servizi che il Director può ricevere.</span><span class="sxs-lookup"><span data-stu-id="b4b99-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="b4b99-105">È inoltre presente un certificato token OAuth ai fini dell'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="b4b99-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="b4b99-106">Certificati per il Director</span><span class="sxs-lookup"><span data-stu-id="b4b99-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4b99-107">Componente</span><span class="sxs-lookup"><span data-stu-id="b4b99-107">Component</span></span></th>
<th><span data-ttu-id="b4b99-108">Nome soggetto (SN)</span><span class="sxs-lookup"><span data-stu-id="b4b99-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="b4b99-109">Nomi alternativi soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="b4b99-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="b4b99-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="b4b99-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4b99-111">Predefinita</span><span class="sxs-lookup"><span data-stu-id="b4b99-111">Default</span></span></p></td>
<td><p><span data-ttu-id="b4b99-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b4b99-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b4b99-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b4b99-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="b4b99-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4b99-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="b4b99-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4b99-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="b4b99-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4b99-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="b4b99-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4b99-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="b4b99-118">(Facoltativamente) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4b99-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b4b99-119">I certificati del server Director possono essere richiesti da un'autorità di certificazione (CA) gestita internamente o da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="b4b99-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="b4b99-120">Il Director risponde alle richieste provenienti dal proxy inverso nel perimetro o dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="b4b99-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="b4b99-121">I client interni non utilizzeranno il server Director.</span><span class="sxs-lookup"><span data-stu-id="b4b99-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="b4b99-122">In alternativa, una voce con caratteri jolly per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="b4b99-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b99-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="b4b99-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="b4b99-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b4b99-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b4b99-125">Nessuna voce</span><span class="sxs-lookup"><span data-stu-id="b4b99-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="b4b99-126">Si noti che la lunghezza minima della chiave è 1024, ma è possibile che si riceva un avviso che indica che la lunghezza minima consigliata per la chiave è 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="b4b99-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="b4b99-p103">Il certificato OAuthTokenIssuer è un certificato finalizzato al solo scopo di autenticare i server in un ambiente su larga scala e può essere richiesto a una CA interna o a una CA pubblica. Il certificato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b4b99-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

