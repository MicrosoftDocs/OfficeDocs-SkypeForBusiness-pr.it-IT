---
title: 'Lync Server 2013: requisiti DNS per la mobilità'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="67ccf-102">Requisiti DNS per la mobilità con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ccf-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67ccf-103">_**Argomento Ultima modifica:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="67ccf-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="67ccf-104">Quando si distribuisce la funzionalità di mobilità di Lync Server 2013, è possibile usare i nuovi URL disponibili con il servizio di individuazione automatica di Microsoft Lync Server 2013 oppure usare gli URL dei servizi Web esistenti.</span><span class="sxs-lookup"><span data-stu-id="67ccf-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="67ccf-105">Se usi gli URL esistenti, gli utenti devono immettere manualmente gli URL nelle impostazioni del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="67ccf-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="67ccf-106">Questa opzione viene in genere usata per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="67ccf-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="67ccf-107">Quando si usano i nuovi URL, i client mobili possono scoprire automaticamente le risorse di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67ccf-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="67ccf-108">Quando si supporta l'individuazione automatica, è necessario aggiungere nuovi record DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="67ccf-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="67ccf-109">In questa sezione vengono descritti i record DNS necessari per l'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="67ccf-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="67ccf-110">Per supportare l'individuazione automatica, è necessario creare i record DNS seguenti per ogni dominio SIP:</span><span class="sxs-lookup"><span data-stu-id="67ccf-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="67ccf-111">Record DNS interno per il supporto degli utenti mobili che si connettono dall'interno della rete dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="67ccf-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="67ccf-112">Record DNS esterno o pubblico per supportare gli utenti di dispositivi mobili che si connettono da Internet</span><span class="sxs-lookup"><span data-stu-id="67ccf-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="67ccf-113">L'URL di individuazione automatica interno non deve essere indirizzabile all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="67ccf-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="67ccf-114">L'URL di individuazione automatica esterna non deve essere indirizzabile dall'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="67ccf-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="67ccf-115">Tuttavia, se non è possibile soddisfare questo requisito per l'URL esterno, il client mobile non dovrebbe essere influenzato dal punto di vista.</span><span class="sxs-lookup"><span data-stu-id="67ccf-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="67ccf-116">I record DNS possono essere record CNAME o A (host).</span><span class="sxs-lookup"><span data-stu-id="67ccf-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="67ccf-117">**Record DNS interni**</span><span class="sxs-lookup"><span data-stu-id="67ccf-117">**Internal DNS records**</span></span>

<span data-ttu-id="67ccf-118">È necessario creare uno dei record DNS interni seguenti:</span><span class="sxs-lookup"><span data-stu-id="67ccf-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67ccf-119">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="67ccf-119">Record type</span></span></th>
<th><span data-ttu-id="67ccf-120">Nome host o definizione SRV</span><span class="sxs-lookup"><span data-stu-id="67ccf-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="67ccf-121">Risolve in</span><span class="sxs-lookup"><span data-stu-id="67ccf-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67ccf-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="67ccf-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="67ccf-123">lyncdiscoverinternal. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="67ccf-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="67ccf-124">Servizi Web interni nome di dominio completo (FQDN) per il pool di Director, se è presente o per il pool Front-end se non si dispone di un amministratore</span><span class="sxs-lookup"><span data-stu-id="67ccf-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ccf-125">A (host)</span><span class="sxs-lookup"><span data-stu-id="67ccf-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="67ccf-126">lyncdiscoverinternal. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="67ccf-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="67ccf-127">Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si usa un servizio di bilanciamento del carico del pool di Director, se si ha uno o del pool di front-end se non si ha un amministratore</span><span class="sxs-lookup"><span data-stu-id="67ccf-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67ccf-128">**Record DNS esterni**</span><span class="sxs-lookup"><span data-stu-id="67ccf-128">**External DNS records**</span></span>

<span data-ttu-id="67ccf-129">È necessario creare uno dei record DNS esterni seguenti:</span><span class="sxs-lookup"><span data-stu-id="67ccf-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67ccf-130">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="67ccf-130">Record type</span></span></th>
<th><span data-ttu-id="67ccf-131">Nome host</span><span class="sxs-lookup"><span data-stu-id="67ccf-131">Host name</span></span></th>
<th><span data-ttu-id="67ccf-132">Risolve in</span><span class="sxs-lookup"><span data-stu-id="67ccf-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67ccf-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="67ccf-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="67ccf-134">Lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="67ccf-134">lyncdiscover.</span></span> <span data-ttu-id="67ccf-135">&lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="67ccf-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="67ccf-136">FQDN dei servizi Web esterni per il pool di Director, se si ha uno o per il pool di front-end se non si ha un amministratore</span><span class="sxs-lookup"><span data-stu-id="67ccf-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ccf-137">A (host)</span><span class="sxs-lookup"><span data-stu-id="67ccf-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="67ccf-138">Lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="67ccf-138">lyncdiscover.</span></span> <span data-ttu-id="67ccf-139">&lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="67ccf-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="67ccf-140">Indirizzo IP esterno o pubblico (indirizzo VIP se si usa un bilanciamento del carico) del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="67ccf-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ccf-141">SRV</span><span class="sxs-lookup"><span data-stu-id="67ccf-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="67ccf-142">_sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="67ccf-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="67ccf-143">&lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="67ccf-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="67ccf-144">Risolve il record host (A o AAAA) per il servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="67ccf-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="67ccf-145">Per supportare il servizio di notifica push e il servizio notifica push Apple, è possibile creare un record SRV per ogni dominio SIP che include i client Microsoft Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="67ccf-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="67ccf-146">Questo requisito si applica solo ai client di Microsoft Lync Mobile su dispositivi mobili Apple o Microsoft based.</span><span class="sxs-lookup"><span data-stu-id="67ccf-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="67ccf-147">I dispositivi dispositivi e Nokia Symbian non usano la notifica push.</span><span class="sxs-lookup"><span data-stu-id="67ccf-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="67ccf-148">Lyncdiscover, nota anche come individuazione automatica, il traffico passa attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="67ccf-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="67ccf-149">Il record SRV punta a un record che viene risolto tramite il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="67ccf-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

