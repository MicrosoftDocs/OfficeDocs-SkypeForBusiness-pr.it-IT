---
title: 'Lync Server 2013: configurazione dei server proxy inversi'
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
ms.openlocfilehash: 6cd5b57c29a622b7c0f051b00bb0ef30e265743e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="688cc-102">Configurazione dei server proxy inversi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="688cc-103">_**Ultimo argomento modificato:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="688cc-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="688cc-104">Per le distribuzioni di Microsoft Lync Server 2013 Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per i client esterni per accedere ai servizi Web di Lync Server 2013 (denominati *componenti Web* in Office Communications Server) nel Director e nel pool Home dell'utente.</span><span class="sxs-lookup"><span data-stu-id="688cc-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="688cc-105">Di seguito sono riportate alcune funzionalità che richiedono l'accesso esterno tramite un proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="688cc-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="688cc-106">Consentire agli utenti esterni di scaricare il contenuto delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="688cc-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="688cc-107">Consentire agli utenti esterni di espandere i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="688cc-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="688cc-108">Consentire agli utenti remoti di scaricare file dal servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="688cc-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="688cc-109">Accesso al client Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="688cc-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="688cc-110">Accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="688cc-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="688cc-111">Consentire ai dispositivi esterni di connettersi al servizio Web di aggiornamento dispositivi e ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="688cc-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="688cc-112">Consentire alle applicazioni mobili di individuare e utilizzare automaticamente gli URL mobili (MCX) da Internet.</span><span class="sxs-lookup"><span data-stu-id="688cc-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="688cc-113">Abilitazione del client Lync 2013, dell'app Lync Windows Store e del client per dispositivi mobili Lync 2013 per individuare gli URL di individuazione delle scoperte (individuazione automatica) di Lync e utilizzare Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="688cc-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="688cc-114">È consigliabile configurare il proxy inverso HTTP per la pubblicazione di tutti i servizi Web in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="688cc-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="688cc-115">Publishing https://ExternalFQDN\* /pubblica tutte le directory virtuali di IIS per un pool.</span><span class="sxs-lookup"><span data-stu-id="688cc-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="688cc-116">È necessaria una regola di pubblicazione per ogni server Standard Edition, pool Front End, Director o pool di server Director presente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="688cc-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="688cc-117">È inoltre necessario pubblicare gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="688cc-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="688cc-118">Se l'organizzazione dispone di un Director o di un pool di server Director, il proxy inverso HTTP resterà in attesa delle richieste HTTP/HTTPS relative agli URL semplici e le invierà tramite proxy alla directory virtuale dei servizi Web esterni nel Director o nel pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="688cc-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="688cc-119">Se non è stato distribuito un Director, sarà necessario designare un pool per la gestione delle richieste dirette agli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="688cc-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="688cc-120">Se non si tratta del pool principale dell'utente, le richieste verranno reindirizzate ai servizi Web in tale pool principale.</span><span class="sxs-lookup"><span data-stu-id="688cc-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="688cc-121">Gli URL semplici possono essere gestiti da una regola di pubblicazione Web dedicata oppure è possibile aggiungerli ai nomi pubblici della regola di pubblicazione Web per il Director.</span><span class="sxs-lookup"><span data-stu-id="688cc-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="688cc-122">È inoltre necessario pubblicare l'URL del servizio di individuazione automatica esterno.</span><span class="sxs-lookup"><span data-stu-id="688cc-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="688cc-123">È possibile utilizzare Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7,0, 7,5 o 8,0 con Application Request Routing (IIS ARR) come proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="688cc-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="688cc-124">Nei passaggi dettagliati di questa sezione viene descritto come configurare Forefront Threat Management Gateway 2010, in quanto i passaggi per configurare ISA Server 2006 sono praticamente identici.</span><span class="sxs-lookup"><span data-stu-id="688cc-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="688cc-125">Vengono inoltre fornite indicazioni per IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="688cc-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="688cc-126">Se si utilizza un proxy inverso diverso, consultare la documentazione relativa a tale prodotto e mappare i requisiti definiti qui alle caratteristiche associate in altri proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="688cc-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="688cc-127">Internet Information Server Application Request Routing (IIS ARR) è un'opzione completamente testata e supportata per l'implementazione di un proxy inverso per Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="688cc-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="688cc-128">Nel novembre 2012, Microsoft ha interrotto la vendita delle licenze di ForeFront Threat Management Gateway 2010 o TMG.</span><span class="sxs-lookup"><span data-stu-id="688cc-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="688cc-129">La TMG è ancora un prodotto pienamente supportato ed è ancora disponibile per la vendita su elettrodomestici venduti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="688cc-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="688cc-130">Inoltre, molti dispositivi di bilanciamento del carico hardware di terze parti e firewall forniscono supporto per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="688cc-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="688cc-131">Per i servizi di bilanciamento del carico hardware e firewall che forniscono funzionalità di proxy inverso, consultare il fornitore per istruzioni specifiche su come configurare il proprio prodotto per fornire il supporto per il proxy inverso per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="688cc-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="688cc-132">È inoltre possibile visualizzare terze parti che hanno inviato documentazione per il proprio prodotto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="688cc-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="688cc-133">Il supporto tecnico viene fornito da terze parti per la propria soluzione.</span><span class="sxs-lookup"><span data-stu-id="688cc-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="688cc-134">Per visualizzare terze parti attive nella fornitura di soluzioni, vedere <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="688cc-134">To see third parties that are active in providing solutions, see <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="688cc-135">Negli argomenti e nelle procedure seguenti viene utilizzato Forefront Threat Management Gateway 2010 e IIS ARR come base per le procedure di distribuzione e configurazione.</span><span class="sxs-lookup"><span data-stu-id="688cc-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="688cc-136">Configurare i nomi di dominio completi della Web farm per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="688cc-137">Configurare le schede di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="688cc-138">Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="688cc-139">Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="688cc-140">Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="688cc-141">Creare record DNS per i server proxy inversi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="688cc-142">Verificare l'accesso tramite il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cc-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="688cc-143">Operazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="688cc-143">Before You Begin</span></span>

