---
title: 'Lync Server 2013: requisiti per il routing in base alla posizione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="275a6-102">Requisiti per il routing in base alla posizione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="275a6-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="275a6-103">_**Ultimo argomento modificato:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="275a6-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="275a6-104">Di seguito sono riportati i requisiti necessari per l'installazione e la configurazione dell'applicazione per le conferenze di routing basata sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="275a6-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="275a6-105">L'aggiornamento cumulativo 2 di Lync Server 2013 deve essere distribuito in tutti i server o pool della topologia.</span><span class="sxs-lookup"><span data-stu-id="275a6-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="275a6-106">Se un server o un pool di Lync nella topologia non dispone di un aggiornamento cumulativo 2 o superiore di Lync Server 2013 installato, non è possibile garantire l'applicazione del routing basato sulla posizione delle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="275a6-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="275a6-107">Il routing in base alla posizione di Lync Server 2013 è prerequisito per l'applicazione di conferenza di routing basata sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="275a6-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="275a6-108">Per ulteriori informazioni sulla configurazione del routing in base alla posizione di Lync Server 2013, fare riferimento a [configurazione del routing in base alla posizione](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="275a6-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="275a6-109">I requisiti dell'applicazione per le conferenze di routing in base alla posizione sono gli stessi dei requisiti per il routing in base alla posizione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="275a6-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="275a6-110">Per ulteriori informazioni, fare riferimento alla [pianificazione del routing in base alla posizione](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="275a6-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="275a6-111">Server supportati</span><span class="sxs-lookup"><span data-stu-id="275a6-111">Supported Servers</span></span>

<span data-ttu-id="275a6-112">L'applicazione per le conferenze di routing basata sul percorso richiede che Lync Server 2013 Cumulative Update 2 sia distribuito in tutti i pool Front-end e server Standard Edition nella topologia.</span><span class="sxs-lookup"><span data-stu-id="275a6-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="275a6-113">Se Lync Server 2013 Cumulative Update 2 non è installato in alcuni server Lync nella topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente alle riunioni di Lync e ai trasferimenti di chiamata consultiva.</span><span class="sxs-lookup"><span data-stu-id="275a6-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="275a6-114">La tabella seguente identifica la combinazione dei ruoli del server e delle versioni che supportano il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="275a6-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="275a6-115">Versione pool Front-End</span><span class="sxs-lookup"><span data-stu-id="275a6-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="275a6-116">Versione Mediation Server</span><span class="sxs-lookup"><span data-stu-id="275a6-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="275a6-117">Supportato</span><span class="sxs-lookup"><span data-stu-id="275a6-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="275a6-118">Lync Server 2013 aggiornamento cumulativo 2</span><span class="sxs-lookup"><span data-stu-id="275a6-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="275a6-119">Lync Server 2013 aggiornamento cumulativo 2</span><span class="sxs-lookup"><span data-stu-id="275a6-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="275a6-120">Sì</span><span class="sxs-lookup"><span data-stu-id="275a6-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="275a6-121">Lync Server 2013 aggiornamento cumulativo 2</span><span class="sxs-lookup"><span data-stu-id="275a6-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="275a6-122">Lync Server 2013 aggiornamento cumulativo 1</span><span class="sxs-lookup"><span data-stu-id="275a6-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="275a6-123">No</span><span class="sxs-lookup"><span data-stu-id="275a6-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="275a6-124">Lync Server 2013 aggiornamento cumulativo 2</span><span class="sxs-lookup"><span data-stu-id="275a6-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="275a6-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="275a6-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="275a6-126">No</span><span class="sxs-lookup"><span data-stu-id="275a6-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="275a6-127">Lync Server 2013 aggiornamento cumulativo 2</span><span class="sxs-lookup"><span data-stu-id="275a6-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="275a6-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="275a6-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="275a6-129">No</span><span class="sxs-lookup"><span data-stu-id="275a6-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="275a6-130">Lync Server 2013 aggiornamento cumulativo 1</span><span class="sxs-lookup"><span data-stu-id="275a6-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="275a6-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="275a6-131">Any</span></span></p></td>
<td><p><span data-ttu-id="275a6-132">No</span><span class="sxs-lookup"><span data-stu-id="275a6-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="275a6-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="275a6-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="275a6-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="275a6-134">Any</span></span></p></td>
<td><p><span data-ttu-id="275a6-135">No</span><span class="sxs-lookup"><span data-stu-id="275a6-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="275a6-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="275a6-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="275a6-137">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="275a6-137">Any</span></span></p></td>
<td><p><span data-ttu-id="275a6-138">No</span><span class="sxs-lookup"><span data-stu-id="275a6-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="275a6-139">Client supportati</span><span class="sxs-lookup"><span data-stu-id="275a6-139">Supported Clients</span></span>

