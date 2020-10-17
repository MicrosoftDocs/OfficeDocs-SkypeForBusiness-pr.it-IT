---
title: 'Lync Server 2013: riepilogo delle porte-connettività per la messaggistica istantanea pubblica'
description: 'Lync Server 2013: riepilogo delle porte-connettività per la messaggistica istantanea pubblica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543062"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="0ac07-103">Riepilogo delle porte-connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ac07-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac07-104">_**Ultimo argomento modificato:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="0ac07-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="0ac07-105">Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, è necessario tenere presente che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di contattare i contatti di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="0ac07-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="0ac07-106">Windows Live Messenger è in grado di partecipare alle comunicazioni audio/video con i client Lync.</span><span class="sxs-lookup"><span data-stu-id="0ac07-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="0ac07-107">Questo account per la porta del firewall molto simile e la configurazione del protocollo che in genere si dispone sul firewall per supportare i client Lync come utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="0ac07-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0ac07-108">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="0ac07-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="0ac07-109">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard.</span><span class="sxs-lookup"><span data-stu-id="0ac07-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="0ac07-110">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="0ac07-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="0ac07-111">La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, tranne che per la Cina continentale.</span><span class="sxs-lookup"><span data-stu-id="0ac07-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="0ac07-112">Skype diventerà il client federativo per gli utenti federati che in precedenza utilizzavano Messenger.</span><span class="sxs-lookup"><span data-stu-id="0ac07-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="0ac07-113">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="0ac07-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ac07-114">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="0ac07-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0ac07-115">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="0ac07-115">Source IP address</span></span></th>
<th><span data-ttu-id="0ac07-116">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="0ac07-116">Destination IP address</span></span></th>
<th><span data-ttu-id="0ac07-117">Note</span><span class="sxs-lookup"><span data-stu-id="0ac07-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ac07-118">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0ac07-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0ac07-119">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="0ac07-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="0ac07-120">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0ac07-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0ac07-121">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="0ac07-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ac07-122">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0ac07-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0ac07-123">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0ac07-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0ac07-124">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="0ac07-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="0ac07-125">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="0ac07-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ac07-126">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="0ac07-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0ac07-127">Client</span><span class="sxs-lookup"><span data-stu-id="0ac07-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="0ac07-128">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0ac07-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0ac07-129">Traffico SIP da client a server per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="0ac07-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ac07-130">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="0ac07-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0ac07-131">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0ac07-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0ac07-132">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="0ac07-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0ac07-133">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="0ac07-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ac07-134">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0ac07-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0ac07-135">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0ac07-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0ac07-136">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="0ac07-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0ac07-137">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="0ac07-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ac07-138">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0ac07-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0ac07-139">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="0ac07-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0ac07-140">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0ac07-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0ac07-141">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="0ac07-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ac07-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ac07-142">See Also</span></span>


[<span data-ttu-id="0ac07-143">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ac07-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="0ac07-144">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ac07-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

