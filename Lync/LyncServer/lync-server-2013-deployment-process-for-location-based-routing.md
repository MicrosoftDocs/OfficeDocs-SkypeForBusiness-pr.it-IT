---
title: 'Lync Server 2013: Processo di distribuzione per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="46026-102">Processo di distribuzione per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46026-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46026-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="46026-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="46026-104">Questo argomento offre una panoramica del processo relativo alla configurazione del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="46026-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="46026-105">È necessario distribuire Lync Server Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="46026-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="46026-106">I componenti necessari per il routing basato sulla posizione sono già installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="46026-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="46026-107">Processo di distribuzione del routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46026-108">Fase</span><span class="sxs-lookup"><span data-stu-id="46026-108">Phase</span></span></th>
<th><span data-ttu-id="46026-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="46026-109">Steps</span></span></th>
<th><span data-ttu-id="46026-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="46026-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="46026-111">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="46026-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-112">Distribuzione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="46026-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="46026-113">Configurare Trunks</span><span class="sxs-lookup"><span data-stu-id="46026-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="46026-114">Creare criteri vocali</span><span class="sxs-lookup"><span data-stu-id="46026-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="46026-115">Definire le route vocali</span><span class="sxs-lookup"><span data-stu-id="46026-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46026-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="46026-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="46026-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-117">CsAdministrator</span></span><br />
<span data-ttu-id="46026-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46026-119">Distribuzione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="46026-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46026-120">Verificare la distribuzione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="46026-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="46026-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="46026-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="46026-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-122">CsAdministrator</span></span><br />
<span data-ttu-id="46026-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46026-124">Configurare aree di rete, siti e subnet</span><span class="sxs-lookup"><span data-stu-id="46026-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="46026-125">Creare aree di rete</span><span class="sxs-lookup"><span data-stu-id="46026-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="46026-126">Creare siti di rete</span><span class="sxs-lookup"><span data-stu-id="46026-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="46026-127">Associa le subnet con i siti di rete</span><span class="sxs-lookup"><span data-stu-id="46026-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46026-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="46026-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="46026-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-129">CsAdministrator</span></span><br />
<span data-ttu-id="46026-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="46026-131">Informazioni sulle aree geografiche, i siti e le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="46026-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="46026-132">Creare o modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="46026-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="46026-133">Creare o modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="46026-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="46026-134">Associare una subnet a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="46026-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46026-135">Configurare il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="46026-136">Creare criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="46026-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="46026-137">Definire una configurazione trunk separata per tronco</span><span class="sxs-lookup"><span data-stu-id="46026-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="46026-138">Modificare i criteri vocali</span><span class="sxs-lookup"><span data-stu-id="46026-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="46026-139">Abilitare la configurazione del routing basata sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46026-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="46026-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="46026-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-141">CsAdministrator</span></span><br />
<span data-ttu-id="46026-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="46026-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="46026-143">Distribuzione di esempio</span><span class="sxs-lookup"><span data-stu-id="46026-143">Sample Deployment</span></span>

<span data-ttu-id="46026-144">La distribuzione seguente viene usata per illustrare ulteriormente i meccanismi abilitati dal routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="46026-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="46026-145">![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="46026-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="46026-146">Chiamate PSTN in arrivo</span><span class="sxs-lookup"><span data-stu-id="46026-146">Incoming PSTN calls</span></span>

