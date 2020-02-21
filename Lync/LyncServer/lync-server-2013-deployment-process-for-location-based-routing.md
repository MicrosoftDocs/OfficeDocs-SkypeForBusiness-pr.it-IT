---
title: 'Lync Server 2013: processo di distribuzione per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08def9741ad6ba4f91759e88a38fccdea0d44333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="52491-102">Processo di distribuzione per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52491-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52491-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="52491-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="52491-104">In questo argomento viene fornita una panoramica del processo di configurazione del routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="52491-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="52491-105">Prima di configurare il routing in base alla posizione, è necessario distribuire Lync Server Enterprise Edition o Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="52491-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="52491-106">I componenti necessari per il routing in base alla posizione sono già installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="52491-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="52491-107">Processo di distribuzione del routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52491-108">Fase</span><span class="sxs-lookup"><span data-stu-id="52491-108">Phase</span></span></th>
<th><span data-ttu-id="52491-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="52491-109">Steps</span></span></th>
<th><span data-ttu-id="52491-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="52491-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="52491-111">Documentazione sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="52491-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-112">Distribuzione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="52491-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="52491-113">Configurare trunk</span><span class="sxs-lookup"><span data-stu-id="52491-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="52491-114">Creare criteri vocali</span><span class="sxs-lookup"><span data-stu-id="52491-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="52491-115">Definire le route vocali</span><span class="sxs-lookup"><span data-stu-id="52491-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="52491-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="52491-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="52491-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-117">CsAdministrator</span></span><br />
<span data-ttu-id="52491-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="52491-119">Distribuzione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="52491-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52491-120">Verificare la distribuzione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="52491-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52491-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="52491-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="52491-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-122">CsAdministrator</span></span><br />
<span data-ttu-id="52491-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52491-124">Configurare aree di rete, siti e subnet</span><span class="sxs-lookup"><span data-stu-id="52491-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="52491-125">Creare aree di rete</span><span class="sxs-lookup"><span data-stu-id="52491-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="52491-126">Creare siti di rete</span><span class="sxs-lookup"><span data-stu-id="52491-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="52491-127">Associa le subnet a siti di rete</span><span class="sxs-lookup"><span data-stu-id="52491-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="52491-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="52491-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="52491-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-129">CsAdministrator</span></span><br />
<span data-ttu-id="52491-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="52491-131">Informazioni su aree di rete, siti e subnet</span><span class="sxs-lookup"><span data-stu-id="52491-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="52491-132">Creare o modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="52491-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="52491-133">Creare o modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="52491-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="52491-134">Associare una subnet a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="52491-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52491-135">Configurare il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="52491-136">Creare criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="52491-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="52491-137">Definire la configurazione trunk separata per trunk</span><span class="sxs-lookup"><span data-stu-id="52491-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="52491-138">Modificare i criteri vocali</span><span class="sxs-lookup"><span data-stu-id="52491-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="52491-139">Abilitare la configurazione del routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="52491-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="52491-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="52491-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-141">CsAdministrator</span></span><br />
<span data-ttu-id="52491-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="52491-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="52491-143">Distribuzione di esempio</span><span class="sxs-lookup"><span data-stu-id="52491-143">Sample Deployment</span></span>

<span data-ttu-id="52491-144">La distribuzione seguente viene utilizzata per illustrare ulteriormente i meccanismi abilitati dal routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="52491-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="52491-145">![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="52491-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="52491-146">Chiamate PSTN in arrivo</span><span class="sxs-lookup"><span data-stu-id="52491-146">Incoming PSTN calls</span></span>

