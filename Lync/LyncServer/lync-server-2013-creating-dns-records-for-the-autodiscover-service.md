---
title: 'Lync Server 2013: creazione di record DNS per il servizio di individuazione automatica'
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
ms.openlocfilehash: 928de572305cdbe19f5222f34e6616a8022e37b3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531543"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="a8cb1-102">Creazione di record DNS per il servizio di individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8cb1-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8cb1-103">_**Ultimo argomento modificato:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="a8cb1-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="a8cb1-104">Gli utenti di Lync mobile avranno bisogno di abilitare l'individuazione automatica e una parte di esso implica la creazione di alcuni record DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="a8cb1-105">In base alle proprie esigenze, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a8cb1-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="a8cb1-106">Un record DNS interno per supportare gli utenti mobili che si connettono dall'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="a8cb1-107">Un record DNS esterno, o pubblico, per supportare gli utenti di dispositivi mobili che si connettono da Internet</span><span class="sxs-lookup"><span data-stu-id="a8cb1-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="a8cb1-108">Perché entrambi?</span><span class="sxs-lookup"><span data-stu-id="a8cb1-108">Why both?</span></span> <span data-ttu-id="a8cb1-109">È necessario creare sia un record DNS interno che un record DNS esterno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="a8cb1-110">I record DNS creati possono essere record A (host) o CNAME.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="a8cb1-111">Per ottenere assistenza, è possibile procedere come creare questi record DNS interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="a8cb1-112">Per ulteriori informazioni sui requisiti DNS per gli utenti mobili, è possibile consultare i [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="a8cb1-113">Creazione di un record CNAME DNS interno</span><span class="sxs-lookup"><span data-stu-id="a8cb1-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="a8cb1-114">Per creare un record DNS interno, è necessario eseguire l'accesso a un server DNS della rete con un account di dominio che sia un membro del gruppo Domain Admins o un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="a8cb1-115">Aprire lo snap-in amministrativo DNS. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="a8cb1-116">Nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio Active Directory in cui sono installati il pool di 2013 server Director e il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="a8cb1-117">(ad esempio, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="a8cb1-118">Controllare e vedere se esiste un record host A (AAAA per IPv6) per il pool di server Director per un record DNS interno, deve esistere un record host a per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="a8cb1-119">Se non è presente, è possibile che non si utilizzi un pool di server Director e che sia necessario utilizzare il nome di dominio completo del pool Front end o persino un FQDN di un singolo computer, se questa è la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="a8cb1-120">Tenendo presente questo avviso, verificare se esiste un record host A (AAAA per IPv6) per il pool Front end per un record DNS interno, deve esistere un record host A (o AAAA) per l'FQDN dei servizi Web interni per il pool Front End, ad esempio lyncwebpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="a8cb1-121">In caso contrario, è necessario prendere nota del nome di dominio completo del server front end server o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="a8cb1-122">Dopo aver saputo quali record host A (o AAAA) esistono, nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="a8cb1-123">Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **Nuovo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="a8cb1-124">In **nome alias**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="a8cb1-125">In **nome di dominio completo (FQDN) per host di destinazione**Digitare o passare all'FQDN dei servizi Web interni per il pool di server Director, ad esempio lyncwebdir01. contoso. local, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="a8cb1-126">È necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="a8cb1-127">Creazione di un record CNAME DNS esterno</span><span class="sxs-lookup"><span data-stu-id="a8cb1-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="a8cb1-128">Per creare un record CNAME DNS esterno, è necessario connettersi al provider DNS pubblico e quindi seguire i passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="a8cb1-129">Non è possibile descrivere esattamente la posizione in cui si sta nell'ambiente del provider DNS, in quanto potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma è possibile che questi passaggi siano utili.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="a8cb1-130">Accedere al provider DNS esterno con un account che possa creare record DNS in tale ambiente.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="a8cb1-131">È già necessario disporre di un dominio SIP creato per questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="a8cb1-132">Espandere la **zona di ricerca diretta** per il dominio SIP oppure selezionarla in base all'interfaccia DNS esterna utilizzata.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="a8cb1-133">È già necessario visualizzare un record host A (AAAA per IPv6) per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com), quindi verificare che sia presente.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="a8cb1-134">In caso contrario, potrebbe non essere utilizzato un pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="a8cb1-135">In tal caso, è necessario utilizzare il nome di dominio completo del pool Front end oppure se si esegue questa operazione per un singolo server, per il server Front-End o per il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="a8cb1-136">È inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool Front End (ad esempio lyncwebextpool01.contoso.com) oppure un FQDN per l'FQDN a server singolo se non si dispone di un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="a8cb1-137">Come indicato nel passaggio precedente, è necessario eseguire le seguenti operazione se non si dispone di un pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="a8cb1-138">A questo punto, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo alias (CNAME)** (può essere un'opzione di menu o un collegamento, a seconda del formato del provider DNS).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="a8cb1-139">La casella di testo **nome alias** dovrebbe essere una forma come con il DNS interno, è necessario immettere Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="a8cb1-140">È inoltre necessario disporre di una forma di un **nome di dominio completo (FQDN) per** la casella di testo host di destinazione, in cui è possibile immettere l'FQDN dei servizi Web esterni per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com) e quindi fare clic su OK o su qualsiasi azione nel DNS esterno per accettare la creazione di questa voce.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="a8cb1-141">Come indicato nel passaggio 4, in alto, se non si dispone di un pool di server Director, è necessario utilizzare il nome di dominio completo del pool Front end o il nome di dominio completo (FQDN) che è stato configurato, a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="a8cb1-142">Sarà necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="a8cb1-143">Creazione di un record A DNS interno</span><span class="sxs-lookup"><span data-stu-id="a8cb1-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="a8cb1-144">Per creare un record DNS interno, eseguire l'accesso a un server DNS della rete con un account di dominio che sia membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="a8cb1-145">Aprire lo snap-in amministrativo DNS. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="a8cb1-146">Per un record DNS interno, nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio Active Directory, ad esempio contoso. local, in cui sono installati il pool di server Director e il pool Front End di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="a8cb1-147">Controllare e vedere se esiste un record host A (AAAA per IPv6) per il pool di server Director per un record DNS interno, deve esistere un record host a per il nome di dominio completo (FQDN) dei servizi Web interni per il pool di Director, ad esempio lyncwebdir01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="a8cb1-148">Se non è presente, è possibile che non si utilizzi un pool di server Director e che sia necessario utilizzare l'indirizzo IP per il pool Front end o persino un indirizzo IP di un singolo computer, se questa è la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="a8cb1-149">Tenendo presente questo avviso, verificare se esiste un record host A (AAAA per IPv6) per il pool Front end per un record DNS interno, deve esistere un record host A (o AAAA) per l'FQDN dei servizi Web interni per il pool Front End, ad esempio lyncwebpool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="a8cb1-150">In caso contrario, è necessario prendere nota dell'indirizzo IP per il front end server o il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="a8cb1-151">Dopo aver saputo quali record host A (o AAAA) esistono, nell'albero della console del server DNS espandere Zone di **ricerca diretta** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="a8cb1-152">Fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="a8cb1-153">In **nome**Digitare LyncdiscoverInternal come nome host per l'URL del servizio di individuazione automatica interno.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="a8cb1-154">In **indirizzo IP**Digitare l'indirizzo IP dei servizi Web interni del Director (oppure, se si utilizza un servizio di bilanciamento del carico, digitare l'IP virtuale (VIP) del bilanciamento del carico del server Director).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="a8cb1-155">Come indicato nel passaggio 4 precedente, se non si utilizza un Director, potrebbe essere necessario immettere l'indirizzo IP del server front end server o Standard Edition oppure, se si utilizza un bilanciamento del carico, digitare il VIP del bilanciamento del carico del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="a8cb1-156">Fare clic su **Aggiungi host** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="a8cb1-157">Per creare un record A o AAAA aggiuntivo, ripetere i passaggi da 8 a 10, tenendo presente che sarà necessario creare nuovi record a o AAAA di individuazione automatica nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="a8cb1-158">Dopo aver terminato di creare i record A (per IPv6, AAAA), fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="a8cb1-159">Creazione di un record A DNS esterno</span><span class="sxs-lookup"><span data-stu-id="a8cb1-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="a8cb1-160">Per creare un record DNS esterno, connettersi al provider DNS pubblico e quindi seguire i passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="a8cb1-161">Non è possibile descrivere esattamente la posizione in cui si sta nell'ambiente del provider DNS, in quanto potrebbero essere disponibili diversi modi per gestire il DNS esterno, ma è possibile che questi passaggi siano utili.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="a8cb1-162">È necessario essere connessi come account in grado di creare record DNS in tale ambiente.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="a8cb1-163">Per un record DNS esterno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="a8cb1-164">Per un record DNS esterno, nell'albero della console del server DNS espandere **Zone di ricerca diretta** per il dominio SIP, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="a8cb1-165">È già necessario visualizzare un record host A (AAAA per IPv6) per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com), quindi verificare che sia presente e cosa sia l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="a8cb1-166">In caso contrario, potrebbe non essere utilizzato un pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="a8cb1-167">In tal caso, è necessario utilizzare l'indirizzo IP del pool Front end oppure se si esegue questa operazione per un singolo server, per il server Front-End o per il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="a8cb1-168">Tenere presente che i server possono anche essere dietro un sistema di bilanciamento del carico o tramite un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="a8cb1-169">Prendere nota degli indirizzi IP, nonché per i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="a8cb1-170">È inoltre necessario verificare che esista un record host A (AAAA per IPv6) per il nome di dominio completo (FQDN) dei servizi Web esterni per il pool Front End, ad esempio lyncwebextpool01.contoso.com, oppure un indirizzo IP per l'installazione di Lync a server singolo, se non si dispone di un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="a8cb1-171">Come indicato nel passaggio precedente, è necessario eseguire le seguenti operazione se non si dispone di un pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="a8cb1-172">A questo punto, nel formato appropriato per il provider DNS esterno, scegliere l'opzione per la creazione di un **nuovo host a o AAAA** (può essere un'opzione di menu o un collegamento, a seconda del formato del provider DNS).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="a8cb1-173">È necessario specificare un **nome**, digitare Lyncdiscover come nome host per l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="a8cb1-174">Ci dovrebbe essere anche una casella di testo **indirizzo IP** , ecco dove è possibile immettere l'IP per il pool di server Director (ad esempio, lyncwebexdir01.contoso.com) o eventualmente l'IP del servizio di bilanciamento del carico del pool (o un IP proxy inverso che conduce allo stesso) e quindi fare clic su OK o su qualsiasi azione nel DNS esterno per accettare la creazione di questa voce.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="a8cb1-175">Come indicato nel passaggio 4, in alto, se non si dispone di un pool di server Director, è necessario utilizzare l'indirizzo IP del pool Front end o l'indirizzo IP a un singolo utente configurato, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="a8cb1-176">Sarà necessario creare un nuovo record di individuazione automatica a o AAAA nella zona di ricerca diretta di ogni dominio SIP supportato nell'ambiente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

