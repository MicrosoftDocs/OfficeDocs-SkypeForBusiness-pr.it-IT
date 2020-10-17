---
title: 'Lync Server 2013: architettura di integrazione della messaggistica unificata di Exchange ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2c16350ff111f31eb52a73290b1dbcddc9e580
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512583"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="01e0e-102">Architettura di integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e0e-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e0e-103">_**Ultimo argomento modificato:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="01e0e-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="01e0e-104">L'applicazione di routing di Lync Server 2013 ExUM supporta l'integrazione con una distribuzione di messaggistica unificata di Exchange locale, con la messaggistica unificata di Exchange ospitata da un provider di servizi o con una combinazione di due.</span><span class="sxs-lookup"><span data-stu-id="01e0e-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="01e0e-105">Nella figura riportata di seguito vengono illustrate tutte e tre queste possibilità.</span><span class="sxs-lookup"><span data-stu-id="01e0e-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="01e0e-106">**Integrazione con una distribuzione della messaggistica unificata di Exchange locale e due provider di Exchange ospitati**</span><span class="sxs-lookup"><span data-stu-id="01e0e-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="01e0e-107">![Distribuzione della messaggistica unificata di Exchange in locale di Lync Server](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange in locale di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="01e0e-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="01e0e-108">Sono supportate le modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="01e0e-108">The following modes are supported:</span></span>

  - <span data-ttu-id="01e0e-109">**Distribuzione locale:** Lync Server 2013 e la messaggistica unificata di Exchange sono entrambi distribuiti nei server locali all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="01e0e-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="01e0e-110">**Distribuzione cross-premise:** Lync Server 2013 è distribuito nei server locali all'interno dell'organizzazione e la messaggistica unificata di Exchange è ospitata nella struttura di un provider di servizi online, ad esempio un Data Center di Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="01e0e-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="01e0e-111">**Distribuzione mista:** La distribuzione di Lync Server 2013 dispone di alcune cassette postali utente nei server Exchange locali all'interno dell'azienda e di alcune cassette postali ospitate in un data center del servizio di Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="01e0e-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="01e0e-112">La distribuzione mista può essere utilizzata come soluzione di transizione durante la valutazione e la migrazione in fasi degli utenti nella messaggistica unificata di Exchange ospitata oppure come soluzione definitiva se si sceglie di lasciare in locale i servizi di messaggistica unificata di Exchange di alcuni utenti dopo averne trasferiti altri.</span><span class="sxs-lookup"><span data-stu-id="01e0e-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="01e0e-113">Spazio di indirizzamento SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="01e0e-113">Shared SIP Address Space</span></span>

<span data-ttu-id="01e0e-114">Per integrare Lync Server 2013 con una distribuzione di messaggistica unificata di Exchange locale, è possibile concedere l'autorizzazione Lync Server 2013 alla lettura degli oggetti di servizi di dominio Active Directory di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="01e0e-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="01e0e-115">Questo approccio non funziona per l'integrazione con la messaggistica unificata di Exchange ospitata, tuttavia, perché Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste separate senza alcuna relazione di trust tra di essi.</span><span class="sxs-lookup"><span data-stu-id="01e0e-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="01e0e-116">Per integrare Lync Server 2013 con messaggistica unificata di Exchange ospitata, è necessario configurare uno *spazio di indirizzi SIP condiviso*.</span><span class="sxs-lookup"><span data-stu-id="01e0e-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="01e0e-117">In questa configurazione, lo stesso spazio degli indirizzi del dominio SIP è disponibile sia per Lync Server 2013 che per il provider di servizi di messaggistica unificata di Exchange ospitati.</span><span class="sxs-lookup"><span data-stu-id="01e0e-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01e0e-118">L'utilizzo dello spazio di indirizzi SIP condiviso è simile a quello utilizzato in un ambiente Lync Server 2013 cross-premise, in cui alcuni utenti sono ospitati nella distribuzione locale e alcuni sono disponibili in una distribuzione di hosting (come Lync Online).</span><span class="sxs-lookup"><span data-stu-id="01e0e-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="01e0e-119">Il dominio SIP è diviso tra loro.</span><span class="sxs-lookup"><span data-stu-id="01e0e-119">The SIP domain is split between them.</span></span> <span data-ttu-id="01e0e-120">Quando si integra Lync Server 2013 con la messaggistica unificata di Exchange ospitata, assicurarsi di includere il provider di servizi di messaggistica unificata di Exchange nello spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="01e0e-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="01e0e-121">Per configurare lo spazio di indirizzamento SIP condiviso per l'integrazione con un provider di servizi di messaggistica unificata di Exchange, sarà necessario configurare il server perimetrale come segue:</span><span class="sxs-lookup"><span data-stu-id="01e0e-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="01e0e-122">Configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** per impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="01e0e-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="01e0e-123">**UseDnsSrvRouting** consente di specificare che i server perimetrali si baseranno sui record SRV DNS durante l'invio e la ricezione delle richieste di federazione.</span><span class="sxs-lookup"><span data-stu-id="01e0e-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="01e0e-p105">**AllowFederatedUsers** specifica se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di dominio diviso.</span><span class="sxs-lookup"><span data-stu-id="01e0e-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="01e0e-126">**EnablePartnerDiscovery** specifica se Lync Server 2013 utilizzerà i record DNS per cercare di individuare i domini dei partner che non sono elencati nell'elenco di domini consentiti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="01e0e-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="01e0e-127">Se false, Lync Server 2013 verrà federata solo con i domini che si trovano nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="01e0e-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="01e0e-128">Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.</span><span class="sxs-lookup"><span data-stu-id="01e0e-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="01e0e-129">Nella maggior parte delle distribuzioni, il valore è impostato su False per impedire di aprire la federazione a tutti i partner.</span><span class="sxs-lookup"><span data-stu-id="01e0e-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="01e0e-130">Replicare l'archivio di gestione centrale nel server perimetrale e verificare la replica.</span><span class="sxs-lookup"><span data-stu-id="01e0e-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="01e0e-131">Per ulteriori informazioni, vedere [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="01e0e-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="01e0e-132">Configurare un *provider di hosting* nel server perimetrale eseguendo il cmdlet **New-CsHostingProvider** per impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="01e0e-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="01e0e-133">**Identity** consente di specificare un identificatore come valore stringa univoco per il provider di hosting da creare, ad esempio **Messaggistica unificata Exchange ospitata**.</span><span class="sxs-lookup"><span data-stu-id="01e0e-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="01e0e-p108">**Enabled** consente di indicare se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Deve essere impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="01e0e-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="01e0e-p109">**EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Deve essere impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="01e0e-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="01e0e-138">**HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01e0e-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="01e0e-139">Deve essere impostato su **False**.</span><span class="sxs-lookup"><span data-stu-id="01e0e-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="01e0e-140">**ProxyFQDN** consente di specificare il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting, ad esempio **serverproxy.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="01e0e-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="01e0e-141">Per avere tali informazioni, rivolgersi al provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="01e0e-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="01e0e-142">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="01e0e-142">This value cannot be modified.</span></span> <span data-ttu-id="01e0e-143">Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.</span><span class="sxs-lookup"><span data-stu-id="01e0e-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="01e0e-144">La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01e0e-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="01e0e-145">Deve essere impostato su **False**.</span><span class="sxs-lookup"><span data-stu-id="01e0e-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