<span data-ttu-id="46026-147">Un amministratore può abilitare il trunk definito per instradare le chiamate al "gateway del sito 1" per il routing basato sulla posizione e associare il "gateway del sito 1" al sito 1.</span><span class="sxs-lookup"><span data-stu-id="46026-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="46026-148">Una volta abilitata, le chiamate instradate tramite "gateway sito 1" verranno indirizzate solo agli utenti che si trovano nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="46026-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="46026-149">Tutte le chiamate instradate tramite il trunk "sito 1 gateway" destinato agli utenti in un sito diverso, ad esempio il sito 2, verranno bloccate per evitare il bypass PSTN.</span><span class="sxs-lookup"><span data-stu-id="46026-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="46026-150">Tutte le chiamate PSTN in arrivo tramite "sito 1 gateway" possono essere instradate solo agli endpoint presenti nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="46026-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="46026-151">Ad esempio, quando "Lync User 1" passa al sito 2, tutte le chiamate PSTN in arrivo tramite "sito 1 gateway" non verranno indirizzate agli endpoint "Lync User 1" presenti nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="46026-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="46026-152">La stessa regola di routing si applica se "Lync User 1" si sposta in un sito di rete sconosciuto in cui non è possibile determinare la posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="46026-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="46026-153">La tabella seguente illustra l'esperienza utente di "Lync User 1" in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="46026-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="46026-154">Endpoint degli utenti di Lync 1 situati nel sito di rete 1</span><span class="sxs-lookup"><span data-stu-id="46026-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="46026-155">Endpoint degli utenti di Lync 1 situati nel sito di rete 2</span><span class="sxs-lookup"><span data-stu-id="46026-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="46026-156">Endpoint di Lync User 1 situati nel sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="46026-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-157">Chiamate PSTN in ingresso per l'utente Lync 1</span><span class="sxs-lookup"><span data-stu-id="46026-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="46026-158">Le chiamate vengono instradate agli endpoint in questa posizione</span><span class="sxs-lookup"><span data-stu-id="46026-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="46026-159">Le chiamate non vengono instradate agli endpoint in questa posizione</span><span class="sxs-lookup"><span data-stu-id="46026-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="46026-160">Le chiamate non vengono instradate agli endpoint in questa posizione</span><span class="sxs-lookup"><span data-stu-id="46026-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="46026-161">Chiamate PSTN in uscita</span><span class="sxs-lookup"><span data-stu-id="46026-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="46026-162">Si fa riferimento a route vocali sia nei criteri vocali assegnati direttamente agli utenti, sia nei criteri di routing vocale assegnati ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="46026-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="46026-163">Entrambi i criteri contengono riferimenti alle route, che possono essere usati per instradare una chiamata in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="46026-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="46026-164">Un amministratore può ad esempio definire un criterio di routing vocale per tutti gli utenti che si trovano nel sito di rete 1 per instradare tutte le chiamate in uscita tramite il gateway "sito 1", mentre il criterio vocale di alcuni utenti definisce una route per tutte le chiamate in uscita tramite il "sito 2 gateway".</span><span class="sxs-lookup"><span data-stu-id="46026-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="46026-165">Mentre questi utenti si trovano nel sito di rete 1, le chiamate in uscita verranno instradate tramite il "gateway del sito 1".</span><span class="sxs-lookup"><span data-stu-id="46026-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="46026-166">Quando un utente si trova in un sito di rete configurato per il routing basato sulla posizione, la route dei criteri di routing vocale del sito di rete sostituisce la route dei criteri vocali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="46026-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="46026-167">Questa regola è particolarmente utile per gli utenti che si trasferiscono temporaneamente in un sito diverso.</span><span class="sxs-lookup"><span data-stu-id="46026-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="46026-168">In questo caso specifico un utente userà sempre un gateway locale nella propria posizione; Se "Lync User 3" si trova in "sito 2", tutte le sue chiamate in uscita verranno instradate tramite "gateway del sito 2", ma se si reca nel sito 1, tutte le chiamate in uscita inserite mentre è al sito 1 verranno instradate attraverso "sito 1 gateway".</span><span class="sxs-lookup"><span data-stu-id="46026-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="46026-169">La tabella seguente illustra l'esperienza utente di Lync User 1 che effettua una chiamata in uscita dai siti di rete seguenti.</span><span class="sxs-lookup"><span data-stu-id="46026-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="46026-170">Sito di rete 1</span><span class="sxs-lookup"><span data-stu-id="46026-170">Network site 1</span></span></th>
<th><span data-ttu-id="46026-171">Sito di rete 2</span><span class="sxs-lookup"><span data-stu-id="46026-171">Network site 2</span></span></th>
<th><span data-ttu-id="46026-172">Sito di rete sconosciuto o non abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-173">Autorizzazione delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="46026-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="46026-174">Criterio vocale di Lync User 1</span><span class="sxs-lookup"><span data-stu-id="46026-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="46026-175">Criterio vocale di Lync User 1</span><span class="sxs-lookup"><span data-stu-id="46026-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="46026-176">Criterio vocale di Lync User 1</span><span class="sxs-lookup"><span data-stu-id="46026-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46026-177">Routing delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="46026-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="46026-178">Criteri di routing vocale del sito 1</span><span class="sxs-lookup"><span data-stu-id="46026-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="46026-179">Criteri di routing vocale del sito 2</span><span class="sxs-lookup"><span data-stu-id="46026-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="46026-180">Criteri vocali dell'utente e solo per i sistemi non abilitati per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="46026-181">Trasferimento e inoltro delle chiamate</span><span class="sxs-lookup"><span data-stu-id="46026-181">Call transfers and forwards</span></span>

