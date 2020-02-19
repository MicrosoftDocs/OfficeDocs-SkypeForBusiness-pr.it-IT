---
title: 'Lync Server 2013: determinare i requisiti DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f27f9bf669db874ae276c2c2dff93bda451754
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42132739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="d0bcc-102">Determinare i requisiti DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0bcc-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0bcc-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d0bcc-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d0bcc-104">Utilizzare il diagramma di flusso seguente per determinare i requisiti DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="d0bcc-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="d0bcc-105">Le modifiche per gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 sono note in cui si applicano.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0bcc-106">Microsoft Lync Server 2013 supporta l'utilizzo dell'indirizzamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="d0bcc-107">Per utilizzare gli indirizzi IPv6, è inoltre necessario fornire il supporto per DNS IPv6 e configurare i record host DNS AAAA (noti come "Quad-A").</span><span class="sxs-lookup"><span data-stu-id="d0bcc-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="d0bcc-108">Nelle distribuzioni in cui vengono utilizzati sia IPv4 che IPv6, è preferibile configurare e gestire entrambi i record host A per IPv4 e host AAAA per IPv6.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="d0bcc-109">Anche se la distribuzione è stata completata completamente in IPv6, è possibile che i record host DNS IPv4 siano ancora necessari quando gli utenti esterni utilizzano ancora IPv4.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="d0bcc-110">**Determinazione del diagramma di flusso dei requisiti DNS**</span><span class="sxs-lookup"><span data-stu-id="d0bcc-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="d0bcc-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="d0bcc-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0bcc-112">Per impostazione predefinita, il nome del computer di un computer che non è aggiunto a un dominio è un nome host e non un nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d0bcc-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="d0bcc-113">Generatore di topologie utilizza FQDN, non nomi host.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="d0bcc-114">Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="d0bcc-115">Quando si assegnano FQDN dei server Lync, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno).</span><span class="sxs-lookup"><span data-stu-id="d0bcc-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="d0bcc-116">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d0bcc-117">I caratteri non standard in un FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="d0bcc-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="d0bcc-118">Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-dns-host-records.md">configure DNS Host Records for Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="d0bcc-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="d0bcc-119">Come i client Lync individuano i servizi</span><span class="sxs-lookup"><span data-stu-id="d0bcc-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="d0bcc-120">Microsoft Lync 2010, Lync 2013 e Lync mobile sono simili nel modo in cui il client trova e accede ai servizi in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="d0bcc-121">L'eccezione notevole è l'app di Windows Store Lync che utilizza un processo di percorso del servizio diverso.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="d0bcc-122">In questa sezione vengono illustrati due scenari in cui i client individuano i servizi, in primo luogo il metodo tradizionale tramite una serie di record SRV e host, in secondo luogo utilizzando solo i record del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="d0bcc-123">Gli aggiornamenti cumulativi dei client desktop modificano il processo di percorso DNS da Lync Server 2010 per tutti i client, il processo di query DNS continua fino a quando non viene restituita una query completata oppure l'elenco dei record DNS possibili è esausto e viene restituito l'errore finale il client.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="d0bcc-124">Per tutti i client **ad eccezione** dell'app di Windows Store Lync durante la ricerca DNS, i record SRV vengono interrogati e restituiti al client nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="d0bcc-125">LyncdiscoverInternal. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web interni</span><span class="sxs-lookup"><span data-stu-id="d0bcc-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="d0bcc-126">Lyncdiscover. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web esterni</span><span class="sxs-lookup"><span data-stu-id="d0bcc-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="d0bcc-127">\_sipinternaltls. \_TCP. \<record\> Domain SRV (Service Locator) per le connessioni TLS interne</span><span class="sxs-lookup"><span data-stu-id="d0bcc-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="d0bcc-128">\_sipinternal. \_TCP. \<record\> Domain SRV (Service Locator) per le connessioni TCP interne (eseguite solo se TCP è consentito)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="d0bcc-129">\_SIP. \_TLS. \<record\> Domain SRV (Service Locator) per connessioni TLS esterne</span><span class="sxs-lookup"><span data-stu-id="d0bcc-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="d0bcc-130">sipinternal. \<record\> del dominio a (host) per il pool o il Director front end, risolvibile solo nella rete interna</span><span class="sxs-lookup"><span data-stu-id="d0bcc-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="d0bcc-131">SIP. \<record\> del dominio a (host) per il pool Front end o il server Director nella rete interna oppure il servizio Access Edge quando il client è esterno</span><span class="sxs-lookup"><span data-stu-id="d0bcc-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="d0bcc-132">sipexternal. \<record\> del dominio a (host) per il servizio Access Edge quando il client è esterno</span><span class="sxs-lookup"><span data-stu-id="d0bcc-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="d0bcc-133">L'app Lync Windows Store cambia completamente il processo perché utilizza due record:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="d0bcc-134">LyncdiscoverInternal. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web interni</span><span class="sxs-lookup"><span data-stu-id="d0bcc-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="d0bcc-135">Lyncdiscover. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web esterni</span><span class="sxs-lookup"><span data-stu-id="d0bcc-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="d0bcc-136">Non è previsto alcun fallback per gli altri tipi di record.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="d0bcc-137">La differenza tra i metodi utilizzati per i client più recenti rispetto ai client meno recenti è che il servizio di individuazione automatica sta diventando il metodo preferito per individuare tutti i servizi.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="d0bcc-138">Quando una connessione ha esito positivo, il servizio di individuazione automatica restituisce tutti gli URL dei servizi Web per il pool principale dell'utente, incluso il servizio per dispositivi mobili (noto come MCX dalla directory virtuale creata per il servizio in IIS), Microsoft Lync Web App e gli URL dell'utilità di pianificazione Web.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="d0bcc-139">Tuttavia, sia l'URL del servizio per dispositivi mobili interno che l'URL del servizio per dispositivi mobili esterni è associato all'FQDN dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="d0bcc-140">Pertanto, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio per dispositivi mobili esternamente tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="d0bcc-141">Se gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 sono stati installati, il servizio di individuazione automatica restituisce anche i riferimenti a Internal/UCWA, External/UCWA e UCWA.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="d0bcc-142">Queste voci si riferiscono al componente Web di Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="d0bcc-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="d0bcc-143">Al momento, viene utilizzata solo la voce UCWA e viene fornito un riferimento a un URL per il componente Web.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="d0bcc-144">UCWA viene utilizzato dai client per dispositivi mobili Lync 2013 anziché dal servizio per dispositivi mobili di MCX utilizzato dai client di telefonia mobile di Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0bcc-145">Quando si creano record SRV, è importante tenere presente che devono puntare a un record DNS a e AAAA (se si utilizza IPv6 Addressing) nello stesso dominio in cui viene creato il record DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="d0bcc-146">Ad esempio, se il record SRV è in contoso.com, il record A e AAAA (se si utilizza l'indirizzamento IPv6) indica che non può trovarsi in fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="d0bcc-147">La configurazione predefinita consiste nel indirizzare tutto il traffico client per dispositivi mobili tramite il sito esterno.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="d0bcc-148">È possibile modificare le impostazioni in modo da restituire solo l'URL interno, se questo è più preferibile per i requisiti.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="d0bcc-149">Con questa configurazione, gli utenti possono utilizzare le applicazioni di Lync mobile nei propri dispositivi mobili solo quando si trovano all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="d0bcc-150">Per definire questa configurazione, è possibile utilizzare il cmdlet <STRONG>Set-CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d0bcc-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d0bcc-151">Anche se le applicazioni per dispositivi mobili possono connettersi ad altri servizi di Lync Server 2013, ad esempio il servizio Rubrica, le richieste Web interne dell'applicazione mobile passano all'FQDN Web esterno solo per il servizio per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="d0bcc-152">Altre richieste di servizio, ad esempio le richieste della Rubrica, non richiedono questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="d0bcc-153">I dispositivi mobili supportano l'individuazione manuale dei servizi.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="d0bcc-154">In questo caso, ogni utente deve configurare le impostazioni dei dispositivi mobili con gli URI del servizio di individuazione automatica interni ed esterni, inclusi il protocollo e il percorso, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="d0bcc-155">/Autodiscover/autodiscoverservice.svc/root\<d'\>ExtPoolFQDN https://per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d0bcc-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="d0bcc-156">/AutoDiscover/autodiscover.svc/root\<d'\>IntPoolFQDN https://per l'accesso interno</span><span class="sxs-lookup"><span data-stu-id="d0bcc-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="d0bcc-157">È consigliabile utilizzare l'individuazione automatica anziché l'individuazione manuale.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="d0bcc-158">Tuttavia, le impostazioni manuali possono essere utili per la risoluzione dei problemi relativi alla connettività del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="d0bcc-159">Configurazione del DNS split-brain con Lync Server</span><span class="sxs-lookup"><span data-stu-id="d0bcc-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="d0bcc-160">Il DNS split-brain è conosciuto da un certo numero di nomi, ad esempio, Split DNS o Split-Horizon DNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="d0bcc-161">In questo articolo viene descritta una configurazione DNS in cui sono presenti due aree DNS con lo stesso spazio dei nomi, ma solo una richiesta di servizi di area DNS solo interna e l'altra richiede solo le richieste esterne di servizi di zona DNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="d0bcc-162">Tuttavia, molti dei DNS SRV e di un record contenuti nel DNS interno non saranno contenuti nel DNS esterno e anche l'inverso è vero.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="d0bcc-163">Nei casi in cui lo stesso record DNS esista sia nel DNS interno che in quello esterno (ad esempio, www.contoso.com), l'indirizzo IP restituito sarà diverso in base al percorso (interno o esterno) della query.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0bcc-164">Attualmente, il DNS split-brain non è supportato per la mobilità, o più in particolare, i record DNS di LyncDiscover e LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="d0bcc-165">LyncDiscover deve essere definito in un server DNS esterno e LyncDiscoverInternal deve essere definito in un server DNS interno.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="d0bcc-166">Ai fini di questi argomenti, verrà utilizzato il termine DNS split-brain.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="d0bcc-167">Se si sta configurando il DNS split-brain, l'area interna ed esterna seguente contiene un riepilogo dei tipi di record DNS necessari in ogni area.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="d0bcc-168">Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d0bcc-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="d0bcc-169">**DNS interno:**</span><span class="sxs-lookup"><span data-stu-id="d0bcc-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="d0bcc-170">Contiene un'area DNS denominata contoso.com per la quale è autorevole</span><span class="sxs-lookup"><span data-stu-id="d0bcc-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="d0bcc-171">L'area interna di contoso.com contiene:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="d0bcc-172">DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client Lync Server 2013 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="d0bcc-173">DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o i record CNAME per l'individuazione automatica dei servizi Web di Lync Server 2013 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="d0bcc-174">DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per il nome del pool Front End, il nome del pool di Director o del server Director e tutti i server interni in cui è in esecuzione Lync 2013 nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="d0bcc-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="d0bcc-175">DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per l'interfaccia interna perimetrale di ogni Lync Server 2013, Edge Server nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="d0bcc-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="d0bcc-176">DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per l'interfaccia interna di ogni server proxy inverso nella rete perimetrale (facoltativo per la gestione del proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="d0bcc-177">Tutte le interfacce perimetrali interne di Lync Server 2013 perimetro della rete di bordo utilizzano l'area DNS interna per la risoluzione delle query in contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="d0bcc-178">Tutti i server che eseguono Lync Server 2013 e i client che eseguono Lync 2013 nella rete aziendale puntano ai server DNS interni per la risoluzione delle query in contoso.com o all'utilizzo del file HOSTs in ogni server perimetrale ed elenchi A e AAAA (se si utilizzano i record di indirizzamento IPv6) per server hop successivo, in particolare il VIP del Director o del Director, il VIP del pool Front end o il server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d0bcc-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="d0bcc-179">**DNS esterno:**</span><span class="sxs-lookup"><span data-stu-id="d0bcc-179">**External DNS:**</span></span>

  - <span data-ttu-id="d0bcc-180">Contiene un'area DNS denominata contoso.com per la quale è autorevole</span><span class="sxs-lookup"><span data-stu-id="d0bcc-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="d0bcc-181">L'area contoso.com esterna contiene:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="d0bcc-182">DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client di Lync Server 2013 (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="d0bcc-183">DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o i record CNAME per l'individuazione automatica dei servizi Web di Lync Server 2013 per l'utilizzo con i dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d0bcc-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="d0bcc-184">DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna perimetrale di ogni Lync Server 2013, server perimetrale o IP virtuale (VIP) del servizio di bilanciamento del carico hardware nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="d0bcc-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="d0bcc-185">DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per l'interfaccia esterna del server proxy inverso o VIP per un pool di server proxy inversi nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="d0bcc-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="d0bcc-186">Configurazione automatica senza DNS split-brain</span><span class="sxs-lookup"><span data-stu-id="d0bcc-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="d0bcc-187">Tramite DNS split-brain, un utente di Lync Server 2013 che accede internamente può usufruire della configurazione automatica se la zona DNS interna contiene una \_sipinternaltls. \_record TCP SRV per ogni dominio SIP in uso.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="d0bcc-188">Tuttavia, se non si utilizza il DNS split-brain, la configurazione automatica interna dei client che eseguono Lync non funzionerà a meno che non venga implementata una delle soluzioni alternative descritte in più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="d0bcc-189">Ciò è dovuto al fatto che Lync Server 2013 richiede l'URI SIP dell'utente in modo che corrisponda al dominio del pool Front End designato per la configurazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="d0bcc-190">Questo è stato anche il caso di versioni precedenti di Communicator.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="d0bcc-191">Se ad esempio si dispone di due domini SIP in uso, sarebbero necessari i record del servizio DNS (SRV) seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="d0bcc-192">Se un utente accede come bob@contoso.com, il record SRV seguente funzionerà per la configurazione automatica perché il dominio SIP dell'utente (contoso.com) corrisponde al dominio del pool di front end di configurazione automatica):</span><span class="sxs-lookup"><span data-stu-id="d0bcc-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="d0bcc-193">\_sipinternaltls. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="d0bcc-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="d0bcc-195">Se un utente accede come alice@fabrikam.com, il record DNS SRV seguente funzionerà per la configurazione automatica del secondo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="d0bcc-196">\_sipinternaltls. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="d0bcc-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="d0bcc-198">Per un confronto, se un utente accede come tim@litwareinc.com, il record SRV DNS seguente non funzionerà per la configurazione automatica, in quanto il dominio SIP del client (litwareinc.com) non corrisponde al dominio in cui si trova il pool (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="d0bcc-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="d0bcc-199">\_sipinternaltls. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="d0bcc-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="d0bcc-201">Se è necessaria la configurazione automatica per i client che eseguono Lync, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="d0bcc-202">**Gli oggetti**   criteri di gruppo utilizzano gli oggetti Criteri di gruppo per popolare i valori del server corretti.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0bcc-203">Questa opzione non Abilita la configurazione automatica, ma consente di automatizzare il processo di configurazione manuale, quindi se si utilizza questo approccio, i record SRV associati alla configurazione automatica non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="d0bcc-204">**Area interna corrispondente**   creare un'area nel DNS interno che corrisponda alla zona DNS esterna (ad esempio, contoso.com) e creare record DNS a e aaaa (se si utilizzano gli indirizzi IPv6) corrispondenti al pool di Lync Server 2013 utilizzato per la configurazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="d0bcc-205">Ad esempio, se un utente è ospitato in pool01.contoso.net, ma accede a Lync come bob@contoso.com, creare una zona DNS interna denominata contoso.com e al suo interno, creare un record DNS A e AAAA (se viene utilizzato IPv6 Addressing) per pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="d0bcc-206">**Area interna del pin-point**   se si sta creando un'intera area nel DNS interno non è un'opzione, è possibile creare zone pin-point, ovvero dedicate, che corrispondono ai record SRV necessari per la configurazione automatica e popolare tali zone tramite Dnscmd. exe.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="d0bcc-207">Dnscmd. exe è necessario perché l'interfaccia utente DNS non supporta la creazione di aree a punti pin.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="d0bcc-208">Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front End denominato Pool01 che contiene due front end server, sono necessarie le seguenti aree di pin-point e un record nel DNS interno:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="d0bcc-209">Se l'ambiente contiene un secondo dominio SIP, ad esempio fabrikam.com, è necessario disporre delle seguenti aree di pin-point e di un record nel DNS interno:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="d0bcc-210">L'FQDN del pool Front end viene visualizzato due volte, ma con due indirizzi IP diversi.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="d0bcc-211">Questo perché viene utilizzato il bilanciamento del carico DNS, ma se viene utilizzato il bilanciamento del carico hardware, è presente una sola voce del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="d0bcc-212">Inoltre, i valori FQDN del pool Front End cambiano tra l'esempio di contoso.com e l'esempio di fabrikam.com, ma gli indirizzi IP rimangono invariati.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="d0bcc-213">Ciò è dovuto al fatto che gli utenti accedono da un dominio SIP o utilizzano lo stesso pool Front end per la configurazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="d0bcc-214">Per informazioni dettagliate, vedere l'articolo del Blog di DMTF, "configurazione automatica di Communicator e DNS split- [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707)Brain" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0bcc-215">Il contenuto di ogni blog e il relativo URL sono soggetti a modifica senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="d0bcc-216">Configurazione del DNS (Domain Name System) per il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="d0bcc-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="d0bcc-217">Per configurare il DNS in modo da reindirizzare il traffico Web di Lync Server 2013 al ripristino di emergenza e ai siti di failover, è necessario utilizzare un provider DNS che supporti GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="d0bcc-218">È possibile configurare i record DNS per il Web per supportare il ripristino di emergenza, in modo che le funzionalità che utilizzano i servizi Web continuino anche se un intero pool Front-end viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="d0bcc-219">Questa funzionalità di ripristino di emergenza supporta gli URL semplici di individuazione automatica (URL Lyncdiscover), riunione e accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="d0bcc-220">È possibile definire e configurare i record host DNS aggiuntivi (A e AAAA se si utilizza IPv6) per la risoluzione interna ed esterna dei servizi Web nel provider di GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="d0bcc-221">Nei dettagli seguenti si presuppone che i pool associati, distribuiti geograficamente e GeoDNS supportati dal provider con DNS round robin, siano configurati per l'utilizzo di pool1 come primari e che non vengano Pool2 in caso di perdita di comunicazioni o di errore hardware.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0bcc-222">Record di GeoDNS (esempio)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="d0bcc-223">Record del pool (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="d0bcc-224">Record CNAME (esempio)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="d0bcc-225">Impostazioni DNS (selezionare un'opzione)</span><span class="sxs-lookup"><span data-stu-id="d0bcc-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0bcc-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-229">Alias di Meet.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-230">Alias di Meet.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-231">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-232">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0bcc-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-236">Alias di Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-237">Alias di Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-238">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-239">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0bcc-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-243">Alias di Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-244">Alias di Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-245">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-246">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0bcc-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-250">Alias di Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-251">Alias di Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-252">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-253">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0bcc-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-257">Alias di Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-258">Alias di Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-259">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-260">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0bcc-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-264">Alias di Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-265">Alias di Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-266">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-267">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0bcc-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-271">Alias di Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-272">Alias di Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-273">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-274">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0bcc-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-278">Alias di Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="d0bcc-279">Alias di Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0bcc-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d0bcc-280">Round Robin tra pool</span><span class="sxs-lookup"><span data-stu-id="d0bcc-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="d0bcc-281">Utilizzo primario, connessione a secondario in caso di errore</span><span class="sxs-lookup"><span data-stu-id="d0bcc-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="d0bcc-282">Bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="d0bcc-282">DNS Load Balancing</span></span>

<span data-ttu-id="d0bcc-283">Il bilanciamento del carico DNS è in genere implementato a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="d0bcc-284">L'applicazione, ad esempio un client che esegue Lync, tenta di connettersi a un server in un pool collegandosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per il nome di dominio completo (FQDN) del pool.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="d0bcc-285">Ad esempio, se sono presenti tre Front End Server in un pool denominato pool01.contoso.com, si verificherà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="d0bcc-286">Client che eseguono Lync query DNS per pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="d0bcc-287">La query restituisce tre indirizzi IP e li memorizza nella cache come indicato di seguito (non necessariamente nell'ordine):</span><span class="sxs-lookup"><span data-stu-id="d0bcc-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="d0bcc-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="d0bcc-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="d0bcc-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="d0bcc-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="d0bcc-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="d0bcc-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="d0bcc-291">Il client tenta di stabilire una connessione TCP (Transmission Control Protocol) a uno degli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="d0bcc-292">In caso di esito negativo, il client tenterà l'indirizzo IP successivo nella cache.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="d0bcc-293">Se la connessione TCP ha esito positivo, il client negozia TLS per la connessione al servizio di registrazione principale su pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="d0bcc-294">Se il client cerca tutte le voci memorizzate nella cache senza una connessione completata, l'utente riceve una notifica che attualmente non sono disponibili server che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0bcc-295">Il bilanciamento del carico basato su DNS è diverso da quello del round robin DNS (RR DNS), che in genere si riferisce al bilanciamento del carico facendo affidamento sul DNS per fornire un diverso ordine di indirizzi IP corrispondenti ai server in un pool.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="d0bcc-296">Tipicamente DNS RR attiva solo la distribuzione del carico, ma non Abilita il failover.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="d0bcc-297">Ad esempio, se la connessione a un indirizzo IP restituito dalla query DNS A e AAAA (se si utilizza l'indirizzamento IPv6) ha esito negativo, la connessione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="d0bcc-298">Pertanto, il round robin DNS è di per sé meno affidabile rispetto al bilanciamento del carico basato su DNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="d0bcc-299">È possibile utilizzare il round robin DNS in combinazione con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="d0bcc-300">Il bilanciamento del carico DNS viene utilizzato per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="d0bcc-301">Bilanciamento del carico del SIP da server a server nei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="d0bcc-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="d0bcc-302">Bilanciamento del carico delle applicazioni unificate (Unified Communications Application Services), ad esempio operatore automatico di conferenza, Response Group e parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="d0bcc-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="d0bcc-303">Impedire nuove connessioni alle applicazioni di unificate (note anche come "drenante")</span><span class="sxs-lookup"><span data-stu-id="d0bcc-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="d0bcc-304">Bilanciamento del carico di tutto il traffico da client a server tra client e server perimetrali</span><span class="sxs-lookup"><span data-stu-id="d0bcc-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="d0bcc-305">Non è possibile utilizzare il bilanciamento del carico DNS per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="d0bcc-306">Traffico Web da client a server a Director o front end server</span><span class="sxs-lookup"><span data-stu-id="d0bcc-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="d0bcc-307">Bilanciamento del carico DNS e traffico federato:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="d0bcc-308">Se più record DNS vengono restituiti da una query DNS SRV, il servizio Access Edge preleva sempre il record DNS SRV con la priorità numerica più bassa e il peso numerico più alto.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="d0bcc-309">Il documento Internet Engineering Task Force "un RR DNS per specificare il percorso dei servizi (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> specifica che, se sono stati definiti più record SRV DNS, la priorità viene utilizzata per la prima volta, quindi peso.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="d0bcc-310">Ad esempio, il record DNS SRV A ha un peso di 20 e la priorità di 40 e il record DNS SRV B ha un peso di 10 e la priorità di 50.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="d0bcc-311">Verrà selezionato il record DNS SRV A con priorità 40.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="d0bcc-312">Le regole seguenti si applicano alla selezione dei record DNS SRV:</span><span class="sxs-lookup"><span data-stu-id="d0bcc-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="d0bcc-313">La priorità viene considerata per prima.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-313">Priority is considered first.</span></span> <span data-ttu-id="d0bcc-314">Un client deve tentare di contattare l'host di destinazione definito dal record SRV DNS con la priorità più bassa numerata che può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="d0bcc-315">Gli obiettivi con la stessa priorità devono essere tentati in base a un ordine definito dal campo Weight.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="d0bcc-316">Il campo Weight specifica un peso relativo per le voci con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="d0bcc-317">I pesi maggiori devono avere una probabilità proporzionalmente più alta di essere selezionati.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="d0bcc-318">Gli amministratori DNS devono utilizzare il peso 0 quando non è presente alcuna selezione del server.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="d0bcc-319">In presenza di record che contengono pesi maggiori di 0, i record con peso 0 devono avere una possibilità molto piccola di essere selezionati.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="d0bcc-320">Se vengono restituiti più record SRV DNS con priorità e peso uguali, il servizio Access Edge selezionerà il record SRV ricevuto per primo dal server DNS.</span><span class="sxs-lookup"><span data-stu-id="d0bcc-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

