---
title: Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def07f8caf302471e2d1466bb1a783732ebdc691
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="9dc19-102">Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="9dc19-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dc19-103">_**Ultimo argomento modificato:** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="9dc19-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="9dc19-104">Per fornire agli utenti di Lync Server 2013 con funzionalità di segreteria telefonica nella messaggistica unificata di Exchange ospitata, è necessario eseguire le attività di configurazione seguenti nel server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="9dc19-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="9dc19-105">Configurare il server perimetrale per la federazione.</span><span class="sxs-lookup"><span data-stu-id="9dc19-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="9dc19-106">Replicare i dati dell'archivio di gestione centrale nel server perimetrale e verificare la replica.</span><span class="sxs-lookup"><span data-stu-id="9dc19-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="9dc19-107">Creare un provider di hosting nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9dc19-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="9dc19-108">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dc19-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9dc19-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9dc19-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="9dc19-110">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9dc19-110">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9dc19-111">Prima di eseguire queste operazioni, è necessario creare un record DNS SRV esterno per il servizio Exchange di hosting.</span><span class="sxs-lookup"><span data-stu-id="9dc19-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="9dc19-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata</A>.</span><span class="sxs-lookup"><span data-stu-id="9dc19-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="9dc19-113">Per configurare il server perimetrale per la federazione</span><span class="sxs-lookup"><span data-stu-id="9dc19-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="9dc19-114">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9dc19-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9dc19-p102">Eseguire il cmdlet Set-CsAccessEdgeConfiguration per configurare il server per la federazione. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9dc19-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="9dc19-117">Nell'esempio precedente vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dc19-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="9dc19-118">**UseDnsSrvRouting** specifica che i server perimetrali si baseranno su record DNS SRV per l'invio e la ricezione di richieste di federazione.</span><span class="sxs-lookup"><span data-stu-id="9dc19-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="9dc19-p103">**AllowFederatedUsers** specifica se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di dominio diviso.</span><span class="sxs-lookup"><span data-stu-id="9dc19-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="9dc19-121">**EnablePartnerDiscovery** specifica se Lync Server utilizzerà i record DNS per cercare di individuare i domini dei partner non elencati nell'elenco di domini consentiti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9dc19-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="9dc19-122">Se false, Lync Server 2013 verrà associato solo ai domini trovati nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="9dc19-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="9dc19-123">Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.</span><span class="sxs-lookup"><span data-stu-id="9dc19-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="9dc19-124">Nella maggior parte delle distribuzioni, il valore è impostato su False per impedire di aprire la federazione a tutti i partner.</span><span class="sxs-lookup"><span data-stu-id="9dc19-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="9dc19-125">Per replicare i dati nel server perimetrale e verificare la replica</span><span class="sxs-lookup"><span data-stu-id="9dc19-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="9dc19-126">Verificare che la replica nel server perimetrale sia completa.</span><span class="sxs-lookup"><span data-stu-id="9dc19-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="9dc19-127">Per la procedura, vedere [verificare la connettività tra server interni e server perimetrali in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="9dc19-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="9dc19-128">Per creare un provider di hosting nel server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9dc19-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="9dc19-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9dc19-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9dc19-130">Eseguire il cmdlet **New-CsHostingProvider** per configurare il provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="9dc19-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="9dc19-131">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9dc19-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="9dc19-132">Nell'esempio precedente vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dc19-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="9dc19-p107">**Identity** specifica un identificatore di valore di stringa univoco per il provider di hosting da creare, in questo esempio **Fabrikam.com**. Si noti che il comando non riesce se è già stato configurato un provider esistente per questo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="9dc19-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="9dc19-p108">**Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Finché il valore non verrà impostato su **True**, le due organizzazioni non potranno scambiarsi messaggi.</span><span class="sxs-lookup"><span data-stu-id="9dc19-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="9dc19-137">**EnabledSharedAddressSpace** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).</span><span class="sxs-lookup"><span data-stu-id="9dc19-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="9dc19-138">Prima di impostare <CODE>EnableSharedAddressSpace</CODE> su true, provare a risolvere il record SRV federativo internamente.</span><span class="sxs-lookup"><span data-stu-id="9dc19-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="9dc19-139">Se il record non può essere risolto internamente, è necessario creare i record, _sipfederationtls. _tcp. &lt;domain&gt; e _sip. _tls. &lt;dominio&gt; nel DNS interno.</span><span class="sxs-lookup"><span data-stu-id="9dc19-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="9dc19-140">Questi record devono puntare all'indirizzo IP esterno dell'interfaccia di accesso del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9dc19-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="9dc19-141">**HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dc19-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="9dc19-142">Se **False**, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="9dc19-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="9dc19-p111">**ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting, in questo esempio **proxyserver.fabrikam.com**. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy è necessario eliminare e ricreare la voce per il provider.</span><span class="sxs-lookup"><span data-stu-id="9dc19-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="9dc19-146">La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dc19-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="9dc19-147">**VerficationLevel** indica il livello di verifica consentito per i messaggi inviati e ricevuti dal provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="9dc19-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="9dc19-148">Specificare **UseSourceVerification**, che si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="9dc19-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="9dc19-149">Se il livello non è specificato, il messaggio verrà rifiutato in quanto non verificabile.</span><span class="sxs-lookup"><span data-stu-id="9dc19-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9dc19-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dc19-150">See Also</span></span>


[<span data-ttu-id="9dc19-151">Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</span><span class="sxs-lookup"><span data-stu-id="9dc19-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="9dc19-152">Verificare la connettività tra server interni e server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dc19-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="9dc19-153">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9dc19-153">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

