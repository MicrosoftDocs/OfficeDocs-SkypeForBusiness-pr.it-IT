---
title: Configurazione dell'integrazione di Lync Server locale con Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17d3673cde1351a98d709749403cd3a572bfef04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="40dc6-102">Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="40dc6-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40dc6-103">_**Ultimo argomento modificato:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="40dc6-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="40dc6-104">I clienti che utilizzano le distribuzioni di Lync Server 2013 locali possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in una modalità di distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="40dc6-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="40dc6-105">Le caratteristiche di interoperabilità includono accesso Single Sign-on e messaggistica immediata (IM) e integrazione della presenza con l'interfaccia di Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="40dc6-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="40dc6-106">Per abilitare questa integrazione, è necessario configurare il server perimetrale nella distribuzione di Lync Server locale completando le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40dc6-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="40dc6-107">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="40dc6-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="40dc6-108">Configurare un provider di hosting nel server perimetrale</span><span class="sxs-lookup"><span data-stu-id="40dc6-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="40dc6-109">Verificare la replica dell'archivio di gestione centrale aggiornato</span><span class="sxs-lookup"><span data-stu-id="40dc6-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="40dc6-110">Se Lync Server 2013 è integrato con Exchange Online, un utente che sta tentando di accedere a messaggistica istantanea da OWA è considerato un utente remoto o esterno.</span><span class="sxs-lookup"><span data-stu-id="40dc6-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="40dc6-111">In questo scenario, l'utente deve disporre di un criterio di accesso esterno assegnato con l'opzione seguente selezionata:</span><span class="sxs-lookup"><span data-stu-id="40dc6-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="40dc6-112">**Abilita comunicazioni con utenti remoti**</span><span class="sxs-lookup"><span data-stu-id="40dc6-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="40dc6-113">Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Lync Server tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="40dc6-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="40dc6-114">Per ulteriori informazioni, vedere [gestire i criteri di accesso esterno in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="40dc6-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="40dc6-115">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="40dc6-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="40dc6-116">Per integrare Lync Server 2013 locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="40dc6-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="40dc6-117">Lo stesso spazio di indirizzi di dominio SIP è supportato sia da Lync Server che dal servizio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="40dc6-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="40dc6-118">Utilizzando Lync Server Management Shell, configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , utilizzando i parametri visualizzati nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="40dc6-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="40dc6-119">**AllowFederatedUsers** specifica se agli utenti interni è consentito comunicare con utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="40dc6-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="40dc6-120">Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio degli indirizzi SIP condiviso con Lync Server e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="40dc6-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="40dc6-121">Per informazioni dettagliate sull'utilizzo di Lync Server Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="40dc6-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="40dc6-122">Configurare un provider di hosting nel server perimetrale</span><span class="sxs-lookup"><span data-stu-id="40dc6-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="40dc6-123">Utilizzare Lync Server Management Shell per configurare un provider di hosting nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="40dc6-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="40dc6-124">A tale scopo, eseguire il cmdlet **New-CsHostingProvider** , utilizzando i parametri nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="40dc6-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="40dc6-125">Se si utilizza Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro <STRONG>ProxyFqdn</STRONG> in questo esempio ("exap.um.Outlook.com") con il nome di dominio completo per il servizio gestito da 21ViaNet: "exap.um.partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="40dc6-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="40dc6-126">**Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare (ad esempio, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="40dc6-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="40dc6-127">I valori che contengono spazi devono essere racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="40dc6-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="40dc6-128">**Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata.</span><span class="sxs-lookup"><span data-stu-id="40dc6-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="40dc6-129">Questa impostazione deve essere impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="40dc6-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="40dc6-130">**EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="40dc6-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="40dc6-131">Questa impostazione deve essere impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="40dc6-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="40dc6-132">**HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Office Communications Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40dc6-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="40dc6-133">Questo valore deve essere impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="40dc6-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="40dc6-134">**ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="40dc6-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="40dc6-135">Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="40dc6-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="40dc6-136">La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40dc6-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="40dc6-137">Questo valore deve essere impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="40dc6-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="40dc6-138">**VerificationLevel** indica il livello di verifica consentito per i messaggi inviati e ricevuti dal provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="40dc6-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="40dc6-139">Specificare **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="40dc6-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="40dc6-140">Questa opzione si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="40dc6-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="40dc6-141">Se questo livello non viene specificato, il messaggio verrà rifiutato come non verificabile.</span><span class="sxs-lookup"><span data-stu-id="40dc6-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="40dc6-142">Verificare la replica dell'archivio di gestione centrale aggiornato</span><span class="sxs-lookup"><span data-stu-id="40dc6-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="40dc6-143">Le modifiche apportate utilizzando i cmdlet nelle sezioni precedenti vengono applicate automaticamente al server perimetrale e generalmente richiedono meno di un minuto per la replica.</span><span class="sxs-lookup"><span data-stu-id="40dc6-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="40dc6-144">È possibile verificare lo stato della replica e che le modifiche sono state applicate al server perimetrale utilizzando i cmdlet seguenti.</span><span class="sxs-lookup"><span data-stu-id="40dc6-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="40dc6-145">Per verificare gli aggiornamenti della replica su un server interno nella distribuzione di Lync Server, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="40dc6-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="40dc6-146">Per verificare che le modifiche siano state applicate, eseguire il cmdlet seguente nel server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="40dc6-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40dc6-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40dc6-147">See Also</span></span>


[<span data-ttu-id="40dc6-148">Fornire ai messaggi vocali di Lync Server 2013 utenti la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="40dc6-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="40dc6-149">Integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40dc6-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

