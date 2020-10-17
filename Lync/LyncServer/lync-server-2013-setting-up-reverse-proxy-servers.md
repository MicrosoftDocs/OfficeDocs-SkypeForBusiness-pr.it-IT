---
title: 'Lync Server 2013: configurazione dei server proxy inversi'
description: 'Lync Server 2013: configurazione dei server proxy inversi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd5842e4d735637406f6d0fa4f467f1cb8ed03
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549222"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="d9339-103">Configurazione dei server proxy inversi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-103">Setting up reverse proxy servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9339-104">_**Ultimo argomento modificato:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="d9339-104">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="d9339-105">Per le distribuzioni di Microsoft Lync Server 2013 Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per i client esterni per accedere ai servizi Web di Lync Server 2013 (denominati *componenti Web* in Office Communications Server) nel Director e nel pool Home dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d9339-105">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="d9339-106">Di seguito sono riportate alcune funzionalità che richiedono l'accesso esterno tramite un proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="d9339-106">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="d9339-107">Consentire agli utenti esterni di scaricare il contenuto delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d9339-107">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="d9339-108">Consentire agli utenti esterni di espandere i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d9339-108">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="d9339-109">Consentire agli utenti remoti di scaricare file dal servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="d9339-109">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="d9339-110">Accesso al client Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="d9339-110">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="d9339-111">Accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d9339-111">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="d9339-112">Consentire ai dispositivi esterni di connettersi al servizio Web di aggiornamento dispositivi e ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="d9339-112">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="d9339-113">Consentire alle applicazioni mobili di individuare e utilizzare automaticamente gli URL mobili (MCX) da Internet.</span><span class="sxs-lookup"><span data-stu-id="d9339-113">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="d9339-114">Abilitazione del client Lync 2013, dell'app Lync Windows Store e del client per dispositivi mobili Lync 2013 per individuare gli URL di individuazione delle scoperte (individuazione automatica) di Lync e utilizzare Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="d9339-114">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="d9339-115">È consigliabile configurare il proxy inverso HTTP per la pubblicazione di tutti i servizi Web in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="d9339-115">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="d9339-116">Publishing https://ExternalFQDN/ \* pubblica tutte le directory virtuali di IIS per un pool.</span><span class="sxs-lookup"><span data-stu-id="d9339-116">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="d9339-117">È necessaria una regola di pubblicazione per ogni server Standard Edition, pool Front End, Director o pool di server Director presente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-117">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="d9339-118">È inoltre necessario pubblicare gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="d9339-118">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="d9339-119">Se l'organizzazione dispone di un Director o di un pool di server Director, il proxy inverso HTTP resterà in attesa delle richieste HTTP/HTTPS relative agli URL semplici e le invierà tramite proxy alla directory virtuale dei servizi Web esterni nel Director o nel pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="d9339-119">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="d9339-120">Se non è stato distribuito un Director, sarà necessario designare un pool per la gestione delle richieste dirette agli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="d9339-120">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="d9339-121">Se non si tratta del pool principale dell'utente, le richieste verranno reindirizzate ai servizi Web in tale pool principale.</span><span class="sxs-lookup"><span data-stu-id="d9339-121">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="d9339-122">Gli URL semplici possono essere gestiti da una regola di pubblicazione Web dedicata oppure è possibile aggiungerli ai nomi pubblici della regola di pubblicazione Web per il Director.</span><span class="sxs-lookup"><span data-stu-id="d9339-122">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="d9339-123">È inoltre necessario pubblicare l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="d9339-123">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="d9339-124">È possibile utilizzare Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7,0, 7,5 o 8,0 con Application Request Routing (IIS ARR) come proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d9339-124">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="d9339-125">Nei passaggi dettagliati di questa sezione viene descritto come configurare Forefront Threat Management Gateway 2010, in quanto i passaggi per configurare ISA Server 2006 sono praticamente identici.</span><span class="sxs-lookup"><span data-stu-id="d9339-125">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="d9339-126">Vengono inoltre fornite indicazioni per IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="d9339-126">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="d9339-127">Se si utilizza un proxy inverso diverso, consultare la documentazione relativa a tale prodotto e mappare i requisiti definiti qui alle caratteristiche associate in altri proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="d9339-127">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9339-128">Internet Information Server Application Request Routing (IIS ARR) è un'opzione completamente testata e supportata per l'implementazione di un proxy inverso per Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9339-128">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="d9339-129">Nel novembre 2012, Microsoft ha interrotto la vendita delle licenze di ForeFront Threat Management Gateway 2010 o TMG.</span><span class="sxs-lookup"><span data-stu-id="d9339-129">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="d9339-130">La TMG è ancora un prodotto pienamente supportato ed è ancora disponibile per la vendita su elettrodomestici venduti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d9339-130">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="d9339-131">Inoltre, molti dispositivi di bilanciamento del carico hardware di terze parti e firewall forniscono supporto per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d9339-131">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="d9339-132">Per i servizi di bilanciamento del carico hardware e firewall che forniscono funzionalità di proxy inverso, consultare il fornitore per istruzioni specifiche su come configurare il proprio prodotto per fornire il supporto per il proxy inverso per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9339-132">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="d9339-133">È inoltre possibile visualizzare terze parti che hanno inviato documentazione per il proprio prodotto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d9339-133">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="d9339-134">Il supporto tecnico viene fornito da terze parti per la propria soluzione.</span><span class="sxs-lookup"><span data-stu-id="d9339-134">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="d9339-135">Per visualizzare terze parti attive nella fornitura di soluzioni, vedere <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="d9339-135">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="d9339-136">Negli argomenti e nelle procedure seguenti viene utilizzato Forefront Threat Management Gateway 2010 e IIS ARR come base per le procedure di distribuzione e configurazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-136">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="d9339-137">Configurare i nomi di dominio completi della Web farm per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-137">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="d9339-138">Configurare le schede di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-138">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="d9339-139">Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-139">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="d9339-140">Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-140">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="d9339-141">Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-141">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="d9339-142">Creare record DNS per i server proxy inversi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-142">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="d9339-143">Verificare l'accesso tramite il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9339-143">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="d9339-144">Operazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="d9339-144">Before You Begin</span></span>

