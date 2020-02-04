---
title: "Lync Server 2013: Requisiti dei certificati per l'accesso utente esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="32224-102">Requisiti dei certificati per l'accesso utente esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32224-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32224-103">_**Argomento Ultima modifica:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="32224-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="32224-104">Il software di comunicazione di Microsoft Lync Server 2013 supporta l'uso di un unico certificato pubblico per le interfacce esterne Edge di Access e Web Conferencing, oltre al servizio di autenticazione A/V.</span><span class="sxs-lookup"><span data-stu-id="32224-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="32224-105">L'interfaccia interna di Edge in genere usa un certificato privato emesso da un'autorità di certificazione interna (CA), ma può anche usare un certificato pubblico, purché si trovi in una CA pubblica attendibile.</span><span class="sxs-lookup"><span data-stu-id="32224-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="32224-106">Il proxy inverso nella distribuzione usa un certificato pubblico e crittografa la comunicazione dal proxy inverso ai client e il proxy inverso ai server interni tramite HTTP (ovvero, Transport Layer Security su HTTP).</span><span class="sxs-lookup"><span data-stu-id="32224-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="32224-107">Di seguito sono riportati i requisiti per il certificato pubblico usato per le interfacce esterne Edge di Access e Web Conferencing e il servizio di autenticazione A/V:</span><span class="sxs-lookup"><span data-stu-id="32224-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="32224-108">Il certificato deve essere emesso da un'autorità di certificazione pubblica approvata che supporta il nome alternativo soggetto.</span><span class="sxs-lookup"><span data-stu-id="32224-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="32224-109">Per informazioni dettagliate, vedere l'articolo 929395 della Microsoft Knowledge Base "partner per i certificati delle comunicazioni unificate per Exchange Server e per [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Communications Server".</span><span class="sxs-lookup"><span data-stu-id="32224-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="32224-110">Se il certificato verrà usato in un pool di Edge, deve essere creato come esportabile, con lo stesso certificato usato in ogni Edge Server nel pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="32224-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="32224-111">Il requisito della chiave privata esportabile è per gli scopi del servizio di autenticazione A/V, che deve usare la stessa chiave privata in tutti i server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="32224-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="32224-112">Se si vuole massimizzare l'uptime per i servizi audio/video, esaminare i requisiti di certificato per l'implementazione di un certificato di servizio A/V Edge disaccoppiato, ovvero un certificato di servizio A/V Edge separato dagli altri scopi del certificato esterno.</span><span class="sxs-lookup"><span data-stu-id="32224-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="32224-113">Per informazioni dettagliate, vedere [le modifiche apportate a Lync server 2013 che influiscono sulla pianificazione di Edge Server](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [pianificare i certificati Edge Server in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e la [gestione dei certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="32224-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="32224-114">Il nome dell'oggetto del certificato è l'interfaccia esterna del servizio di Access Edge Fully Qualified Domain Name (FQDN) o il bilanciamento del carico hardware VIP (ad esempio, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="32224-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="32224-115">).</span><span class="sxs-lookup"><span data-stu-id="32224-115">).</span></span> <span data-ttu-id="32224-116">Il nome soggetto non può avere un carattere jolly, ma deve essere un nome esplicito.</span><span class="sxs-lookup"><span data-stu-id="32224-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32224-117">Per Lync Server 2013, questo non è più un requisito, ma è comunque consigliato per la compatibilità con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="32224-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="32224-118">L'elenco nome alternativo oggetto contiene gli FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="32224-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="32224-119">Interfaccia esterna o servizio di bilanciamento del carico hardware VIP di Access Edge (ad esempio, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="32224-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="32224-120">Anche se il nome del soggetto del certificato è uguale all'FQDN di Access Edge, il nome dell'oggetto alternativo deve contenere anche il nome di dominio completo di Access Edge, perché Transport Layer Security (TLS) ignora i nomi dei soggetti e usa le voci alternative per il nome del soggetto convalida.</span><span class="sxs-lookup"><span data-stu-id="32224-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="32224-121">Interfaccia esterna di Web Conferencing Edge o VIP di bilanciamento del carico hardware (ad esempio, webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="32224-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="32224-122">Se si usa la configurazione automatica client o la Federazione, includere anche gli FQDN di dominio SIP usati all'interno della società, ad esempio sip.contoso.com, sip.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="32224-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="32224-123">Il servizio A/V Edge non usa il nome del soggetto o le voci alternative oggetto.</span><span class="sxs-lookup"><span data-stu-id="32224-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32224-124">L'ordine degli FQDN nell'elenco nomi alternativi oggetto non ha importanza.</span><span class="sxs-lookup"><span data-stu-id="32224-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="32224-125">Se si distribuiscono più server Edge con bilanciamento del carico in un sito, il certificato del servizio di autenticazione A/V installato in ogni server perimetrale deve essere della stessa autorità di certificazione e deve usare la stessa chiave privata.</span><span class="sxs-lookup"><span data-stu-id="32224-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="32224-126">Tieni presente che la chiave privata del certificato deve essere esportabile, indipendentemente dal fatto che venga usata in un server perimetrale o in molti server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="32224-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="32224-127">Deve anche essere esportabile se Richiedi il certificato da qualsiasi computer diverso da Edge Server.</span><span class="sxs-lookup"><span data-stu-id="32224-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="32224-128">Poiché il servizio di autenticazione A/V non usa il nome dell'oggetto o il nome alternativo dell'oggetto, è possibile riutilizzare il certificato di Access Edge purché vengano soddisfatti i requisiti per il nome dell'oggetto e l'oggetto alternativo per il bordo di accesso e il Web Conferencing Edge e la chiave privata del certificato sia esportabile.</span><span class="sxs-lookup"><span data-stu-id="32224-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="32224-129">I requisiti per il certificato privato (o pubblico) usato per l'interfaccia interna del bordo sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="32224-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="32224-130">Il certificato può essere emesso da una CA interna o da una CA di un certificato pubblico approvato.</span><span class="sxs-lookup"><span data-stu-id="32224-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="32224-131">Il nome dell'oggetto del certificato è in genere l'FQDN dell'interfaccia interna del bordo o del bilanciamento del carico hardware VIP (ad esempio, lsedge.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="32224-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="32224-132">Tuttavia, puoi usare un certificato con carattere jolly sul bordo interno.</span><span class="sxs-lookup"><span data-stu-id="32224-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="32224-133">Nessun elenco di nomi alternativi soggetto è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="32224-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="32224-134">Proxy inverso nelle richieste di servizi di distribuzione per:</span><span class="sxs-lookup"><span data-stu-id="32224-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="32224-135">Accesso degli utenti esterni al contenuto della riunione per le riunioni</span><span class="sxs-lookup"><span data-stu-id="32224-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="32224-136">Accesso degli utenti esterni per espandere e visualizzare i membri dei gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="32224-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="32224-137">Accesso degli utenti esterni ai file scaricabili dal servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="32224-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="32224-138">Accesso degli utenti esterni al client Lync Web App</span><span class="sxs-lookup"><span data-stu-id="32224-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="32224-139">Accesso degli utenti esterni alla pagina Web delle impostazioni dei servizi di conferenza telefonica con chiamata in ingresso</span><span class="sxs-lookup"><span data-stu-id="32224-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="32224-140">Accesso degli utenti esterni al servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="32224-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="32224-141">Accesso al dispositivo esterno al servizio di aggiornamento del dispositivo e ottenere gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="32224-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="32224-142">Il proxy inverso pubblica gli URL dei componenti Web di server interni.</span><span class="sxs-lookup"><span data-stu-id="32224-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="32224-143">Gli URL dei componenti Web sono definiti in Director, Front End Server o front end pool come **servizi Web esterni** in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="32224-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="32224-144">Le voci con caratteri jolly sono supportate nel campo nome alternativo oggetto del certificato assegnato al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="32224-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="32224-145">Per informazioni dettagliate su come configurare la richiesta di certificato per il proxy inverso, vedere [richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="32224-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="32224-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32224-146">See Also</span></span>


[<span data-ttu-id="32224-147">Supporto dei certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32224-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

