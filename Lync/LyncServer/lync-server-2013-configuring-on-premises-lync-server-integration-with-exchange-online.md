---
title: Configurazione dell'integrazione di Lync Server locale con Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae1ba45ace830f33b239bf2f8ead1a75fcee3417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="ead94-102">Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ead94-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ead94-103">_**Argomento Ultima modifica:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="ead94-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="ead94-104">I clienti che usano distribuzioni locali di Lync Server 2013 possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in modalità di distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="ead94-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ead94-105">Le caratteristiche di interoperabilità includono il Single Sign-on e la messaggistica istantanea (IM) e l'integrazione della presenza con l'interfaccia di Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ead94-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ead94-106">Per abilitare questa integrazione, è necessario configurare l'Edge Server nella distribuzione locale di Lync Server completando le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ead94-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="ead94-107">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="ead94-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="ead94-108">Configurare un provider di hosting nell'Edge Server</span><span class="sxs-lookup"><span data-stu-id="ead94-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="ead94-109">Verificare la replica dell'archivio di gestione centralizzato aggiornato</span><span class="sxs-lookup"><span data-stu-id="ead94-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="ead94-110">Se Lync Server 2013 è integrato con Exchange Online, un utente che sta provando ad accedere a messaggistica istantanea da OWA viene considerato un utente remoto o esterno.</span><span class="sxs-lookup"><span data-stu-id="ead94-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="ead94-111">In questo scenario, questo utente deve avere un criterio di accesso esterno assegnato con l'opzione seguente selezionata:</span><span class="sxs-lookup"><span data-stu-id="ead94-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="ead94-112">**Abilitare le comunicazioni con gli utenti remoti**</span><span class="sxs-lookup"><span data-stu-id="ead94-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="ead94-113">Abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Lync Server tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="ead94-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="ead94-114">Per altre informazioni, vedere [gestire i criteri di accesso esterno in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ead94-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ead94-115">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="ead94-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ead94-116">Per integrare Lync Server 2013 in locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="ead94-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ead94-117">Lo stesso spazio per l'indirizzo del dominio SIP è supportato sia da Lync Server che dal servizio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ead94-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="ead94-118">Usando Lync Server Management Shell, configurare l'Edge Server per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , usando i parametri visualizzati nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ead94-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="ead94-119">\*\*AllowFederatedUsers \*\* specifica se agli utenti interni è consentito comunicare con utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="ead94-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ead94-120">Questa proprietà determina anche se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio di indirizzi SIP condiviso con Lync Server ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ead94-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="ead94-121">Per informazioni dettagliate su come usare Lync Server Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ead94-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ead94-122">Configurare un provider di hosting nell'Edge Server</span><span class="sxs-lookup"><span data-stu-id="ead94-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ead94-123">Usare Lync Server Management Shell per configurare un provider di hosting nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ead94-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="ead94-124">A questo scopo, eseguire il cmdlet **New-CsHostingProvider** usando i parametri nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ead94-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="ead94-125">Se si usa Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro <STRONG>ProxyFqdn</STRONG> in questo esempio ("exap.um.Outlook.com") con il nome di dominio completo per il servizio gestito da 21ViaNet: "exap.um.partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="ead94-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="ead94-126">**Identity** specifica un identificatore di valore di stringa univoco per il provider di hosting da creare, ad esempio "Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ead94-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ead94-127">I valori che contengono spazi devono essere racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="ead94-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="ead94-128">\*\*Enabled \*\* indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata.</span><span class="sxs-lookup"><span data-stu-id="ead94-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ead94-129">Deve essere impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="ead94-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="ead94-130">**EnabledSharedAddressSpace** indica se il provider di hosting verrà usato in uno scenario di spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="ead94-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ead94-131">Deve essere impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="ead94-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="ead94-132">**HostsOCSUsers** indica se il provider di hosting viene usato per ospitare Office Communications Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ead94-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="ead94-133">Deve essere impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="ead94-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="ead94-134">**ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="ead94-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ead94-135">Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ead94-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="ead94-136">La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto all'interno della topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ead94-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="ead94-137">Deve essere impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="ead94-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="ead94-138">**VerificationLevel** indica il livello di verifica consentito per i messaggi inviati da e verso il provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="ead94-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ead94-139">Specifica **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="ead94-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="ead94-140">Questa opzione si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="ead94-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="ead94-141">Se questo livello non è specificato, il messaggio verrà rifiutato come non verificabile.</span><span class="sxs-lookup"><span data-stu-id="ead94-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ead94-142">Verificare la replica dell'archivio di gestione centralizzato aggiornato</span><span class="sxs-lookup"><span data-stu-id="ead94-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ead94-143">Le modifiche apportate tramite i cmdlet nelle sezioni precedenti vengono applicate automaticamente all'Edge Server e in genere richiedono meno di un minuto per la replica.</span><span class="sxs-lookup"><span data-stu-id="ead94-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="ead94-144">Puoi verificare lo stato della replica e che le modifiche sono state applicate all'Edge Server usando i cmdlet seguenti.</span><span class="sxs-lookup"><span data-stu-id="ead94-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="ead94-145">Per verificare gli aggiornamenti della replica su un server interno nella distribuzione di Lync Server, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="ead94-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="ead94-146">Per verificare che le modifiche siano state applicate, eseguire il cmdlet seguente nell'Edge Server:</span><span class="sxs-lookup"><span data-stu-id="ead94-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ead94-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ead94-147">See Also</span></span>


[<span data-ttu-id="ead94-148">Fornire agli utenti di Lync Server 2013 la segreteria telefonica nella messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="ead94-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="ead94-149">Integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ead94-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

