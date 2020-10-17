---
title: 'Lync Server 2013: requisiti dei certificati per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87657340205722a721485f213029220641885075
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533393"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="94c55-102">Requisiti dei certificati per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94c55-102">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94c55-103">_**Ultimo argomento modificato:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="94c55-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="94c55-104">Se si distribuisce la funzionalità di mobilità e si supporta l'individuazione automatica per i client mobili, è necessario includere determinate voci di nomi alternativi soggetto nei certificati per supportare le connessioni sicure dai client mobili.</span><span class="sxs-lookup"><span data-stu-id="94c55-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="94c55-105">È necessario includere voci di nomi alternativi soggetto per l'individuazione automatica nei certificati seguenti:</span><span class="sxs-lookup"><span data-stu-id="94c55-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="94c55-106">Pool Director</span><span class="sxs-lookup"><span data-stu-id="94c55-106">Director pool</span></span>

  - <span data-ttu-id="94c55-107">Pool Front End</span><span class="sxs-lookup"><span data-stu-id="94c55-107">Front End pool</span></span>

  - <span data-ttu-id="94c55-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="94c55-108">Reverse proxy</span></span>

<span data-ttu-id="94c55-109">In questa sezione vengono descritte le voci di nomi alternativi soggetto richieste nei certificati per l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="94c55-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94c55-110">La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma l'aggiunta di più voci di nomi alternativi soggetto ai certificati pubblici utilizzati dal proxy inverso può essere un compito oneroso.</span><span class="sxs-lookup"><span data-stu-id="94c55-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="94c55-111">Se esistono molti domini SIP, nel qual caso l'aggiunta di nomi alternativi soggetto è particolarmente onerosa, è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, anziché HTTPS come da configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="94c55-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="94c55-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-technical-requirements-for-mobility.md">requisiti tecnici per i dispositivi mobili in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="94c55-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="94c55-113">Requisiti relativi ai certificati per il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="94c55-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94c55-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94c55-114">Description</span></span></th>
<th><span data-ttu-id="94c55-115">Voce nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="94c55-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c55-116">URL interno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="94c55-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="94c55-117">SAN = LyncdiscoverInternal. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c55-118">URL esterno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="94c55-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="94c55-119">SAN = lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="94c55-120">In alternativa, è possibile utilizzare SAN = \*. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="94c55-121">Requisiti relativi ai certificati per il pool Front End</span><span class="sxs-lookup"><span data-stu-id="94c55-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94c55-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94c55-122">Description</span></span></th>
<th><span data-ttu-id="94c55-123">Voce nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="94c55-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c55-124">URL interno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="94c55-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="94c55-125">SAN = LyncdiscoverInternal. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c55-126">URL esterno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="94c55-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="94c55-127">SAN = lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="94c55-128">In alternativa, è possibile utilizzare SAN = \*. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="94c55-129">Requisiti relativi ai certificati del proxy inverso (CA pubblica)</span><span class="sxs-lookup"><span data-stu-id="94c55-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94c55-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94c55-130">Description</span></span></th>
<th><span data-ttu-id="94c55-131">Voce nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="94c55-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c55-132">URL esterno del servizio di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="94c55-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="94c55-133">SAN = lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="94c55-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="94c55-134">Questo nome alternativo del soggetto viene assegnato al certificato assegnato al listener SSL nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="94c55-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="94c55-135">Il listener del proxy inverso avrà nomi alternativi del soggetto per gli URL dei servizi Web esterni (ad esempio, SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com se è stato distribuito il server Director facoltativo).</span><span class="sxs-lookup"><span data-stu-id="94c55-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