<span data-ttu-id="52491-147">Un amministratore può abilitare il trunk definito per instradare le chiamate al "sito 1 gateway" per il routing in base alla posizione e associare il "sito 1 gateway" al sito 1.</span><span class="sxs-lookup"><span data-stu-id="52491-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="52491-148">Una volta abilitata, le chiamate instradate tramite "sito 1 gateway" verranno instradate solo agli utenti che si trovano nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="52491-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="52491-149">Tutte le chiamate instradate attraverso il trunk "site 1 gateway" destinate agli utenti in un sito diverso, ad esempio il sito 2, verranno bloccate per impedire il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="52491-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="52491-150">Tutte le chiamate PSTN in ingresso tramite "site 1 gateway" potranno essere instradate solo agli endpoint situati nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="52491-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="52491-151">Ad esempio, quando "Lync User 1" si sposta nel sito 2, tutte le chiamate PSTN in ingresso tramite "site 1 gateway" non verranno instradate agli endpoint "Lync User 1" presenti nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="52491-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="52491-152">La stessa regola di routing si applica se "Lync User 1" si sposta in un sito di rete sconosciuto in cui la posizione dell'utente non può essere determinata.</span><span class="sxs-lookup"><span data-stu-id="52491-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="52491-153">Nella tabella seguente viene descritta l'esperienza utente di "Lync User 1" in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="52491-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="52491-154">Endpoint di Lync User 1 situati nel sito di rete 1</span><span class="sxs-lookup"><span data-stu-id="52491-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="52491-155">Endpoint di Lync User 1 situati nel sito di rete 2</span><span class="sxs-lookup"><span data-stu-id="52491-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="52491-156">Endpoint di Lync User 1 che si trovano in un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="52491-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-157">Chiamate PSTN in ingresso a Lync User 1</span><span class="sxs-lookup"><span data-stu-id="52491-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="52491-158">Le chiamate vengono instradate agli endpoint in questo percorso</span><span class="sxs-lookup"><span data-stu-id="52491-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="52491-159">Le chiamate non vengono instradate agli endpoint in questo percorso</span><span class="sxs-lookup"><span data-stu-id="52491-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="52491-160">Le chiamate non vengono instradate agli endpoint in questo percorso</span><span class="sxs-lookup"><span data-stu-id="52491-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="52491-161">Chiamate PSTN in uscita</span><span class="sxs-lookup"><span data-stu-id="52491-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="52491-162">Le route vocali vengono referenziate sia nei criteri vocali assegnati direttamente agli utenti, sia nei criteri di routing vocale assegnati a siti di rete.</span><span class="sxs-lookup"><span data-stu-id="52491-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="52491-163">Entrambi i criteri contengono riferimenti a route, che possono essere utilizzati per instradare una chiamata in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="52491-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="52491-164">Ad esempio, un amministratore può definire un criterio di routing vocale per tutti gli utenti che si trovano nel sito di rete 1 per instradare tutte le chiamate in uscita attraverso il "sito 1 gateway" mentre il criterio vocale di alcuni utenti definisce una route per tutte le chiamate in uscita attraverso il "sito 2 gateway".</span><span class="sxs-lookup"><span data-stu-id="52491-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="52491-165">Anche se questi utenti si trovano nel sito di rete 1, le chiamate in uscita verranno instradate attraverso il "sito 1 gateway".</span><span class="sxs-lookup"><span data-stu-id="52491-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="52491-166">Quando un utente si trova in un sito di rete configurato per il routing in base alla posizione, la route dei criteri di routing vocale del sito di rete sostituisce la route dei criteri vocali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="52491-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="52491-167">Questa regola è particolarmente utile per gli utenti che si spostano temporaneamente in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="52491-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="52491-168">In questo caso particolare, un utente utilizzerà sempre un gateway che è locale per la propria posizione. Se "Lync User 3" si trova in "site 2", tutte le chiamate in uscita verranno instradate tramite "site 2 gateway", ma se si sposta sul sito 1, tutte le chiamate in uscita poste mentre è nel sito 1 verranno instradate attraverso "site 1 gateway".</span><span class="sxs-lookup"><span data-stu-id="52491-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="52491-169">Nella tabella seguente viene illustrata l'esperienza utente di Lync User 1 che effettua una chiamata in uscita dai seguenti siti di rete.</span><span class="sxs-lookup"><span data-stu-id="52491-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="52491-170">Sito di rete 1</span><span class="sxs-lookup"><span data-stu-id="52491-170">Network site 1</span></span></th>
<th><span data-ttu-id="52491-171">Sito di rete 2</span><span class="sxs-lookup"><span data-stu-id="52491-171">Network site 2</span></span></th>
<th><span data-ttu-id="52491-172">Sito di rete sconosciuto o non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-173">Autorizzazione delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="52491-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="52491-174">Criteri vocali di Lync User 1</span><span class="sxs-lookup"><span data-stu-id="52491-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="52491-175">Criteri vocali di Lync User 1</span><span class="sxs-lookup"><span data-stu-id="52491-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="52491-176">Criteri vocali di Lync User 1</span><span class="sxs-lookup"><span data-stu-id="52491-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52491-177">Routing delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="52491-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="52491-178">Criterio di routing vocale del sito 1</span><span class="sxs-lookup"><span data-stu-id="52491-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="52491-179">Criterio di routing vocale del sito 2</span><span class="sxs-lookup"><span data-stu-id="52491-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="52491-180">Criteri vocali dell'utente e solo per i sistemi non abilitati per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="52491-181">Trasferimenti e inoltri di chiamata</span><span class="sxs-lookup"><span data-stu-id="52491-181">Call transfers and forwards</span></span>

