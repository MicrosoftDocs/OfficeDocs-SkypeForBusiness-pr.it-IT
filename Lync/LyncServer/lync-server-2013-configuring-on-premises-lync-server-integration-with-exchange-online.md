---
title: Configurazione dell'integrazione di Lync Server locale con Exchange Online
description: Configurazione dell'integrazione di Lync Server locale con Exchange Online.
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
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553938"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="a38a4-103">Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a38a4-103">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a38a4-104">_**Ultimo argomento modificato:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="a38a4-104">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="a38a4-105">I clienti che utilizzano le distribuzioni di Lync Server 2013 locali possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in una modalità di distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="a38a4-105">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="a38a4-106">Le caratteristiche di interoperabilità includono accesso Single Sign-on e messaggistica immediata (IM) e integrazione della presenza con l'interfaccia di Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="a38a4-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="a38a4-107">Per abilitare questa integrazione, è necessario configurare il server perimetrale nella distribuzione di Lync Server locale completando le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a4-107">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="a38a4-108">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="a38a4-108">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="a38a4-109">Configurare un provider di hosting nel server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a38a4-109">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="a38a4-110">Verificare la replica dell'archivio di gestione centrale aggiornato</span><span class="sxs-lookup"><span data-stu-id="a38a4-110">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="a38a4-111">Se Lync Server 2013 è integrato con Exchange Online, un utente che sta tentando di accedere a messaggistica istantanea da OWA è considerato un utente remoto o esterno.</span><span class="sxs-lookup"><span data-stu-id="a38a4-111">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="a38a4-112">In questo scenario, l'utente deve disporre di un criterio di accesso esterno assegnato con l'opzione seguente selezionata:</span><span class="sxs-lookup"><span data-stu-id="a38a4-112">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="a38a4-113">**Abilita comunicazioni con utenti remoti**</span><span class="sxs-lookup"><span data-stu-id="a38a4-113">**Enable communications with remote users**</span></span>

<span data-ttu-id="a38a4-114">Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Lync Server tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="a38a4-114">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="a38a4-115">Per ulteriori informazioni, vedere [gestire i criteri di accesso esterno in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="a38a4-115">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="a38a4-116">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="a38a4-116">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="a38a4-117">Per integrare Lync Server 2013 locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="a38a4-117">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="a38a4-118">Lo stesso spazio di indirizzi di dominio SIP è supportato sia da Lync Server che dal servizio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a38a4-118">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="a38a4-119">Utilizzando Lync Server Management Shell, configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , utilizzando i parametri visualizzati nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a38a4-119">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="a38a4-120">**AllowFederatedUsers** specifica se agli utenti interni è consentito comunicare con utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="a38a4-120">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="a38a4-121">Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio degli indirizzi SIP condiviso con Lync Server e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a38a4-121">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="a38a4-122">Per informazioni dettagliate sull'utilizzo di Lync Server Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="a38a4-122">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="a38a4-123">Configurare un provider di hosting nel server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a38a4-123">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="a38a4-124">Utilizzare Lync Server Management Shell per configurare un provider di hosting nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a38a4-124">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="a38a4-125">A tale scopo, eseguire il cmdlet **New-CsHostingProvider** , utilizzando i parametri nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a38a4-125">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="a38a4-126">Se si utilizza Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro <STRONG>ProxyFqdn</STRONG> in questo esempio ("exap.um.Outlook.com") con il nome di dominio completo per il servizio gestito da 21ViaNet: "exap.um.partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="a38a4-126">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="a38a4-127">**Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare (ad esempio, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="a38a4-127">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="a38a4-128">I valori che contengono spazi devono essere racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="a38a4-128">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="a38a4-129">**Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata.</span><span class="sxs-lookup"><span data-stu-id="a38a4-129">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="a38a4-130">Questa impostazione deve essere impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="a38a4-130">This must be set to **True**.</span></span>

  - <span data-ttu-id="a38a4-131">**EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="a38a4-131">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="a38a4-132">Questa impostazione deve essere impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="a38a4-132">This must be set to **True**.</span></span>

  - <span data-ttu-id="a38a4-133">**HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Office Communications Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a38a4-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="a38a4-134">Questo valore deve essere impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="a38a4-134">This must be set to **False**.</span></span>

  - <span data-ttu-id="a38a4-135">**ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="a38a4-135">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="a38a4-136">Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a38a4-136">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="a38a4-137">La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a38a4-137">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="a38a4-138">Questo valore deve essere impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="a38a4-138">This must be set to **False**.</span></span>

  - <span data-ttu-id="a38a4-139">**VerificationLevel** indica il livello di verifica consentito per i messaggi inviati e ricevuti dal provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="a38a4-139">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="a38a4-140">Specificare **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="a38a4-140">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="a38a4-141">Questa opzione si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="a38a4-141">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="a38a4-142">Se questo livello non viene specificato, il messaggio verrà rifiutato come non verificabile.</span><span class="sxs-lookup"><span data-stu-id="a38a4-142">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="a38a4-143">Verificare la replica dell'archivio di gestione centrale aggiornato</span><span class="sxs-lookup"><span data-stu-id="a38a4-143">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="a38a4-144">Le modifiche apportate utilizzando i cmdlet nelle sezioni precedenti vengono applicate automaticamente al server perimetrale e generalmente richiedono meno di un minuto per la replica.</span><span class="sxs-lookup"><span data-stu-id="a38a4-144">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="a38a4-145">È possibile verificare lo stato della replica e che le modifiche sono state applicate al server perimetrale utilizzando i cmdlet seguenti.</span><span class="sxs-lookup"><span data-stu-id="a38a4-145">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="a38a4-146">Per verificare gli aggiornamenti della replica su un server interno nella distribuzione di Lync Server, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a38a4-146">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="a38a4-147">Per verificare che le modifiche siano state applicate, eseguire il cmdlet seguente nel server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="a38a4-147">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a38a4-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a38a4-148">See Also</span></span>


[<span data-ttu-id="a38a4-149">Fornire ai messaggi vocali di Lync Server 2013 utenti la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="a38a4-149">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="a38a4-150">Integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a38a4-150">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