<span data-ttu-id="688cc-144">Per una distribuzione corretta di Forefront Threat Management Gateway 2010 come proxy inverso, è necessario impostare e configurare un server, utilizzando i prerequisiti e i requisiti hardware definiti nella documentazione di Forefront Threat Management Gateway 2010.</span><span class="sxs-lookup"><span data-stu-id="688cc-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="688cc-145">Vedere l'argomento seguente impostato per configurare correttamente l'hardware e per installare Forefront Threat Management Gateway 2010 sul server prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="688cc-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="688cc-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="688cc-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="688cc-147">Consigli sull'hardware di Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="688cc-147">Forefront TMG 2010 hardware recommendations</span></span>](http://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="688cc-148">Per distribuire correttamente IIS ARR come proxy inverso, esaminare gli argomenti seguenti per configurare l'hardware e il software prerequisito.</span><span class="sxs-lookup"><span data-stu-id="688cc-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="688cc-149">Per installare IIS su Windows Server 2008 o Windows Server 2008 R2, vedere [Installing IIS 7 on Windows server 2008 o Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="688cc-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="688cc-150">Per installare IIS su Windows Server 2012, vedere [installazione di IIS 8 su Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="688cc-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="688cc-151">Per installare IIS su Windows Server 2012 R2, vedere [installazione di iis 8,5 su Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="688cc-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="688cc-152">Per scaricare l'estensione di routing delle richieste di applicazioni per IIS, seguire le istruzioni sul [download di Application Request Routing v 2.5](http://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="688cc-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="688cc-153">Per installare ARR, per le istruzioni riportate in [Install Application Request Routing versione 2](http://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="688cc-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](http://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="688cc-154">Le istruzioni attualmente pubblicate sono per ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="688cc-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="688cc-155">Per l'installazione dell'estensione, non esiste alcuna differenza tra le due versioni.</span><span class="sxs-lookup"><span data-stu-id="688cc-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

