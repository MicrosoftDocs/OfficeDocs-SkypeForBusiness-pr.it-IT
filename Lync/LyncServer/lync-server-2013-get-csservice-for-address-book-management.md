---
title: 'Lync Server 2013: Get-CsService per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656c1aa545a1f10e49c5ff60b51c20386854d146
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="a5347-102">Get-CsService per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5347-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5347-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a5347-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a5347-104">Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet Get-CsService: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a5347-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="a5347-105">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a5347-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="a5347-106">Get-CsService è utile per recuperare e visualizzare la configurazione corrente dei servizi Web definiti dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="a5347-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="a5347-107">Definendo il nome di dominio completo (FQDN) del pool e il parametro WebServer, il cmdlet restituisce i servizi basati sul Web offerti dal server, inclusi il gestore della Rubrica e gli URI di espansione della lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a5347-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="a5347-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5347-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="a5347-109">Questo cmdlet restituisce i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="a5347-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="a5347-110">Identità: WebServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="a5347-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="a5347-111">Filestore: FileStore:DC01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="a5347-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="a5347-112">UserServer: UserServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="a5347-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="a5347-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="a5347-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="a5347-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="a5347-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="a5347-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="a5347-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="a5347-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="a5347-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="a5347-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="a5347-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="a5347-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="a5347-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="a5347-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="a5347-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="a5347-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="a5347-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="a5347-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="a5347-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="a5347-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="a5347-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="a5347-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="a5347-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="a5347-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="a5347-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="a5347-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="a5347-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="a5347-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="a5347-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="a5347-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="a5347-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="a5347-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="a5347-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="a5347-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="a5347-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="a5347-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="a5347-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="a5347-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="a5347-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="a5347-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="a5347-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="a5347-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="a5347-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="a5347-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="a5347-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="a5347-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="a5347-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="a5347-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="a5347-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="a5347-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="a5347-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="a5347-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="a5347-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="a5347-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="a5347-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="a5347-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="a5347-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="a5347-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="a5347-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="a5347-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="a5347-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="a5347-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="a5347-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5347-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="a5347-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a5347-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="a5347-150">DependentServiceList: {Registrar:pool01. contoso. NET, ConferencingServer:pool01. contoso. NET}</span><span class="sxs-lookup"><span data-stu-id="a5347-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="a5347-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="a5347-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="a5347-152">SiteId: sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="a5347-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="a5347-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a5347-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="a5347-154">Versione: 5</span><span class="sxs-lookup"><span data-stu-id="a5347-154">Version : 5</span></span>

<span data-ttu-id="a5347-155">Ruolo: webserver</span><span class="sxs-lookup"><span data-stu-id="a5347-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a5347-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5347-156">See Also</span></span>


[<span data-ttu-id="a5347-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="a5347-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

