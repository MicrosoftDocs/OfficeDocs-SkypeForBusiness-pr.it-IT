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
ms.openlocfilehash: 8d41d0d3fe8960f286cfe9bed1f27ae08d43c9fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="26a29-102">Get-CsService per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26a29-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26a29-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="26a29-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="26a29-p101">Chi può eseguire questo cmdlet: per impostazione predefinita, sono autorizzati a eseguire localmente il cmdlet Get-CsService i membri dei gruppi seguenti: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di Controllo dell'accesso basato sui ruoli (RBAC) a cui tale cmdlet è stato assegnato, inclusi i ruoli RBAC personalizzati creati personalmente, al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="26a29-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="26a29-106">Get-CsService è utile per recuperare e visualizzare la configurazione corrente dei servizi Web definiti dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="26a29-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="26a29-107">Definendo il nome di dominio completo (FQDN) del pool e il parametro WebServer, il cmdlet restituisce i servizi basati sul Web offerti dal server, inclusi il gestore della Rubrica e gli URI di espansione delle liste di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="26a29-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="26a29-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="26a29-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="26a29-109">Questo cmdlet restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="26a29-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="26a29-110">Identità: WebServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="26a29-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="26a29-111">Filestore: FileStore:DC01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="26a29-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="26a29-112">UserServer: UserServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="26a29-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="26a29-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="26a29-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="26a29-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="26a29-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="26a29-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="26a29-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="26a29-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="26a29-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="26a29-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="26a29-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="26a29-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="26a29-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="26a29-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="26a29-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="26a29-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="26a29-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="26a29-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="26a29-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="26a29-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="26a29-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="26a29-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="26a29-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="26a29-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="26a29-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="26a29-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="26a29-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="26a29-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="26a29-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="26a29-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="26a29-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="26a29-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="26a29-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="26a29-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="26a29-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="26a29-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="26a29-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="26a29-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="26a29-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="26a29-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="26a29-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="26a29-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="26a29-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="26a29-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="26a29-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="26a29-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="26a29-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="26a29-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="26a29-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="26a29-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="26a29-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="26a29-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="26a29-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="26a29-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="26a29-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="26a29-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="26a29-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="26a29-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="26a29-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="26a29-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="26a29-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="26a29-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="26a29-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26a29-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="26a29-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="26a29-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="26a29-150">DependentServiceList: {Registrar:pool01. contoso. NET, ConferencingServer:pool01. contoso. NET}</span><span class="sxs-lookup"><span data-stu-id="26a29-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="26a29-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="26a29-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="26a29-152">SiteId: sito: Redmond</span><span class="sxs-lookup"><span data-stu-id="26a29-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="26a29-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="26a29-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="26a29-154">Versione: 5</span><span class="sxs-lookup"><span data-stu-id="26a29-154">Version : 5</span></span>

<span data-ttu-id="26a29-155">Ruolo: webserver</span><span class="sxs-lookup"><span data-stu-id="26a29-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="26a29-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26a29-156">See Also</span></span>


[<span data-ttu-id="26a29-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="26a29-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

