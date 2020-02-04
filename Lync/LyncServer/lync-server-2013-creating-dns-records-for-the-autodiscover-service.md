---
title: 'Lync Server 2013: Creazione di record DNS per il servizio di individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d91c67620a87fdd91a1755592175e8cf2964d259
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="52a1a-102">Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52a1a-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52a1a-103">_**Argomento Ultima modifica:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="52a1a-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="52a1a-104">Gli utenti di Lync mobile dovranno abilitare l'individuazione automatica e parte della creazione di alcuni record DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="52a1a-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="52a1a-105">A seconda delle esigenze, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="52a1a-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="52a1a-106">Un record DNS interno che supporta gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52a1a-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="52a1a-107">Un record DNS esterno o pubblico per supportare gli utenti di dispositivi mobili che si connettono da Internet</span><span class="sxs-lookup"><span data-stu-id="52a1a-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="52a1a-108">Perché entrambi?</span><span class="sxs-lookup"><span data-stu-id="52a1a-108">Why both?</span></span> <span data-ttu-id="52a1a-109">È necessario creare sia un record DNS interno che un record DNS esterno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="52a1a-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="52a1a-110">I record DNS creati possono essere un record (host) o un record CNAME.</span><span class="sxs-lookup"><span data-stu-id="52a1a-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="52a1a-111">Per semplificare la creazione di questi record DNS interni ed esterni, è possibile procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="52a1a-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="52a1a-112">Per altre informazioni sui requisiti DNS per gli utenti di dispositivi mobili, è possibile consultare i [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="52a1a-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="52a1a-113">Creazione di un record CNAME DNS interno</span><span class="sxs-lookup"><span data-stu-id="52a1a-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="52a1a-114">Per creare un record DNS interno, è necessario accedere a un server DNS della rete con un account di dominio che sia un membro del gruppo Domain Admins o un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="52a1a-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="52a1a-115">Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="52a1a-116">Nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory in cui sono installati il pool di Lync Server 2013 Director e il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="52a1a-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="52a1a-117">(ad esempio, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="52a1a-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="52a1a-118">Verificare se per il pool di Director è presente un record host (AAAA per IPv6) per un record DNS interno, è necessario che sia presente un record per il nome di dominio completo dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="52a1a-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="52a1a-119">Se non è presente, è possibile che non si stia usando un pool di Director e che sia necessario usare il nome di dominio completo per il pool di front end o anche un FQDN di un singolo server, se questa è la configurazione.</span><span class="sxs-lookup"><span data-stu-id="52a1a-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="52a1a-120">Tenendo presente questo aspetto, verificare se per il pool di front end esiste un record (AAAA per IPv6) ospitante per un record DNS interno, deve esistere un record host A (o AAAA) per il nome di dominio completo dei servizi Web interni per il pool di front-end, ad esempio , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="52a1a-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="52a1a-121">In caso contrario, è necessario prendere nota del nome di dominio completo per il server front-end o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="52a1a-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="52a1a-122">Una volta che si sa quali sono i record host A (o AAAA), nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52a1a-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="52a1a-123">Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="52a1a-124">In **nome alias**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="52a1a-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="52a1a-125">In **nome di dominio completo (FQDN) per l'host di destinazione**Digitare o passare all'FQDN dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="52a1a-126">È necessario creare un nuovo record CNAME di individuazione automatica nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52a1a-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="52a1a-127">Creazione di un record CNAME DNS esterno</span><span class="sxs-lookup"><span data-stu-id="52a1a-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="52a1a-128">Per creare un record CNAME DNS esterno, è necessario connettersi al provider DNS pubblico e seguire i passaggi descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="52a1a-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="52a1a-129">Non è possibile descrivere esattamente il punto in cui ci si trova nell'ambiente del provider DNS perché potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma ci auguriamo che questi passaggi siano utili.</span><span class="sxs-lookup"><span data-stu-id="52a1a-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="52a1a-130">Accedere al provider DNS esterno con un account che può creare record DNS in tale ambiente.</span><span class="sxs-lookup"><span data-stu-id="52a1a-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="52a1a-131">Dovresti avere già un dominio SIP creato per questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="52a1a-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="52a1a-132">Espandi l' **area di ricerca diretta** per il dominio SIP oppure selezionala in base all'interfaccia DNS esterna in uso.</span><span class="sxs-lookup"><span data-stu-id="52a1a-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="52a1a-133">Si dovrebbe già vedere un record host (AAAA per IPv6) per il pool di Director (ad esempio lyncwebexdir01.contoso.com), quindi verificare che sia presente.</span><span class="sxs-lookup"><span data-stu-id="52a1a-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="52a1a-134">In caso contrario, potresti non usare un pool di Director.</span><span class="sxs-lookup"><span data-stu-id="52a1a-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="52a1a-135">In questo caso, è necessario usare il nome di dominio completo del pool Front-end oppure, se si esegue questa operazione per un singolo server, per il server front-end o per il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="52a1a-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="52a1a-136">Sarà inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool di front-end (ad esempio lyncwebextpool01.contoso.com) o un nome di dominio completo per il nome di dominio completo del server singolo se non si dispone di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="52a1a-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="52a1a-137">Come indicato nel passaggio precedente, se non si dispone di un pool di Director, sarà necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="52a1a-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="52a1a-138">A questo punto, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo alias (CNAME)** , che può essere un'opzione di menu o un collegamento, a seconda del formato del provider DNS.</span><span class="sxs-lookup"><span data-stu-id="52a1a-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="52a1a-139">Dovrebbe essere presente una qualche forma di casella di testo **nome alias** con il DNS interno, devi immettere Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterna.</span><span class="sxs-lookup"><span data-stu-id="52a1a-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="52a1a-140">Dovrebbe essere disponibile anche una forma di un **nome di dominio completo (FQDN) per** la casella di testo host di destinazione, ecco dove si immetterà l'FQDN dei servizi Web esterni per il pool di Director (ad esempio, lyncwebexdir01.contoso.com) e quindi fare clic su OK o su qualsiasi azione nel DNS esterno per accettare la creazione di questa voce.</span><span class="sxs-lookup"><span data-stu-id="52a1a-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="52a1a-141">Come indicato nel passaggio 4, in precedenza, se non si dispone di un pool di Director, sarà necessario usare il nome di dominio completo del pool di front end o il nome di dominio completo a server singolo configurato, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="52a1a-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="52a1a-142">È necessario creare un nuovo record CNAME di individuazione automatica nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="52a1a-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="52a1a-143">Creazione di un record DNS interno</span><span class="sxs-lookup"><span data-stu-id="52a1a-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="52a1a-144">Per creare un record DNS interno, accedere a un server DNS della rete con un account di dominio membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="52a1a-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="52a1a-145">Aprire lo snap-in di amministrazione DNS: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="52a1a-146">Per un record DNS interno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio Active Directory, ad esempio contoso. local, in cui sono installati il pool di Lync Server 2013 Director e il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="52a1a-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="52a1a-147">Verificare se per il pool di Director è presente un record host (AAAA per IPv6) per un record DNS interno, è necessario che sia presente un record per il nome di dominio completo dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="52a1a-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="52a1a-148">Se non è presente, è possibile che non si usi un pool di Director e che sia necessario usare l'indirizzo IP per il pool Front-end o anche un singolo indirizzo IP del server, se questa è la configurazione.</span><span class="sxs-lookup"><span data-stu-id="52a1a-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="52a1a-149">Tenendo presente questo aspetto, verificare se per il pool di front end esiste un record (AAAA per IPv6) ospitante per un record DNS interno, deve esistere un record host A (o AAAA) per il nome di dominio completo dei servizi Web interni per il pool di front-end, ad esempio , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="52a1a-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="52a1a-150">In caso contrario, è necessario prendere nota dell'indirizzo IP per il server front-end o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="52a1a-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="52a1a-151">Una volta che si sa quali sono i record host A (o AAAA), nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52a1a-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="52a1a-152">Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="52a1a-153">In **nome**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="52a1a-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="52a1a-154">In **indirizzo IP**Digitare l'indirizzo IP dei servizi Web interni del Director (oppure, se si usa un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del bilanciamento del carico del direttore).</span><span class="sxs-lookup"><span data-stu-id="52a1a-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="52a1a-155">Come indicato nel passaggio 4, se non si usa un Director, potrebbe essere necessario immettere l'indirizzo IP del server front-end o Standard Edition oppure, se si usa un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="52a1a-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="52a1a-156">Fare clic su **Aggiungi host**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="52a1a-157">Per creare un record A o AAAA aggiuntivo, ripetere i passaggi da 8 a 10, tenendo presente che è necessario creare nuovi record di individuazione automatica a o AAAA nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52a1a-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="52a1a-158">Al termine della creazione di un record (per IPv6, AAAA), fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="52a1a-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="52a1a-159">Creazione di un record DNS esterno</span><span class="sxs-lookup"><span data-stu-id="52a1a-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="52a1a-160">Per creare un record DNS esterno, connettersi al provider DNS pubblico e seguire i passaggi.</span><span class="sxs-lookup"><span data-stu-id="52a1a-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="52a1a-161">Non è possibile descrivere esattamente il punto in cui ci si trova nell'ambiente del provider DNS perché potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma ci auguriamo che questi passaggi siano utili.</span><span class="sxs-lookup"><span data-stu-id="52a1a-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="52a1a-162">È necessario avere effettuato l'accesso come account che può creare record DNS in quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="52a1a-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="52a1a-163">Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52a1a-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="52a1a-164">Per un record DNS esterno, nell'albero della console del server DNS espandere le **aree di ricerca in avanti** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52a1a-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="52a1a-165">Si dovrebbe già vedere un record host (AAAA per IPv6) per il pool di Director (ad esempio lyncwebexdir01.contoso.com), quindi verificare che sia presente e quale sia l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="52a1a-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="52a1a-166">In caso contrario, potresti non usare un pool di Director.</span><span class="sxs-lookup"><span data-stu-id="52a1a-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="52a1a-167">In questo caso, è necessario usare l'indirizzo IP del pool Front-end oppure, se si esegue questa operazione per un singolo server, per il server front-end o per il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="52a1a-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="52a1a-168">Tieni presente che i server potrebbero essere anche dietro a un dispositivo di bilanciamento del carico oppure usando un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="52a1a-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="52a1a-169">Prendere nota degli indirizzi IP anche per seguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="52a1a-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="52a1a-170">È inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool di front end (ad esempio lyncwebextpool01.contoso.com) o un indirizzo IP per l'installazione di Lync a server singolo se si non hanno pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="52a1a-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="52a1a-171">Come indicato nel passaggio precedente, se non si dispone di un pool di Director, sarà necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="52a1a-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="52a1a-172">Ora, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo host a o AAAA** (può trattarsi di un'opzione di menu o di un collegamento, a seconda del formato del provider DNS).</span><span class="sxs-lookup"><span data-stu-id="52a1a-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="52a1a-173">Dovrebbe essere disponibile una posizione in cui immettere un **nome**, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="52a1a-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="52a1a-174">Dovrebbe essere anche disponibile una casella di testo per l' **indirizzo IP** , che consente di immettere l'IP per il pool di Director (ad esempio, lyncwebexdir01.contoso.com) o eventualmente per l'IP del servizio di bilanciamento del carico del pool (o di un IP proxy inverso che conduce allo stesso), quindi fare clic su OK o eseguire qualsiasi azione nel DNS esterno per accettare la creazione di questa voce.</span><span class="sxs-lookup"><span data-stu-id="52a1a-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="52a1a-175">Come indicato nel passaggio 4, in precedenza, se non si dispone di un pool di Director, è necessario usare l'indirizzo IP del pool Front-end o l'indirizzo IP a server singolo configurato, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="52a1a-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="52a1a-176">È necessario creare un nuovo record di individuazione automatica a o AAAA nell'area di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="52a1a-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

