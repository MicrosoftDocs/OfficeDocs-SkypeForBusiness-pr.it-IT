---
title: 'Lync Server 2013: configurare il supporto federativo per un dominio Lync Online'
description: 'Lync Server 2013: configurare il supporto federativo per un dominio Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553302"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="1d2ef-103">Configurare il supporto federativo per un dominio Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d2ef-103">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d2ef-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1d2ef-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1d2ef-105">Per la Federazione con un cliente di Microsoft Lync Online 2010 è necessario completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d2ef-105">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="1d2ef-106">Configurare il supporto per il dominio del cliente di Lync Online 2010 (ad esempio, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="1d2ef-106">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="1d2ef-107">Come specificato nei [prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) sezione di questa documentazione, è necessario avere già abilitato la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-107">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="1d2ef-108">Se si abilita la federazione, è necessario specificare il metodo da utilizzare per controllare l'accesso da parte dei domini federati.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-108">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="1d2ef-109">Se l'organizzazione è stata configurata in modo da utilizzare l'individuazione, l'aggiunta del dominio all'elenco dei domini consentiti dell'organizzazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-109">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="1d2ef-110">Se l'individuazione del dominio non è stata abilitata, è necessario aggiungere il nome di dominio del cliente Lync Online all'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-110">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="1d2ef-111">È possibile aggiungere un nome di dominio utilizzando il pannello di controllo di Lync Server o eseguendo il cmdlet **New-CsAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="1d2ef-111">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="1d2ef-112">Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server, inclusa l'abilitazione dell'individuazione dei domini, vedere [Manage SIP Federated Providers for your organization in Lync server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-112">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="1d2ef-113">Per informazioni dettagliate sull'utilizzo del cmdlet **New-CsAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-113">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d2ef-114">Un cliente di Lync Online può disporre di più domini.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-114">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="1d2ef-115">Se si desidera eseguire la Federazione con più domini, è necessario configurare il supporto per ogni singolo dominio con cui si desidera supportare il servizio federativo e l'amministratore del cliente di Lync Online deve abilitare la Federazione per ognuno dei domini da federata.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-115">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="1d2ef-116">Configurare il supporto per il provider di hosting del dominio dei clienti di Lync Online 2010 con cui si desidera eseguire la Federazione.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-116">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="1d2ef-117">Utilizzare la procedura disponibile in questa sezione per configurare il supporto per tale provider.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-117">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d2ef-118">Questo passaggio è obbligatorio solo per la Federazione con un dominio di un cliente di Lync Online, non per la Federazione con qualsiasi dominio distribuito in locale nella posizione di un partner federato.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-118">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="1d2ef-119">Per configurare il supporto per un provider di hosting</span><span class="sxs-lookup"><span data-stu-id="1d2ef-119">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="1d2ef-120">Da un front end server, avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-120">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1d2ef-121">Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-121">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="1d2ef-122">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="1d2ef-122">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="1d2ef-123">Nell'esempio precedente vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d2ef-123">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="1d2ef-p105">**Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. Il comando avrà esito negativo se è stato già configurato un provider esistente con lo stesso valore di Identity.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-p105">**Identity** specifies a unique string value identifier for the hosting provider that you are creating. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="1d2ef-p106">**ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-p106">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="1d2ef-129">**VerificationLevel** specifica come o se i messaggi inviati da un provider di hosting devono essere verificati per accertare che provengano effettivamente da quel provider.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-129">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="1d2ef-p107">**Enabled** indica se la connessione di rete fra il proprio dominio e il provider di hosting è abilitata. Finché il valore non viene impostato su **True**, le due organizzazioni non potranno scambiarsi messaggi.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="1d2ef-132">**EnabledSharedAddressSpace** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).</span><span class="sxs-lookup"><span data-stu-id="1d2ef-132">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="1d2ef-133">**HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="1d2ef-134">Se **False**, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-134">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="1d2ef-135">La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-135">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="1d2ef-136">Per informazioni dettagliate sull'utilizzo di questo cmdlet, vedere [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1d2ef-136">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

