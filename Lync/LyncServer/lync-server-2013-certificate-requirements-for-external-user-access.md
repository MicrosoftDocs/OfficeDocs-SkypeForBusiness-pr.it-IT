---
title: "Lync Server 2013: requisiti dei certificati per l'accesso degli utenti esterni"
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
ms.openlocfilehash: 37494b3f8389709681ffc92a17d388b71baddd70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517953"
---
# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="e0671-102">Requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0671-102">Certificate requirements for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0671-103">_**Ultimo argomento modificato:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="e0671-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="e0671-104">Il software di comunicazione Microsoft Lync Server 2013 supporta l'utilizzo di un singolo certificato pubblico per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione A/V.</span><span class="sxs-lookup"><span data-stu-id="e0671-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="e0671-105">L'interfaccia interna perimetrale utilizza in genere un certificato privato emesso da un'autorità di certificazione (CA) interna, ma può anche utilizzare un certificato pubblico, purché provenga da una CA pubblica attendibile.</span><span class="sxs-lookup"><span data-stu-id="e0671-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="e0671-106">Il proxy inverso della distribuzione utilizza un certificato pubblico e crittografa le comunicazioni dal proxy inverso ai client e dal proxy inverso ai server interni mediante HTTP, ovvero Transport Layer Security su HTTP.</span><span class="sxs-lookup"><span data-stu-id="e0671-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="e0671-107">Di seguito sono riportati i requisiti dei certificati pubblici utilizzati per le interfacce esterne dell'Access Edge Server e del Web Conferencing Edge Server, nonché per il servizio di autenticazione A/V:</span><span class="sxs-lookup"><span data-stu-id="e0671-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="e0671-108">Il certificato deve essere emesso da una CA pubblica approvata che supporta il nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="e0671-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="e0671-109">Per informazioni dettagliate, vedere l'articolo 929395 della Microsoft Knowledge Base "partner di certificati per comunicazioni unificate per Exchange Server e per Communications Server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="e0671-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="e0671-p103">Se il certificato verrà utilizzato in un pool di server perimetrali, deve essere creato come esportabile, con lo stesso certificato utilizzato in ogni server perimetrale del pool. Il requisito della chiave privata esportabile è previsto per il servizio di autenticazione A/V, che deve utilizzare la stessa chiave privata in tutti i server perimetrali del pool.</span><span class="sxs-lookup"><span data-stu-id="e0671-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="e0671-112">Se si desidera massimizzare il tempo di ingrandimento per i servizi audio/video, esaminare i requisiti dei certificati per l'implementazione di un certificato del servizio A/V Edge separato, ovvero un certificato del servizio A/V Edge A parte di altri scopi del certificato esterno.</span><span class="sxs-lookup"><span data-stu-id="e0671-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="e0671-113">Per informazioni dettagliate, vedere [changes in Lync server 2013 che influiscono sulla pianificazione del server perimetrale](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [pianificare i certificati server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e la [gestione temporanea dei certificati AV e OAuth in Lync Server 2013 utilizzando-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="e0671-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="e0671-114">Il nome del soggetto del certificato è l'interfaccia esterna del servizio Access Edge completo (FQDN) o il VIP del dispositivo di bilanciamento del carico hardware (ad esempio, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e0671-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="e0671-115">).</span><span class="sxs-lookup"><span data-stu-id="e0671-115">).</span></span> <span data-ttu-id="e0671-116">Il nome del soggetto non può avere un carattere jolly, deve essere un nome esplicito.</span><span class="sxs-lookup"><span data-stu-id="e0671-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0671-117">Per Lync Server 2013, questo non è più un requisito, ma è comunque consigliato per la compatibilità con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="e0671-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="e0671-118">L'elenco di nomi alternativi del soggetto contiene i nomi FQDN dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0671-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="e0671-119">L'interfaccia esterna del servizio Access Edge o il VIP del dispositivo di bilanciamento del carico hardware (ad esempio, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e0671-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e0671-120">Anche se il nome del soggetto del certificato è uguale al nome FQDN dell'Access Edge Server, deve contenere anche questo FQDN perché Transport Layer Security (TLS) ignora il nome del soggetto e utilizza le voci dei nomi alternativi del soggetto per la convalida.</span><span class="sxs-lookup"><span data-stu-id="e0671-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="e0671-121">L'interfaccia esterna del Web Conferencing Edge Server o il VIP del dispositivo di bilanciamento del carico hardware, ad esempio webcon.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e0671-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="e0671-122">Se si utilizza la configurazione automatica dei client o la federazione, includere anche eventuali FQDN di dominio SIP utilizzati all'interno dell'organizzazione, ad esempio sip.contoso.com, sip.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="e0671-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="e0671-123">Il servizio A/V Edge non utilizza le voci Subject Name o Subject Alternative names.</span><span class="sxs-lookup"><span data-stu-id="e0671-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0671-124">L'ordine dei nomi FQDN nell'elenco di nomi alternativi del soggetto non è importante.</span><span class="sxs-lookup"><span data-stu-id="e0671-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="e0671-p106">Se si distribuiscono più server perimetrali con bilanciamento del carico in un sito, il certificato del servizio di autenticazione A/V installato in ogni server perimetrale deve provenire dalla stessa CA e deve utilizzare la stessa chiave privata. Si noti che la chiave privata del certificato deve essere esportabile, indipendentemente dal fatto che venga utilizzata in uno o in più server perimetrali. Deve essere esportabile anche se il certificato viene richiesto da qualsiasi altro computer diverso dal server perimetrale. Poiché il servizio di autenticazione A/V non utilizza il nome del soggetto o il nome alternativo del soggetto, è possibile riutilizzare il certificato dell'Access Edge Server, purché vengano soddisfatti i requisiti del nome del soggetto e del nome alternativo del soggetto per l'Access Edge Server e il Web Conferencing Edge Server e la chiave privata del certificato sia esportabile.</span><span class="sxs-lookup"><span data-stu-id="e0671-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="e0671-129">I requisiti per il certificato privato (o pubblico) utilizzato per l'interfaccia interna del server perimetrale sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0671-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="e0671-130">Il certificato può essere emesso da una CA interna o da una CA pubblica approvata.</span><span class="sxs-lookup"><span data-stu-id="e0671-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="e0671-p107">Il nome del soggetto del certificato corrisponde in genere al nome FQDN dell'interfaccia interna perimetrale o al VIP del servizio di bilanciamento del carico hardware, ad esempio lsedge.contoso.com. È tuttavia possibile utilizzare anche un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="e0671-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="e0671-133">Non è richiesto alcun elenco di nomi alternativi del soggetto.</span><span class="sxs-lookup"><span data-stu-id="e0671-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="e0671-134">Il proxy inverso dei servizi di distribuzione richiede:</span><span class="sxs-lookup"><span data-stu-id="e0671-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="e0671-135">Accesso di utenti esterni al contenuto delle riunioni</span><span class="sxs-lookup"><span data-stu-id="e0671-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="e0671-136">Accesso di utenti esterni per espandere e visualizzare i membri di gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e0671-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="e0671-137">Accesso di utenti esterni a file scaricabili dal servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="e0671-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="e0671-138">Accesso degli utenti esterni al client Lync Web App</span><span class="sxs-lookup"><span data-stu-id="e0671-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="e0671-139">Accesso di utenti esterni alla pagina Web Impostazioni conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="e0671-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="e0671-140">Accesso di utenti esterni al servizio Informazioni percorso</span><span class="sxs-lookup"><span data-stu-id="e0671-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="e0671-141">Accesso di utenti esterni al servizio Aggiornamento dispositivo e recupero di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e0671-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="e0671-142">Il proxy inverso pubblica gli URL dei componenti Web del server interno.</span><span class="sxs-lookup"><span data-stu-id="e0671-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="e0671-143">Gli URL dei componenti Web sono definiti in Director, Front End Server o pool Front end come **servizi Web esterni** in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e0671-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="e0671-144">Le voci con caratteri jolly sono supportate nel campo del nome alternativo del soggetto del certificato assegnato al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="e0671-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="e0671-145">Per informazioni dettagliate su come configurare la richiesta di certificato per il proxy inverso, vedere [request and Configure a certificate for your inverse http proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="e0671-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e0671-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0671-146">See Also</span></span>


[<span data-ttu-id="e0671-147">Supporto per i certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0671-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

