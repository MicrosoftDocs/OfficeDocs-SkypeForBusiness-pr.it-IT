---
title: 'Lync Server 2013: requisiti per il routing basato sulla posizione per i servizi di conferenza'
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
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="6af12-102">Requisiti per il routing basato sulla posizione per i servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af12-103">_**Argomento Ultima modifica:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="6af12-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="6af12-104">Di seguito sono riportati i requisiti necessari per l'installazione e la configurazione dell'applicazione di conferenza di routing basata sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="6af12-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="6af12-105">L'aggiornamento cumulativo 2 di Lync Server 2013 deve essere distribuito in tutti i server o i pool della topologia.</span><span class="sxs-lookup"><span data-stu-id="6af12-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6af12-106">Se un server o un pool di Lync nella topologia non ha installato Lync Server 2013 aggiornamento cumulativo 2 o versione successiva, non è possibile garantire l'applicazione del routing basato sulla posizione delle riunioni Lync.</span><span class="sxs-lookup"><span data-stu-id="6af12-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="6af12-107">Il routing basato sulla posizione di Lync Server 2013 è un requisito predefinito per l'applicazione di conferenza di routing basata sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6af12-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="6af12-108">Per altre informazioni sulla configurazione del routing basato sulla posizione di Lync Server 2013, vedere [configurazione del routing basato sulla posizione](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6af12-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="6af12-109">I requisiti dell'applicazione per i servizi di conferenza di routing basati sulla posizione corrispondono ai requisiti per il routing basato sulla posizione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af12-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="6af12-110">Per altre informazioni, vedere [pianificazione per il routing basato sulla posizione](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6af12-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="6af12-111">Server supportati</span><span class="sxs-lookup"><span data-stu-id="6af12-111">Supported Servers</span></span>

<span data-ttu-id="6af12-112">L'applicazione per i servizi di conferenza di routing basata sulla posizione richiede che l'aggiornamento cumulativo 2 di Lync Server 2013 sia distribuito in tutti i pool Front-end e nei server Standard Edition della topologia.</span><span class="sxs-lookup"><span data-stu-id="6af12-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="6af12-113">Se l'aggiornamento cumulativo 2 di Lync Server 2013 non è installato in alcuni server Lync della topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente alle riunioni di Lync e ai trasferimenti delle chiamate consultive.</span><span class="sxs-lookup"><span data-stu-id="6af12-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="6af12-114">La tabella seguente identifica la combinazione di ruoli server e versioni che supportano il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6af12-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6af12-115">Versione pool Front-End</span><span class="sxs-lookup"><span data-stu-id="6af12-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="6af12-116">Versione Mediation Server</span><span class="sxs-lookup"><span data-stu-id="6af12-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="6af12-117">Supportati</span><span class="sxs-lookup"><span data-stu-id="6af12-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af12-118">Aggiornamento cumulativo 2 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6af12-119">Aggiornamento cumulativo 2 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6af12-120">Sì</span><span class="sxs-lookup"><span data-stu-id="6af12-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af12-121">Aggiornamento cumulativo 2 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6af12-122">Aggiornamento cumulativo 1 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="6af12-123">No</span><span class="sxs-lookup"><span data-stu-id="6af12-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af12-124">Aggiornamento cumulativo 2 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6af12-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6af12-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6af12-126">No</span><span class="sxs-lookup"><span data-stu-id="6af12-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af12-127">Aggiornamento cumulativo 2 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6af12-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6af12-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6af12-129">No</span><span class="sxs-lookup"><span data-stu-id="6af12-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af12-130">Aggiornamento cumulativo 1 di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af12-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="6af12-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="6af12-131">Any</span></span></p></td>
<td><p><span data-ttu-id="6af12-132">No</span><span class="sxs-lookup"><span data-stu-id="6af12-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af12-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6af12-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6af12-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="6af12-134">Any</span></span></p></td>
<td><p><span data-ttu-id="6af12-135">No</span><span class="sxs-lookup"><span data-stu-id="6af12-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af12-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6af12-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6af12-137">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="6af12-137">Any</span></span></p></td>
<td><p><span data-ttu-id="6af12-138">No</span><span class="sxs-lookup"><span data-stu-id="6af12-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="6af12-139">Client supportati</span><span class="sxs-lookup"><span data-stu-id="6af12-139">Supported Clients</span></span>

<span data-ttu-id="6af12-140">I client Lync che supportano il routing basato sulla posizione delle riunioni Lync sono gli stessi client che supportano il routing basato sulla posizione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af12-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="6af12-141">Per altre informazioni, fare riferimento al [supporto client e server per il routing basato sulla posizione](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6af12-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="6af12-142">Requisiti di Mediation Server per i trasferimenti di chiamate consultive</span><span class="sxs-lookup"><span data-stu-id="6af12-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="6af12-143">L'applicazione per i servizi di conferenza di routing basata sulla posizione richiede la distribuzione di server di mediazione autonomi per applicare restrizioni di routing basate sul percorso per i trasferimenti di chiamate consultive.</span><span class="sxs-lookup"><span data-stu-id="6af12-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="6af12-144">Per applicare il routing basato sulla posizione dei trasferimenti delle chiamate consultive, il Mediation Server deve essere associato a un solo peer di Mediation Server (ad esempio PBX, gateway SIP e così via) nelle aree di rete in cui è necessario un routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6af12-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="6af12-145">Se altri peer di Mediation Server vengono distribuiti nella stessa area di rete, il peer di Mediation Server deve essere associato a un Mediation Server diverso.</span><span class="sxs-lookup"><span data-stu-id="6af12-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="6af12-146">Questo requisito è dettagliato come segue:</span><span class="sxs-lookup"><span data-stu-id="6af12-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="6af12-147">Singolo Mediation Server per più peer di Mediation Server quando un trasferimento di una chiamata consultiva viene indirizzato a un peer di Mediation Server tramite un Mediation Server configurato con più trunk SIP in più peer (ad esempio, PBX e gateway), le consultazioni il trasferimento delle chiamate è bloccato per evitare l'esclusione del pedaggio PSTN se il trasferimento delle chiamate consultive è consentito tramite alcuni trunk SIP ma non è consentito tramite altri trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="6af12-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="6af12-148">Ad esempio, nel caso di un singolo Mediation Server che assiste un peer del gateway PSTN Mediation Server e un peer di Mediation Server PBX, verrà osservato il comportamento seguente:</span><span class="sxs-lookup"><span data-stu-id="6af12-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="6af12-149">Quando un utente di Lync proveniente da un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire l'esclusione del pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="6af12-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="6af12-150">Quando un utente di Lync di un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata non è consentita, anche se non si trova in un potenziale Tol PSTN l bypassando.</span><span class="sxs-lookup"><span data-stu-id="6af12-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="6af12-151">Separare i server di mediazione per peer di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="6af12-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="6af12-152">Quando un trasferimento consultivo è destinato a un peer di Mediation Server, il trasferimento consultivo verrà valutato in base al peer di mediazione server singolo gestito dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="6af12-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="6af12-153">La chiamata non è consentita o consentita in base alle sue potenzialità di incorrere in un telepedaggio PSTN indipendentemente da tutti gli altri peer del server di mediazioni nel sito mentre vengono serviti da server di mediazione distinti.</span><span class="sxs-lookup"><span data-stu-id="6af12-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="6af12-154">Ad esempio, nel caso di un server di mediazione separato che assiste un peer di mediazione del gateway PSTN e un peer di Mediation Server PBX, verrà osservato il comportamento seguente:</span><span class="sxs-lookup"><span data-stu-id="6af12-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="6af12-155">Quando un utente di Lync proveniente da un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PSTN a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata non sarà consentita per impedire l'esclusione del pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="6af12-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="6af12-156">Quando un utente di Lync proveniente da un sito specifico (ad esempio il sito 1) tenta di trasferire una chiamata con un endpoint PBX nello stesso sito (sito 1) a un utente di Lync da un sito diverso (ad esempio il sito 2) tramite il trasferimento consultivo, la chiamata sarà consentita perché non viene incorrere in un eventuale bypass a pedaggio PSTN Ing.</span><span class="sxs-lookup"><span data-stu-id="6af12-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="6af12-157">Funzionalità non supportate dall'applicazione per i servizi di conferenza di routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="6af12-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="6af12-158">Le funzionalità seguenti non sono supportate dall'applicazione di conferenza di routing basata sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="6af12-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="6af12-159">Servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6af12-159">Dial-in conferencing.</span></span> <span data-ttu-id="6af12-160">Il routing basato sulla posizione non può essere applicato per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6af12-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="6af12-161">Qualsiasi richiesta di accesso esterno a una conferenza specificata non verrà limitata dal routing basato sulla posizione, anche se l'organizzatore di conferenze è un utente di Lync abilitato per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6af12-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="6af12-162">È consigliabile non eseguire il provisioning di numeri di accesso alle conferenze nelle aree in cui devono essere applicate restrizioni di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6af12-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

