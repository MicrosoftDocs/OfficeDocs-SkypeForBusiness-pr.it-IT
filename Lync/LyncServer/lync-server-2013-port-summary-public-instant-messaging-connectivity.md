---
title: 'Lync Server 2013: riepilogo delle porte-connettività per la messaggistica istantanea pubblica'
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
ms.openlocfilehash: 8bce3413e7e41e3784cb0ba300c621a7c042b618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534163"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="2608a-102">Riepilogo delle porte-connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2608a-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2608a-103">_**Ultimo argomento modificato:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="2608a-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="2608a-104">Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, è necessario tenere presente che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di contattare i contatti di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="2608a-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="2608a-105">Windows Live Messenger è in grado di partecipare alle comunicazioni audio/video con i client Lync.</span><span class="sxs-lookup"><span data-stu-id="2608a-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="2608a-106">Questo account per la porta del firewall molto simile e la configurazione del protocollo che in genere si dispone sul firewall per supportare i client Lync come utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="2608a-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2608a-107">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="2608a-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="2608a-108">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard.</span><span class="sxs-lookup"><span data-stu-id="2608a-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="2608a-109">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="2608a-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="2608a-110">La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, tranne che per la Cina continentale.</span><span class="sxs-lookup"><span data-stu-id="2608a-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="2608a-111">Skype diventerà il client federativo per gli utenti federati che in precedenza utilizzavano Messenger.</span><span class="sxs-lookup"><span data-stu-id="2608a-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="2608a-112">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="2608a-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2608a-113">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="2608a-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2608a-114">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="2608a-114">Source IP address</span></span></th>
<th><span data-ttu-id="2608a-115">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="2608a-115">Destination IP address</span></span></th>
<th><span data-ttu-id="2608a-116">Note</span><span class="sxs-lookup"><span data-stu-id="2608a-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2608a-117">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2608a-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2608a-118">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="2608a-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="2608a-119">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="2608a-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="2608a-120">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="2608a-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2608a-121">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2608a-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2608a-122">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="2608a-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="2608a-123">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="2608a-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="2608a-124">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="2608a-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2608a-125">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="2608a-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2608a-126">Client</span><span class="sxs-lookup"><span data-stu-id="2608a-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="2608a-127">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="2608a-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="2608a-128">Traffico SIP da client a server per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="2608a-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2608a-129">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="2608a-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="2608a-130">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="2608a-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="2608a-131">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2608a-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="2608a-132">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="2608a-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2608a-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2608a-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2608a-134">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="2608a-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="2608a-135">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2608a-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="2608a-136">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="2608a-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2608a-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2608a-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2608a-138">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2608a-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="2608a-139">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="2608a-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="2608a-140">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="2608a-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2608a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2608a-141">See Also</span></span>


[<span data-ttu-id="2608a-142">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2608a-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="2608a-143">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2608a-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

