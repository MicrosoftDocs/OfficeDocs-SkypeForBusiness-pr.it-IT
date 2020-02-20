---
title: 'Lync Server 2013: requisiti DNS per i pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18c5b7d16cf5bb7fe13c68a025e9033899c62c4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="10d50-102">Requisiti DNS per i pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10d50-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10d50-103">_**Ultimo argomento modificato:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="10d50-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="10d50-104">In questa sezione vengono descritti i record DNS (Domain Name System) necessari per la distribuzione di pool Front End.</span><span class="sxs-lookup"><span data-stu-id="10d50-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="10d50-105">Record DNS per i pool Front End</span><span class="sxs-lookup"><span data-stu-id="10d50-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="10d50-106">Nella tabella seguente vengono specificati i requisiti DNS per la distribuzione di un pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10d50-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="10d50-107">Requisiti di DNS per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="10d50-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10d50-108">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="10d50-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="10d50-109">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="10d50-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10d50-110">Pool Front End con più Front End Server e un dispositivo di bilanciamento del carico hardware (indipendentemente dal fatto che nel pool sia implementato anche il bilanciamento del carico DNS)</span><span class="sxs-lookup"><span data-stu-id="10d50-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="10d50-111">Se si utilizza sia il bilanciamento del carico DNS che un dispositivo di bilanciamento del carico hardware, è necessario utilizzare record host (A).</span><span class="sxs-lookup"><span data-stu-id="10d50-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="10d50-112">Creare un record A interno che venga risolto nel nome di dominio completo (FQDN) del pool Front End per il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="10d50-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="10d50-113">Creare un record host (A) interno per i servizi Web interni nell'indirizzo IP virtuale del dispositivo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="10d50-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="10d50-114">È necessario utilizzare il nome dei servizi Web interni come definito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="10d50-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="10d50-115">Ad esempio, se si utilizzano sia il bilanciamento del carico DNS che il bilanciamento del carico hardware, è necessario un record a per ogni Front End Server in un pool per il bilanciamento del carico DNS e un record a per i servizi Web interni che puntano all'IP virtuale del dispositivo di bilanciamento del carico hardware. :</span><span class="sxs-lookup"><span data-stu-id="10d50-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="10d50-116">Bilanciamento del carico DNS:   Pool01.contoso.net   Indirizzo IP del pool   10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="10d50-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="10d50-117">Ogni Front End Server avrà anche un record A distinto:</span><span class="sxs-lookup"><span data-stu-id="10d50-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="10d50-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="10d50-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="10d50-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="10d50-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="10d50-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="10d50-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="10d50-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="10d50-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="10d50-122">Bilanciamento del carico hardware:   WebInternal.contoso.net   Indirizzo IP virtuale del dispositivo di bilanciamento del carico hardware   192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="10d50-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="10d50-p102">Tutto il traffico eccetto quello HTTP/HTTPS utilizzerà il record Pool01.contoso.net. Il traffico HTTP/HTTPS utilizzerà l'indirizzo dei servizi Web interni 192.168.10.5 definito</span><span class="sxs-lookup"><span data-stu-id="10d50-p102">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record. HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d50-125">Pool Front End con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="10d50-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="10d50-p103">Un set di record A interni che risolvono l'FQDN del pool nell'indirizzo IP di ogni server nel pool. Deve esistere un solo record A per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="10d50-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d50-128">Pool Front End con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="10d50-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="10d50-129">Un set di record A interni che risolvono l'FQDN di ogni server nell'indirizzo IP di tale server.</span><span class="sxs-lookup"><span data-stu-id="10d50-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="10d50-130">Per ulteriori informazioni, vedere <a href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="10d50-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d50-131">Pool Front End con un solo Front End Server e un database back-end dedicato, ma senza servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="10d50-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="10d50-132">Un record A interno che risolve l'FQDN del pool Front End nell'indirizzo IP del singolo server Enterprise Edition Front End Server.</span><span class="sxs-lookup"><span data-stu-id="10d50-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d50-133">Accesso client automatico</span><span class="sxs-lookup"><span data-stu-id="10d50-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="10d50-134">Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;domain&gt; over Port 5061 che corrisponde al nome di dominio completo del pool Front end che autentica e reindirizza le richieste client per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="10d50-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="10d50-135">Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for Automatic client Sign-in in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="10d50-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d50-136">Individuazione del servizio Web Aggiornamento dispositivi da parte di dispositivi per comunicazioni unificate</span><span class="sxs-lookup"><span data-stu-id="10d50-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="10d50-137">Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che si risolve nell'indirizzo IP del pool Front end che ospita il servizio Web aggiornamento dispositivi.</span><span class="sxs-lookup"><span data-stu-id="10d50-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="10d50-138">Se viene acceso un dispositivo per comunicazioni unificate, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il pool Front End che ospita il servizio Web Aggiornamento dispositivi e ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="10d50-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="10d50-139">In caso contrario, i dispositivi ottengono queste informazioni tramite il provisioning di tipo in-band la prima volta che un utente effettua l'accesso.</span><span class="sxs-lookup"><span data-stu-id="10d50-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="10d50-140">Se si dispone di una distribuzione esistente del servizio Web aggiornamento dispositivi in Lync Server 2010, è stato già creato un record interno con il nome ucupdates. &lt;Dominio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="10d50-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="10d50-141">Per Microsoft Office Communications Server 2007 R2, è necessario creare un record DNS aggiuntivo con il nome ucupdates-R2. &lt;Dominio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="10d50-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d50-142">Proxy inverso per il supporto del traffico HTTP</span><span class="sxs-lookup"><span data-stu-id="10d50-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="10d50-143">Un record A esterno che risolve l'FQDN della Web farm esterna nell'indirizzo IP esterno del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="10d50-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="10d50-144">I client e i dispositivi per comunicazioni unificate utilizzano questo record per la connessione al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="10d50-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="10d50-145">Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="10d50-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="10d50-146">Nella tabella seguente viene illustrato un esempio dei record DNS necessari per il nome di dominio completo (FQDN) della Web farm interna.</span><span class="sxs-lookup"><span data-stu-id="10d50-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="10d50-147">Record DNS di esempio per il nome di dominio completo (FQDN) della Web farm interna</span><span class="sxs-lookup"><span data-stu-id="10d50-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10d50-148">FQDN Web farm interna</span><span class="sxs-lookup"><span data-stu-id="10d50-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="10d50-149">FQDN pool</span><span class="sxs-lookup"><span data-stu-id="10d50-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="10d50-150">Record A DNS</span><span class="sxs-lookup"><span data-stu-id="10d50-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10d50-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10d50-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10d50-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10d50-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10d50-153">Record A DNS per ee-pool.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico utilizzato dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="10d50-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="10d50-154">Record A DNS per webcon.contoso.com che viene risolto nell'indirizzo VIP del servizio di bilanciamento del carico utilizzato dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="10d50-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d50-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10d50-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10d50-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10d50-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10d50-157">Record A DNS per ee-pool.contoso.com che viene risolto nell'indirizzo IP virtuale (VIP) del servizio di bilanciamento del carico utilizzato dai server Enterprise Edition Front End Server nel pool Front End.</span><span class="sxs-lookup"><span data-stu-id="10d50-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="10d50-158">Si noti che se si utilizza il bilanciamento del carico DNS nel pool, il pool Front End e la Web farm interna non potranno avere lo stesso FQDN.</span><span class="sxs-lookup"><span data-stu-id="10d50-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