<span data-ttu-id="275a6-140">I client Lync che supportano il routing in base alla posizione delle riunioni di Lync sono gli stessi client che supportano il routing in base alla posizione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="275a6-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="275a6-141">Per ulteriori informazioni, fare riferimento al [supporto per client e server per il routing in base alla posizione](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="275a6-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="275a6-142">Requisiti di Mediation Server per i trasferimenti di chiamata consultiva</span><span class="sxs-lookup"><span data-stu-id="275a6-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="275a6-143">L'applicazione per le conferenze di routing in base alla posizione richiede la distribuzione di Mediation Server autonomi per applicare restrizioni di routing basate sul percorso nei trasferimenti di chiamata consultiva.</span><span class="sxs-lookup"><span data-stu-id="275a6-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="275a6-144">Per applicare il routing in base alla posizione dei trasferimenti di chiamata consultiva, è necessario che il Mediation Server sia associato a un solo peer Mediation Server (ad esempio PBX, gateway SIP e così via) nelle aree di rete in cui è necessario il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="275a6-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="275a6-145">Se sono distribuiti altri peer di Mediation Server nella stessa area di rete, è necessario che il peer Mediation Server sia associato a un Mediation Server diverso.</span><span class="sxs-lookup"><span data-stu-id="275a6-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="275a6-146">Questo requisito è dettagliato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="275a6-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="275a6-147">Singolo Mediation Server per più peer di Mediation Server quando un trasferimento di chiamata consultivo viene instradato a un peer di Mediation Server tramite un Mediation Server configurato con più trunk SIP su più peer (ad esempio, PBX e gateway), la consultazione il trasferimento di chiamata è bloccato per impedire il bypass a pedaggio PSTN se il trasferimento delle chiamate consultive è consentito tramite alcuni trunk SIP ma non consentito tramite altri trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="275a6-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="275a6-148">Ad esempio, nel caso di un singolo Mediation Server per la manutenzione di un peer di Mediation Server gateway PSTN e di un peer di Mediation Server PBX, si osserverà il comportamento seguente:</span><span class="sxs-lookup"><span data-stu-id="275a6-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="275a6-149">Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="275a6-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="275a6-150">Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non è consentita anche se non si trova in un potenziale Tol PSTN l bypassare.</span><span class="sxs-lookup"><span data-stu-id="275a6-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="275a6-151">Mediation Server distinti per peer di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="275a6-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="275a6-152">Quando un trasferimento consultivo è destinato a un peer di Mediation Server, il trasferimento consultivo verrà valutato rispetto al peer di Mediation Server singolo gestito dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="275a6-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="275a6-153">La chiamata non è consentita o consentita in base alle sue potenzialità di incorrere in un bypass a pedaggio PSTN indipendentemente da tutti gli altri peer del server di Mediation nel sito in cui sono serviti da server Mediation distinti.</span><span class="sxs-lookup"><span data-stu-id="275a6-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="275a6-154">Ad esempio, nel caso di un Mediation Server separato per la manutenzione di un peer di Mediation Server gateway PSTN e di un peer di Mediation Server PBX, si osserverà il comportamento seguente:</span><span class="sxs-lookup"><span data-stu-id="275a6-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="275a6-155">Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="275a6-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="275a6-156">Quando un utente di Lync proveniente da un determinato sito (ovvero il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync proveniente da un sito diverso (ovvero il sito 2) tramite il trasferimento consultivo, la chiamata sarà consentita perché non si trova in un eventuale bypass a pedaggio PSTN. conoscenza.</span><span class="sxs-lookup"><span data-stu-id="275a6-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="275a6-157">Funzionalità non supportate dall'applicazione per le conferenze di routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="275a6-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="275a6-158">Le funzionalità seguenti non sono supportate dall'applicazione per le conferenze di routing in base alla posizione:</span><span class="sxs-lookup"><span data-stu-id="275a6-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="275a6-159">Servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="275a6-159">Dial-in conferencing.</span></span> <span data-ttu-id="275a6-160">Impossibile applicare il routing in base alla posizione per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="275a6-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="275a6-161">Qualsiasi richiesta di accesso esterno a una determinata conferenza non verrà limitata dal routing basato sulla posizione anche se l'organizzatore di conferenze è un utente di Lync abilitato per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="275a6-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="275a6-162">È consigliabile non eseguire il provisioning dei numeri di accesso per le conferenze nelle aree in cui devono essere applicate restrizioni di routing basate sul percorso.</span><span class="sxs-lookup"><span data-stu-id="275a6-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

