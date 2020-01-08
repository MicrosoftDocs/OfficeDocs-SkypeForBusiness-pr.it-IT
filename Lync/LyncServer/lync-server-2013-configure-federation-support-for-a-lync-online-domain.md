---
title: 'Lync Server 2013: configurare il supporto federativo per un dominio Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7568e3e93850301a0c37fc73ae44cf4f5a84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="7c837-102">Configurare il supporto federativo per un dominio Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c837-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c837-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7c837-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7c837-104">Per la Federazione con un cliente di Microsoft Lync Online 2010 è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7c837-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="7c837-105">Configurare il supporto per il dominio del cliente di Lync Online 2010, ad esempio contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7c837-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="7c837-106">Come specificato nei [prerequisiti per la Federazione con un cliente di Lync Online nella sezione Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) di questa documentazione, è necessario avere già abilitato la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7c837-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="7c837-107">L'abilitazione della Federazione richiede l'impostazione del metodo da usare per controllare l'accesso da domini federati.</span><span class="sxs-lookup"><span data-stu-id="7c837-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="7c837-108">Se l'organizzazione è stata configurata per l'uso dell'individuazione, l'aggiunta del dominio all'elenco consentiti dell'organizzazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7c837-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="7c837-109">Se non è stata abilitata l'individuazione del dominio, è necessario aggiungere il nome di dominio del cliente di Lync Online all'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="7c837-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="7c837-110">È possibile aggiungere un nome di dominio usando il pannello di controllo di Lync Server oppure eseguendo il cmdlet **New-CsAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="7c837-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="7c837-111">Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server, incluso l'attivazione dell'individuazione dei domini, vedere [gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="7c837-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="7c837-112">Per informazioni dettagliate sull'uso del cmdlet **New-CsAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="7c837-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c837-113">Un cliente di Lync Online può avere più domini.</span><span class="sxs-lookup"><span data-stu-id="7c837-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="7c837-114">Se si vuole eseguire la Federazione con più di uno dei domini, è necessario configurare il supporto per ogni singolo dominio con cui si vuole supportare la federazioni e l'amministratore del cliente di Lync Online deve abilitare la Federazione per ognuno dei domini come federati.</span><span class="sxs-lookup"><span data-stu-id="7c837-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="7c837-115">Configurare il supporto per il provider di hosting del dominio cliente di Lync Online 2010 con cui si vuole eseguire la Federazione.</span><span class="sxs-lookup"><span data-stu-id="7c837-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="7c837-116">Usare la procedura descritta in questa sezione per configurare il supporto per il provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="7c837-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c837-117">Questo passaggio è obbligatorio solo per la Federazione con un dominio di un cliente di Lync Online, non per la Federazione con qualsiasi dominio distribuito localmente nella posizione di un partner federato.</span><span class="sxs-lookup"><span data-stu-id="7c837-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="7c837-118">Per configurare il supporto per un provider di hosting</span><span class="sxs-lookup"><span data-stu-id="7c837-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="7c837-119">Da un server front-end avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7c837-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7c837-120">Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="7c837-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="7c837-121">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="7c837-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="7c837-122">Nell'esempio precedente vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c837-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="7c837-123">**Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare.</span><span class="sxs-lookup"><span data-stu-id="7c837-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="7c837-124">Si noti che il comando non riesce se è già stato configurato un provider esistente per questo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="7c837-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="7c837-125">**ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="7c837-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="7c837-126">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="7c837-126">This value cannot be modified.</span></span> <span data-ttu-id="7c837-127">Se il provider di hosting cambia server proxy è necessario eliminare e ricreare la voce per il provider.</span><span class="sxs-lookup"><span data-stu-id="7c837-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="7c837-128">**VerificationLevel** specifica come vengono verificati i messaggi di posta elettronica inviati da un provider di hosting per verificare che siano stati inviati da tale provider.</span><span class="sxs-lookup"><span data-stu-id="7c837-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="7c837-p107">\*\*Enabled \*\* indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Finché il valore non verrà impostato su \*\*True \*\*, le due organizzazioni non potranno scambiarsi messaggi.</span><span class="sxs-lookup"><span data-stu-id="7c837-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="7c837-131">\*\*EnabledSharedAddressSpace \*\* indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).</span><span class="sxs-lookup"><span data-stu-id="7c837-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="7c837-132">**HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c837-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="7c837-133">Se \*\*False \*\*, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c837-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="7c837-134">La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto all'interno della topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c837-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="7c837-135">Per informazioni dettagliate sull'uso di questo cmdlet, vedere [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="7c837-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

