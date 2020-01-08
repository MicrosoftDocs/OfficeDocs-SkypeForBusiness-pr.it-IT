---
title: 'Lync Server 2013: requisiti DNS per i pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="8138b-102">Requisiti DNS per i pool Front-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8138b-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8138b-103">_**Argomento Ultima modifica:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="8138b-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="8138b-104">Questa sezione descrive i record DNS (Domain Name System) necessari per la distribuzione di pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="8138b-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="8138b-105">Record DNS per i pool Front-End</span><span class="sxs-lookup"><span data-stu-id="8138b-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="8138b-106">Nella tabella seguente sono specificati i requisiti DNS per una distribuzione del pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8138b-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="8138b-107">Requisiti DNS per un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="8138b-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8138b-108">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="8138b-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="8138b-109">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="8138b-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8138b-110">Pool Front end con più server front-end e un servizio di bilanciamento del carico hardware (indipendentemente dal fatto che il bilanciamento del carico DNS sia distribuito anche in tale pool)</span><span class="sxs-lookup"><span data-stu-id="8138b-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="8138b-111">Quando si usano sia il bilanciamento del carico DNS che un servizio di bilanciamento del carico hardware, è necessario ospitare record (A).</span><span class="sxs-lookup"><span data-stu-id="8138b-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="8138b-112">Creare un record interno che risolva il nome di dominio completo (FQDN) del pool Front-end per il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="8138b-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="8138b-113">Creare un record host interno (A) per i servizi Web interni all'indirizzo IP virtuale (VIP) del servizio di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="8138b-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="8138b-114">È necessario usare il nome servizi Web interni come definito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="8138b-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="8138b-115">Ad esempio, se si usano sia il bilanciamento del carico DNS che il bilanciamento del carico hardware, si avrà un record a per ogni server front-end in un pool per il bilanciamento del carico DNS e un record per i servizi Web interni che puntano all'IP virtuale del servizio di bilanciamento del carico hardware :</span><span class="sxs-lookup"><span data-stu-id="8138b-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="8138b-116">Bilanciamento del carico DNS: Pool01.contoso.net indirizzo IP del pool 10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="8138b-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="8138b-117">Ogni server front-end avrà anche un record distinto:</span><span class="sxs-lookup"><span data-stu-id="8138b-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="8138b-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="8138b-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="8138b-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="8138b-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="8138b-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="8138b-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="8138b-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="8138b-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="8138b-122">Bilanciamento del carico hardware: indirizzo IP WebInternal.contoso.net di HLB VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="8138b-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="8138b-123">Tutto il traffico ad eccezione del traffico HTTP/HTTPS userà il record Pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="8138b-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="8138b-124">Il traffico HTTP/HTTPS utilizzerà l'indirizzo dei servizi Web interni definiti di 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="8138b-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8138b-125">Pool Front end con bilanciamento del carico DNS distribuito</span><span class="sxs-lookup"><span data-stu-id="8138b-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="8138b-126">Un set di record interni che risolve il nome di dominio completo del pool nell'indirizzo IP di ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="8138b-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="8138b-127">È necessario un record per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="8138b-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8138b-128">Pool Front end con bilanciamento del carico DNS distribuito</span><span class="sxs-lookup"><span data-stu-id="8138b-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="8138b-129">Un set di record interni che risolve il nome di dominio completo di ogni server nel pool con l'indirizzo IP del server.</span><span class="sxs-lookup"><span data-stu-id="8138b-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="8138b-130">Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8138b-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8138b-131">Pool Front-end con un singolo server front-end e un database back-end dedicato ma nessun bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="8138b-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="8138b-132">Un record interno che risolve il nome di dominio completo del pool Front end con l'indirizzo IP del server front-end single Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8138b-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8138b-133">Accesso automatico client</span><span class="sxs-lookup"><span data-stu-id="8138b-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="8138b-134">Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;dominio&gt; sulla porta 5061 che esegue il mapping al nome di dominio completo del pool Front end che autentica e reindirizza le richieste client per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8138b-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="8138b-135">Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisiti DNS per l'accesso automatico al client in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8138b-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8138b-136">Individuazione del servizio Web di aggiornamento dispositivi da dispositivi Unified Communications (UC)</span><span class="sxs-lookup"><span data-stu-id="8138b-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="8138b-137">Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che risolve l'indirizzo IP del pool Front-end che ospita il servizio Web Update del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8138b-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="8138b-138">Nella situazione in cui è attivato un dispositivo UC, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il servizio Web di aggiornamento del dispositivo di hosting del pool Front end e di ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="8138b-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="8138b-139">In caso contrario, i dispositivi ottengono queste informazioni anche se il provisioning in banda è la prima volta che si accede a un utente.</span><span class="sxs-lookup"><span data-stu-id="8138b-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="8138b-140">Se si dispone di una distribuzione esistente del servizio Web Update per dispositivi in Lync Server 2010, è già stato creato un record interno con il nome ucupdates. &lt;Dominio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="8138b-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="8138b-141">Per Microsoft Office Communications Server 2007 R2, è necessario creare un record DNS aggiuntivo con il nome ucupdates-R2. &lt;Dominio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="8138b-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8138b-142">Proxy inverso per supportare il traffico HTTP</span><span class="sxs-lookup"><span data-stu-id="8138b-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="8138b-143">Un record esterno che risolve il nome di dominio completo della Web farm esterna nell'indirizzo IP esterno del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8138b-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="8138b-144">I client e i dispositivi UC usano questo record per connettersi al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8138b-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="8138b-145">Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determinare i requisiti DNS per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8138b-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8138b-146">Nella tabella seguente viene illustrato un esempio dei record DNS necessari per l'FQDN della Web farm interna.</span><span class="sxs-lookup"><span data-stu-id="8138b-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="8138b-147">Record DNS di esempio per l'FQDN della Web farm interna</span><span class="sxs-lookup"><span data-stu-id="8138b-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8138b-148">FQDN interno della Web farm</span><span class="sxs-lookup"><span data-stu-id="8138b-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="8138b-149">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="8138b-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="8138b-150">Record DNS (s)</span><span class="sxs-lookup"><span data-stu-id="8138b-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8138b-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8138b-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8138b-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8138b-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8138b-153">DNS un record per il ee-pool.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico usato dai server front-end.</span><span class="sxs-lookup"><span data-stu-id="8138b-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="8138b-154">Record DNS per webcon.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico usato dai server front-end.</span><span class="sxs-lookup"><span data-stu-id="8138b-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8138b-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8138b-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8138b-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8138b-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8138b-157">Record DNS per ee-pool.contoso.com che viene risolto nell'indirizzo IP virtuale (VIP) del servizio di bilanciamento del carico usato dai server front-end Enterprise Edition nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="8138b-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="8138b-158">Tieni presente che se usi il bilanciamento del carico DNS in questo pool, il tuo pool di front end e la Web farm interna non possono avere lo stesso nome FQDN.</span><span class="sxs-lookup"><span data-stu-id="8138b-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