<span data-ttu-id="52491-182">Quando le chiamate vengono trasferite o inoltrate, il routing delle chiamate è influenzato dal routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="52491-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="52491-183">Nella tabella seguente viene illustrato Lync User 1 che consente di trasferire o inoltrare una chiamata PSTN a un altro utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="52491-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52491-184">Utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="52491-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="52491-185">Lync User 2</span><span class="sxs-lookup"><span data-stu-id="52491-185">Lync user 2</span></span></th>
<th><span data-ttu-id="52491-186">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="52491-186">Lync user 4</span></span></th>
<th><span data-ttu-id="52491-187">Utente di Lync nel sito di rete non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-188">Lync utente 1</span><span class="sxs-lookup"><span data-stu-id="52491-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="52491-189">Inoltro di chiamata o trasferimento consentito</span><span class="sxs-lookup"><span data-stu-id="52491-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="52491-190">Non è consentito l'inoltro di chiamata o il trasferimento</span><span class="sxs-lookup"><span data-stu-id="52491-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="52491-191">Non è consentito l'inoltro di chiamata o il trasferimento</span><span class="sxs-lookup"><span data-stu-id="52491-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="52491-192">Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sulla modalità di instradamento della chiamata in base alla posizione dell'utente Lync trasferito (Lync User 2, Lync User 4 e così via) a un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="52491-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52491-193">Endpoint in cui la chiamata viene trasferita o inoltrata a</span><span class="sxs-lookup"><span data-stu-id="52491-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="52491-194">Lync User 2</span><span class="sxs-lookup"><span data-stu-id="52491-194">Lync user 2</span></span></th>
<th><span data-ttu-id="52491-195">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="52491-195">Lync user 4</span></span></th>
<th><span data-ttu-id="52491-196">Utente di Lync nel sito di rete non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-197">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="52491-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="52491-198">La chiamata inoltra o il trasferimento viene instradato attraverso i criteri di routing vocale del sito 1 e l'uscita tramite il gateway del sito 1</span><span class="sxs-lookup"><span data-stu-id="52491-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="52491-199">La chiamata inoltra o il trasferimento viene instradato attraverso i criteri di routing vocale del sito 2 e l'uscita tramite il gateway del sito 2</span><span class="sxs-lookup"><span data-stu-id="52491-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="52491-200">La chiamata inoltra o il trasferimento viene instradato attraverso il criterio vocale di Lync User e l'uscita tramite un gateway non abilitato per il routing basato sulla posizione (se disponibile)</span><span class="sxs-lookup"><span data-stu-id="52491-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="52491-201">Squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="52491-201">Simultaneous ringing</span></span>

<span data-ttu-id="52491-202">Una volta configurata la distribuzione in base alla posizione nella topologia di esempio, vengono applicate le interazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="52491-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="52491-203">Nella tabella seguente viene illustrato se il routing in base alla posizione consente lo squillo simultaneo di diversi utenti di Lync (ad esempio, Lync User 2, Lync User 4 e così via).</span><span class="sxs-lookup"><span data-stu-id="52491-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52491-204">Destinazione chiamata PSTN in ingresso</span><span class="sxs-lookup"><span data-stu-id="52491-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="52491-205">Lync User 2</span><span class="sxs-lookup"><span data-stu-id="52491-205">Lync user 2</span></span></th>
<th><span data-ttu-id="52491-206">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="52491-206">Lync user 4</span></span></th>
<th><span data-ttu-id="52491-207">Utente di Lync nel sito di rete non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-208">Lync utente 1</span><span class="sxs-lookup"><span data-stu-id="52491-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="52491-209">Squillo simultaneo consentito</span><span class="sxs-lookup"><span data-stu-id="52491-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="52491-210">Squillo simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="52491-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="52491-211">Squillo simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="52491-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="52491-212">Nella tabella seguente viene illustrato se il routing in base alla posizione consente lo squillo simultaneo a un endpoint PSTN da diversi utenti di Lync (ad esempio, Lync User 2, Lync User 4 e così via).</span><span class="sxs-lookup"><span data-stu-id="52491-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52491-213">Destinazione anello simultaneo</span><span class="sxs-lookup"><span data-stu-id="52491-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="52491-214">Lync User 2</span><span class="sxs-lookup"><span data-stu-id="52491-214">Lync user 2</span></span></th>
<th><span data-ttu-id="52491-215">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="52491-215">Lync user 4</span></span></th>
<th><span data-ttu-id="52491-216">Utente di Lync nel sito di rete non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52491-217">Telefono cellulare Lync User 1 (endpoint PSTN)</span><span class="sxs-lookup"><span data-stu-id="52491-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="52491-218">Chiamata instradata tramite il criterio di routing vocale di Network site 1 e l'uscita tramite il gateway del sito 1</span><span class="sxs-lookup"><span data-stu-id="52491-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="52491-219">Chiamata instradata tramite il criterio di routing vocale di Network site 2 e l'uscita tramite il gateway del sito 2</span><span class="sxs-lookup"><span data-stu-id="52491-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="52491-220">La chiamata viene instradata tramite il criterio vocale chiamante e l'uscita tramite un gateway PSTN non è abilitata per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52491-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52491-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52491-221">See Also</span></span>


[<span data-ttu-id="52491-222">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52491-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