<span data-ttu-id="46026-182">Quando le chiamate vengono trasferite o inoltrate, il routing delle chiamate è influenzato dal routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="46026-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="46026-183">Nella tabella seguente viene illustrato l'utente di Lync 1 che trasferisce o inoltra una chiamata PSTN a un altro utente Lync.</span><span class="sxs-lookup"><span data-stu-id="46026-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46026-184">Utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="46026-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="46026-185">Utente di Lync 2</span><span class="sxs-lookup"><span data-stu-id="46026-185">Lync user 2</span></span></th>
<th><span data-ttu-id="46026-186">Utente di Lync 4</span><span class="sxs-lookup"><span data-stu-id="46026-186">Lync user 4</span></span></th>
<th><span data-ttu-id="46026-187">L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-188">Utente Lync 1</span><span class="sxs-lookup"><span data-stu-id="46026-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="46026-189">Inoltro di chiamata o trasferimento consentito</span><span class="sxs-lookup"><span data-stu-id="46026-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="46026-190">La chiamata inoltra o transfer non è consentita</span><span class="sxs-lookup"><span data-stu-id="46026-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="46026-191">La chiamata inoltra o transfer non è consentita</span><span class="sxs-lookup"><span data-stu-id="46026-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="46026-192">Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sulla modalità di instradamento della chiamata in base alla posizione dell'utente di Lync trasferito (Lync User 2, Lync User 4 e così via) in un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="46026-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46026-193">Endpoint in cui viene trasferita o inoltrata la chiamata a</span><span class="sxs-lookup"><span data-stu-id="46026-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="46026-194">Utente di Lync 2</span><span class="sxs-lookup"><span data-stu-id="46026-194">Lync user 2</span></span></th>
<th><span data-ttu-id="46026-195">Utente di Lync 4</span><span class="sxs-lookup"><span data-stu-id="46026-195">Lync user 4</span></span></th>
<th><span data-ttu-id="46026-196">L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-197">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="46026-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="46026-198">La chiamata inoltra o transfer viene instradato attraverso i criteri di routing vocale del sito 1 e l'uscita tramite gateway del sito 1</span><span class="sxs-lookup"><span data-stu-id="46026-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="46026-199">La chiamata inoltra o transfer viene instradato attraverso i criteri di routing vocale del sito 2 e l'uscita tramite gateway del sito 2</span><span class="sxs-lookup"><span data-stu-id="46026-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="46026-200">Inoltro di chiamata o trasferimento viene instradato tramite il criterio vocale dell'utente di Lync e l'uscita tramite un gateway non abilitato per il routing basato sulla posizione (se disponibile)</span><span class="sxs-lookup"><span data-stu-id="46026-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="46026-201">Squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="46026-201">Simultaneous ringing</span></span>

<span data-ttu-id="46026-202">Una volta configurato il routing basato sulla posizione nella topologia di esempio, vengono applicate le interazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="46026-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="46026-203">La tabella seguente illustra se il routing basato sulla posizione consente la chiamata simultanea per diversi utenti di Lync (ad esempio, Lync User 2, Lync User 4 e così via).</span><span class="sxs-lookup"><span data-stu-id="46026-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46026-204">Destinazione chiamata PSTN in arrivo</span><span class="sxs-lookup"><span data-stu-id="46026-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="46026-205">Utente di Lync 2</span><span class="sxs-lookup"><span data-stu-id="46026-205">Lync user 2</span></span></th>
<th><span data-ttu-id="46026-206">Utente di Lync 4</span><span class="sxs-lookup"><span data-stu-id="46026-206">Lync user 4</span></span></th>
<th><span data-ttu-id="46026-207">L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-208">Utente Lync 1</span><span class="sxs-lookup"><span data-stu-id="46026-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="46026-209">Squillo simultaneo consentito</span><span class="sxs-lookup"><span data-stu-id="46026-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="46026-210">Squillo simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="46026-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="46026-211">Squillo simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="46026-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="46026-212">La tabella seguente illustra se il routing basato sulla posizione consente la chiamata simultanea a un endpoint PSTN da diversi utenti di Lync, ad esempio Lync User 2, Lync User 4 e così via.</span><span class="sxs-lookup"><span data-stu-id="46026-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46026-213">Destinazione anello simultaneo</span><span class="sxs-lookup"><span data-stu-id="46026-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="46026-214">Utente di Lync 2</span><span class="sxs-lookup"><span data-stu-id="46026-214">Lync user 2</span></span></th>
<th><span data-ttu-id="46026-215">Utente di Lync 4</span><span class="sxs-lookup"><span data-stu-id="46026-215">Lync user 4</span></span></th>
<th><span data-ttu-id="46026-216">L'utente di Lync nel sito di rete non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46026-217">Lync utente 1 cellulare (endpoint PSTN)</span><span class="sxs-lookup"><span data-stu-id="46026-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="46026-218">Chiamata instradata tramite il criterio di routing vocale di Network site 1 e l'uscita tramite gateway del sito 1</span><span class="sxs-lookup"><span data-stu-id="46026-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="46026-219">Chiamata instradata tramite il criterio di routing vocale di Network site 2 e l'uscita tramite gateway del sito 2</span><span class="sxs-lookup"><span data-stu-id="46026-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="46026-220">Chiamata instradata tramite il criterio vocale chiamante ed è in uscita tramite un gateway PSTN non abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="46026-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46026-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46026-221">See Also</span></span>


[<span data-ttu-id="46026-222">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46026-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

