---
title: "Lync Server 2013: configurazione del DNS per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="f7783-102">Configurazione del DNS per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7783-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7783-103">_**Argomento Ultima modifica:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="f7783-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="f7783-104">Per supportare l'individuazione automatica per i client Lync, è necessario creare i seguenti record DNS (Domain Name System):</span><span class="sxs-lookup"><span data-stu-id="f7783-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="f7783-105">Record DNS interno per supportare i client Lync che si connettono dall'interno della rete dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f7783-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="f7783-106">Record DNS esterno o pubblico per supportare i client Lync che si connettono da Internet</span><span class="sxs-lookup"><span data-stu-id="f7783-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="f7783-107">È necessario creare un record DNS interno e un record DNS esterno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="f7783-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="f7783-108">I record DNS possono essere un record (host) o un record CNAME, in base alla possibilità di creare nuovi certificati con il nome alternativo soggetto aggiuntivo (SAN).</span><span class="sxs-lookup"><span data-stu-id="f7783-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="f7783-109">Se non è possibile richiedere e distribuire un nuovo certificato esterno (pubblico) con lyncdiscover. \<San nome\> di dominio, usare la procedura per l'uso della porta HTTP/TCP 80.</span><span class="sxs-lookup"><span data-stu-id="f7783-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="f7783-110">Le procedure seguenti descrivono come creare record DNS interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="f7783-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="f7783-111">Per creare record CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="f7783-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="f7783-112">Accedere a un server DNS come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="f7783-113">Per creare un record DNS interno, accedere a un server DNS della rete come membro del gruppo Domain Admins o membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f7783-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="f7783-114">Per creare un record DNS esterno, connettersi al provider DNS pubblico.</span><span class="sxs-lookup"><span data-stu-id="f7783-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="f7783-115">Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f7783-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="f7783-116">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7783-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="f7783-117">Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory, ad esempio contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f7783-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f7783-118">Questo dominio è il dominio Active Directory in cui sono installati il&nbsp;pool di Lync Server 2013 Director e il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="f7783-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="f7783-119">Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="f7783-120">Verificare che per il pool di Director sia presente un record di un host, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="f7783-121">Per un record DNS interno, deve esistere un record per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f7783-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="f7783-122">Per un record DNS esterno, deve esistere un record per l'FQDN dei servizi Web esterni per il pool di Director, ad esempio lyncwebextdir.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="f7783-123">Verificare che per il pool Front-end sia presente un record di un host, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="f7783-124">Per un record DNS interno, deve esistere un record per l'FQDN dei servizi Web interni per il pool Front-End, ad esempio lyncwebpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f7783-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="f7783-125">Per un record DNS esterno, deve esistere un record per l'FQDN dei servizi Web esterni per il pool Front-End, ad esempio lyncwebextpool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="f7783-126">Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7783-127">Se si sta creando un record DNS esterno, le <STRONG>aree di ricerca inoltrate</STRONG> sono già espanse per il dominio SIP dal passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="f7783-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="f7783-128">Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="f7783-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="f7783-129">In **nome alias**Digitare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7783-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="f7783-130">Per un record DNS interno, digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="f7783-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="f7783-131">Per un record DNS esterno, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="f7783-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="f7783-132">In **nome di dominio completo (FQDN) per l'host di destinazione**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7783-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="f7783-133">Per un record DNS interno, digitare o passare all'FQDN dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7783-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="f7783-134">Per un record DNS esterno, digitare o passare all'FQDN dei servizi Web esterni per il pool di Director, ad esempio lyncwebextdir.contoso.com, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7783-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7783-135">Se non si usa un amministratore, usare il nome di dominio completo dei servizi Web interni ed esterni per il pool Front-end oppure, per un singolo server, il nome di dominio completo per il server front-end o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f7783-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f7783-136">È necessario creare un nuovo record CNAME di individuazione automatica nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7783-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="f7783-137">Per creare record DNS</span><span class="sxs-lookup"><span data-stu-id="f7783-137">To create DNS A records</span></span>

1.  <span data-ttu-id="f7783-138">Accedere a un server DNS come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="f7783-139">Per creare un record DNS interno, accedere a un server DNS della rete come membro del gruppo Domain Admins o membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f7783-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="f7783-140">Per creare un record DNS esterno, connettersi al provider DNS pubblico o al server DNS esterno.</span><span class="sxs-lookup"><span data-stu-id="f7783-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="f7783-141">Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f7783-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="f7783-142">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7783-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="f7783-143">Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory, ad esempio contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f7783-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f7783-144">Questo dominio è il dominio Active Directory in cui sono installati il&nbsp;pool di Lync Server 2013 Director e il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="f7783-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="f7783-145">Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="f7783-146">Verificare che esista un record host A (per IPv6, AAAA) per il pool di Director come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="f7783-147">Per un record DNS interno, deve esistere un record host A (per IPv6, AAAA) per il nome di dominio completo dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f7783-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="f7783-148">Per un record DNS esterno, deve esistere un record host A (per IPv6, AAAA) per il nome di dominio completo dei servizi Web esterni per il pool di Director (ad esempio, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f7783-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="f7783-149">Verificare che sia presente un record host A (per IPv6, AAAA) per il pool Front-End, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="f7783-150">Per un record DNS interno, deve esistere un record host A (per IPv6, AAAA) per l'FQDN dei servizi Web interni per il pool Front-End, ad esempio lyncwebpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="f7783-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="f7783-151">Per un record DNS esterno, deve esistere un record host A (per IPv6, AAAA) per il nome di dominio completo dei servizi Web esterni per il pool Front-End, ad esempio lyncwebextpool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="f7783-152">Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f7783-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7783-153">Se si sta creando un record DNS esterno, le <STRONG>aree di ricerca inoltrate</STRONG> sono già espanse per il dominio SIP dal passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="f7783-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="f7783-154">Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="f7783-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="f7783-155">In **nome**Digitare il nome dell'host come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="f7783-156">Per un record DNS interno, digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="f7783-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="f7783-157">Per un record DNS esterno, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="f7783-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7783-158">Il nome di dominio viene considerato dalla zona in cui è definito il record e, pertanto, non deve essere immesso come parte del record A.</span><span class="sxs-lookup"><span data-stu-id="f7783-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="f7783-159">In **indirizzo IP**Digitare l'indirizzo IP come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7783-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="f7783-160">Per un record DNS interno, digitare l'indirizzo IP dei servizi Web interni del Director oppure, se si usa un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del bilanciamento del carico di Director.</span><span class="sxs-lookup"><span data-stu-id="f7783-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f7783-161">Se non si usa un amministratore, digitare l'indirizzo IP del server front-end o Standard Edition oppure, se si usa un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="f7783-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="f7783-162">Per un record DNS esterno, digitare l'indirizzo IP esterno o pubblico del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f7783-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="f7783-163">Fare clic su **Aggiungi host**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7783-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="f7783-164">Per creare un record aggiuntivo, ripetere i passaggi da 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="f7783-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f7783-165">È necessario creare un nuovo Lyncdiscover e lyncdiscoverinternal un record nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7783-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="f7783-166">Al termine della creazione di un record (per IPv6, AAAA), fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f7783-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

