---
title: 'Lync Server 2013: Get-CsService per la gestione della Rubrica'
description: 'Lync Server 2013: Get-CsService per la gestione della Rubrica.'
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
ms.openlocfilehash: 5e46173429988d87022c13fab33e3778279dd0e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554652"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="12312-103">Get-CsService per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12312-103">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12312-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12312-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12312-p101">Chi può eseguire questo cmdlet: per impostazione predefinita, sono autorizzati a eseguire localmente il cmdlet Get-CsService i membri dei gruppi seguenti: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di Controllo dell'accesso basato sui ruoli (RBAC) a cui tale cmdlet è stato assegnato, inclusi i ruoli RBAC personalizzati creati personalmente, al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="12312-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="12312-107">Get-CsService è utile per recuperare e visualizzare la configurazione corrente dei servizi Web definiti dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="12312-107">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="12312-108">Definendo il nome di dominio completo (FQDN) del pool e il parametro WebServer, il cmdlet restituisce i servizi basati sul Web offerti dal server, inclusi il gestore della Rubrica e gli URI di espansione delle liste di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12312-108">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="12312-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="12312-109">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="12312-110">Questo cmdlet restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="12312-110">This cmdlet returns the following:</span></span>

<span data-ttu-id="12312-111">Identità: WebServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="12312-111">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="12312-112">Filestore: FileStore:DC01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="12312-112">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="12312-113">UserServer: UserServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="12312-113">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="12312-114">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="12312-114">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="12312-115">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="12312-115">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="12312-116">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="12312-116">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="12312-117">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="12312-117">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="12312-118">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="12312-118">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="12312-119">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="12312-119">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="12312-120">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="12312-120">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="12312-121">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="12312-121">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="12312-122">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="12312-122">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="12312-123">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="12312-123">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="12312-124">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="12312-124">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="12312-125">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="12312-125">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="12312-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="12312-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="12312-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="12312-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="12312-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="12312-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="12312-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="12312-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="12312-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="12312-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="12312-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="12312-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="12312-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="12312-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="12312-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="12312-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="12312-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="12312-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="12312-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="12312-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="12312-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="12312-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="12312-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="12312-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="12312-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="12312-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="12312-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="12312-142">MeetExternalUri : https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="12312-142">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="12312-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="12312-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="12312-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="12312-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="12312-145">ReachExternalUri : https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="12312-145">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="12312-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="12312-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="12312-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="12312-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="12312-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="12312-149">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12312-149">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="12312-150">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="12312-150">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="12312-151">DependentServiceList: {Registrar:pool01. contoso. NET, ConferencingServer:pool01. contoso. NET}</span><span class="sxs-lookup"><span data-stu-id="12312-151">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="12312-152">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="12312-152">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="12312-153">SiteId: sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="12312-153">SiteId : Site:Redmond</span></span>

<span data-ttu-id="12312-154">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="12312-154">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="12312-155">Versione: 5</span><span class="sxs-lookup"><span data-stu-id="12312-155">Version : 5</span></span>

<span data-ttu-id="12312-156">Ruolo: webserver</span><span class="sxs-lookup"><span data-stu-id="12312-156">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="12312-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12312-157">See Also</span></span>


[<span data-ttu-id="12312-158">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="12312-158">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

