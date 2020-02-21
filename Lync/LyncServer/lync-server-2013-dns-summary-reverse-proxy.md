---
title: 'Lync Server 2013: Riepilogo di DNS-proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5f79437c5253365e4333e7cd064883bba968a54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="5cb9a-102">Riepilogo DNS-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cb9a-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cb9a-103">_**Ultimo argomento modificato:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="5cb9a-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="5cb9a-104">È possibile configurare due schede di rete all'interno del proxy inverso in questo modo:</span><span class="sxs-lookup"><span data-stu-id="5cb9a-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="5cb9a-105">Requisiti relativi alla scheda di rete per proxy inverso</span><span class="sxs-lookup"><span data-stu-id="5cb9a-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="5cb9a-106">Esempio di **scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="5cb9a-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="5cb9a-107">Interfaccia interna con indirizzo 172.25.33.40 assegnato.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="5cb9a-108">Nessun gateway predefinito definito.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="5cb9a-109">Verificare che esista una route dalla rete che contiene l'interfaccia interna del proxy inverso a qualsiasi rete che contiene server del pool Front End di Lync Server (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="5cb9a-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="5cb9a-110">Esempio di **scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="5cb9a-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="5cb9a-111">A questa scheda di rete viene assegnato almeno un indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="5cb9a-p101">Il gateway viene definito in modo da puntare al router o al firewall integrato nel perimetro esterno (10.45.16.1 in questi esempi di scenario).</span><span class="sxs-lookup"><span data-stu-id="5cb9a-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="5cb9a-114">Record DNS necessari per il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="5cb9a-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cb9a-115">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="5cb9a-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5cb9a-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="5cb9a-116">FQDN</span></span></th>
<th><span data-ttu-id="5cb9a-117">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="5cb9a-117">IP address</span></span></th>
<th><span data-ttu-id="5cb9a-118">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="5cb9a-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cb9a-119">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="5cb9a-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cb9a-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-121">Listener assegnato per risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-p102">Servizi Web esterni dalla distribuzione interna. È possibile definire e creare altri record per tutti i pool e singoli server per un dominio SIP che userà questo proxy inverso e dispone di servizi Web esterni definiti.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cb9a-124">DNS/A esterno</span><span class="sxs-lookup"><span data-stu-id="5cb9a-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cb9a-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-126">Listener assegnato per risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-127">Servizi Web esterni per i direttori o i pool di server Director nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="5cb9a-128">È possibile definire il numero di amministratori che sono direttori distinti, di cui possono essere associati ad altri domini SIP.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5cb9a-129">La definizione dei record DNS per e la pubblicazione dei direttori non è una decisione del pool Front end o del Director.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="5cb9a-130">Se si utilizzano i Director, è necessario definire e pubblicare sia il server Director che i servizi Web esterni del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="5cb9a-131">I tipi di traffico specifici (per l'autenticazione e altri utilizzi) verranno inviati prima al server Director, se definito nella topologia.</span><span class="sxs-lookup"><span data-stu-id="5cb9a-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cb9a-132">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="5cb9a-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cb9a-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-134">Listener assegnato per risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-135">Conferenza telefonica con accesso remoto pubblicata esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cb9a-136">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="5cb9a-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cb9a-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-138">Listener assegnato per risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-139">Conferenze pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cb9a-140">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="5cb9a-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cb9a-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-142">Listener assegnato per il server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="5cb9a-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-143">Server Office Web Apps distribuito internamente o nel perimetro e pubblicato per l'accesso client esterno</span><span class="sxs-lookup"><span data-stu-id="5cb9a-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cb9a-144">DNS/A esterno</span><span class="sxs-lookup"><span data-stu-id="5cb9a-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cb9a-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-146">Listener assegnato per risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="5cb9a-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5cb9a-147">Record esterno di individuazione di Lync per l'individuazione automatica pubblicata esternamente e include mobilità, Microsoft Lync Web App e Scheduler Web App</span><span class="sxs-lookup"><span data-stu-id="5cb9a-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

