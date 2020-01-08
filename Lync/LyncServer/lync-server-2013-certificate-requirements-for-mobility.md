---
title: 'Lync Server 2013: Requisiti dei certificati per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="92d18-102">Requisiti dei certificati per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92d18-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92d18-103">_**Argomento Ultima modifica:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="92d18-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="92d18-104">Se si distribuisce la caratteristica mobilità e si supporta l'individuazione automatica per i client mobili, è necessario includere alcune voci alternative per i nomi dei soggetti in certificati per supportare connessioni sicure dai client mobili.</span><span class="sxs-lookup"><span data-stu-id="92d18-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="92d18-105">È necessario includere voci di nome alternative per l'individuazione automatica nei certificati seguenti:</span><span class="sxs-lookup"><span data-stu-id="92d18-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="92d18-106">Pool di Director</span><span class="sxs-lookup"><span data-stu-id="92d18-106">Director pool</span></span>

  - <span data-ttu-id="92d18-107">Pool Front End</span><span class="sxs-lookup"><span data-stu-id="92d18-107">Front End pool</span></span>

  - <span data-ttu-id="92d18-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="92d18-108">Reverse proxy</span></span>

<span data-ttu-id="92d18-109">In questa sezione vengono illustrate le voci di nome alternative oggetto necessarie per i certificati per l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="92d18-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92d18-110">La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma l'aggiunta di più voci di nomi alternativi soggetto ai certificati pubblici usati dal proxy inverso può essere costosa.</span><span class="sxs-lookup"><span data-stu-id="92d18-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="92d18-111">Se si hanno molti domini SIP, rendendo l'aggiunta di nomi alternativi oggetto molto costosi, è possibile configurare il proxy inverso per l'uso di HTTP per la richiesta di servizio di individuazione automatica iniziale, invece di usare HTTPS (la configurazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="92d18-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="92d18-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-technical-requirements-for-mobility.md">requisiti tecnici per la mobilità in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="92d18-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="92d18-113">Requisiti dei certificati del pool di Director</span><span class="sxs-lookup"><span data-stu-id="92d18-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92d18-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92d18-114">Description</span></span></th>
<th><span data-ttu-id="92d18-115">Voce alternativa nome oggetto</span><span class="sxs-lookup"><span data-stu-id="92d18-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d18-116">URL del servizio di individuazione automatica interno</span><span class="sxs-lookup"><span data-stu-id="92d18-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="92d18-117">SAN = LyncdiscoverInternal. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92d18-118">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="92d18-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="92d18-119">SAN = lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="92d18-120">In alternativa, è possibile usare SAN = \*. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="92d18-121">Requisiti del certificato del pool Front-End</span><span class="sxs-lookup"><span data-stu-id="92d18-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92d18-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92d18-122">Description</span></span></th>
<th><span data-ttu-id="92d18-123">Voce alternativa nome oggetto</span><span class="sxs-lookup"><span data-stu-id="92d18-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d18-124">URL del servizio di individuazione automatica interno</span><span class="sxs-lookup"><span data-stu-id="92d18-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="92d18-125">SAN = LyncdiscoverInternal. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92d18-126">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="92d18-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="92d18-127">SAN = lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="92d18-128">In alternativa, è possibile usare SAN = \*. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="92d18-129">Requisiti dei certificati reverse proxy (public CA)</span><span class="sxs-lookup"><span data-stu-id="92d18-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92d18-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92d18-130">Description</span></span></th>
<th><span data-ttu-id="92d18-131">Voce alternativa nome oggetto</span><span class="sxs-lookup"><span data-stu-id="92d18-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d18-132">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="92d18-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="92d18-133">SAN = lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="92d18-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="92d18-134">Questa SAN viene assegnata al certificato assegnato al listener SSL nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="92d18-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="92d18-135">Il listener del proxy inverso avrà nomi alternativi soggetti per gli URL dei servizi Web esterni, ad esempio SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com, se è stato distribuito il Director facoltativo.</span><span class="sxs-lookup"><span data-stu-id="92d18-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