<span data-ttu-id="d9339-145">Per una distribuzione corretta di Forefront Threat Management Gateway 2010 come proxy inverso, è necessario impostare e configurare un server, utilizzando i prerequisiti e i requisiti hardware definiti nella documentazione di Forefront Threat Management Gateway 2010.</span><span class="sxs-lookup"><span data-stu-id="d9339-145">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="d9339-146">Vedere l'argomento seguente impostato per configurare correttamente l'hardware e per installare Forefront Threat Management Gateway 2010 sul server prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d9339-146">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="d9339-147">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="d9339-147">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="d9339-148">Consigli sull'hardware di Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="d9339-148">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="d9339-149">Per distribuire correttamente IIS ARR come proxy inverso, esaminare gli argomenti seguenti per configurare l'hardware e il software prerequisito.</span><span class="sxs-lookup"><span data-stu-id="d9339-149">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="d9339-150">Per installare IIS su Windows Server 2008 o Windows Server 2008 R2, vedere [Installing IIS 7 on Windows server 2008 o Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="d9339-150">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="d9339-151">Per installare IIS su Windows Server 2012, vedere [installazione di IIS 8 su Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="d9339-151">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="d9339-152">Per installare IIS su Windows Server 2012 R2, vedere [installazione di iis 8,5 su Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="d9339-152">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="d9339-153">Per scaricare l'estensione di routing delle richieste di applicazioni per IIS, seguire le istruzioni sul [download di Application Request Routing v 2.5](https://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="d9339-153">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="d9339-154">Per installare ARR, per le istruzioni riportate in [Install Application Request Routing versione 2](https://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="d9339-154">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9339-155">Le istruzioni attualmente pubblicate sono per ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="d9339-155">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="d9339-156">Per l'installazione dell'estensione, non esiste alcuna differenza tra le due versioni.</span><span class="sxs-lookup"><span data-stu-id="d9339-156">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

