---
title: 'Lync Server 2013: Riepilogo di DNS - proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="e0647-102">Riepilogo di DNS - proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0647-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0647-103">_**Argomento Ultima modifica:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="e0647-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="e0647-104">Si configurano due schede di rete nel proxy inverso, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e0647-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="e0647-105">Requisiti della scheda di rete proxy inverso</span><span class="sxs-lookup"><span data-stu-id="e0647-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="e0647-106">Esempio di **scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="e0647-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="e0647-107">Interfaccia interna con 172.25.33.40 assegnati.</span><span class="sxs-lookup"><span data-stu-id="e0647-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="e0647-108">Nessun gateway predefinito è definito.</span><span class="sxs-lookup"><span data-stu-id="e0647-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="e0647-109">Verificare che esista una route dalla rete che contiene l'interfaccia interna del proxy inverso a tutte le reti che contengono i server del pool Front-End di Lync Server, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="e0647-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="e0647-110">Esempio di **scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="e0647-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="e0647-111">Alla scheda di rete viene assegnato un minimo di un indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="e0647-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="e0647-112">Il gateway viene definito in punti al router o al firewall integrato nel perimetro esterno.</span><span class="sxs-lookup"><span data-stu-id="e0647-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="e0647-113">(10.45.16.1 negli esempi di scenario)</span><span class="sxs-lookup"><span data-stu-id="e0647-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="e0647-114">Record DNS necessari per il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="e0647-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0647-115">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="e0647-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e0647-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="e0647-116">FQDN</span></span></th>
<th><span data-ttu-id="e0647-117">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="e0647-117">IP address</span></span></th>
<th><span data-ttu-id="e0647-118">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="e0647-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0647-119">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="e0647-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0647-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0647-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0647-121">Listener assegnato per le risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="e0647-122">Servizi Web esterni dalla distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e0647-122">External web services from the internal deployment.</span></span> <span data-ttu-id="e0647-123">È possibile definire e creare record aggiuntivi per tutti i pool e i singoli server per qualsiasi dominio SIP che utilizzerà questo proxy inverso e ha definito servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="e0647-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0647-124">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="e0647-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0647-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0647-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0647-126">Listener assegnato per le risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="e0647-127">Servizi Web esterni per i pool di direttori o di Director nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0647-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="e0647-128">Puoi definire il numero di amministratori che ci sono direttori distinti, di cui possono essere associati ad altri domini SIP.</span><span class="sxs-lookup"><span data-stu-id="e0647-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="e0647-129">La definizione dei record DNS per la pubblicazione dei direttori non è un pool di front end o la decisione del direttore.</span><span class="sxs-lookup"><span data-stu-id="e0647-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="e0647-130">Se si usano gli amministratori, è necessario definire e pubblicare sia il Director che i servizi Web esterni del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="e0647-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="e0647-131">I tipi di traffico specifici (per l'autenticazione e altri usi) verranno inviati prima al Director, se sono definiti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="e0647-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0647-132">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="e0647-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0647-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0647-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0647-134">Listener assegnato per le risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="e0647-135">Servizi di conferenza telefonica con accesso esterno pubblicati esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0647-136">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="e0647-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0647-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0647-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0647-138">Listener assegnato per le risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="e0647-139">Conferenze pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0647-140">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="e0647-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0647-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0647-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0647-142">Listener assegnato per Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="e0647-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="e0647-143">Server Office Web Apps distribuito internamente o nel perimetro e pubblicato per l'accesso client esterno</span><span class="sxs-lookup"><span data-stu-id="e0647-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0647-144">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="e0647-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0647-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0647-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0647-146">Listener assegnato per le risorse pubblicate esternamente</span><span class="sxs-lookup"><span data-stu-id="e0647-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="e0647-147">Lync scopre il record esterno per l'individuazione automatica pubblicata esternamente e include mobilità, Microsoft Lync Web App e Scheduler Web App</span><span class="sxs-lookup"><span data-stu-id="e0647-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

