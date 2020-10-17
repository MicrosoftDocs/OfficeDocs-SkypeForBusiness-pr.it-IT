---
title: Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica
description: Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566358"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="c5a9a-103">Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a9a-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5a9a-104">_**Ultimo argomento modificato:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="c5a9a-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="c5a9a-105">I requisiti relativi a porte, protocolli e firewall per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server sono simili a quelli per il server perimetrale distribuito.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="c5a9a-106">I client avviano la comunicazione con il servizio Access Edge tramite TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="c5a9a-107">I partner federati, tuttavia, avvierà le comunicazioni al servizio Access Edge su MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="c5a9a-108">Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, è necessario tenere presente che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di contattare i contatti di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="c5a9a-109">Windows Live Messenger è in grado di partecipare alle comunicazioni audio/video con i client Lync.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="c5a9a-110">Questo account per la porta del firewall molto simile e la configurazione del protocollo che in genere si dispone sul firewall per supportare i client Lync come utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c5a9a-111">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c5a9a-112">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="c5a9a-113">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="c5a9a-114">La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, tranne che per la Cina continentale.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="c5a9a-115">Skype diventerà il client federativo per gli utenti federati che in precedenza utilizzavano Messenger.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="c5a9a-116">Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuito nel server perimetrale consentono la comunicazione dal partner federato XMPP al server perimetrale e consentono inoltre la comunicazione dal server perimetrale al partner federato XMPP.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="c5a9a-117">Una regola viene definita anche nel firewall con accesso interno dal front end server o dal pool Front end al server perimetrale o al pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="c5a9a-118">Riepilogo del firewall-federazione SIP</span><span class="sxs-lookup"><span data-stu-id="c5a9a-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a9a-119">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="c5a9a-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a9a-120">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="c5a9a-120">Source IP address</span></span></th>
<th><span data-ttu-id="c5a9a-121">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="c5a9a-121">Destination IP address</span></span></th>
<th><span data-ttu-id="c5a9a-122">Note</span><span class="sxs-lookup"><span data-stu-id="c5a9a-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a9a-123">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a9a-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-124">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="c5a9a-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-125">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c5a9a-125">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-126">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="c5a9a-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c5a9a-127">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="c5a9a-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a9a-128">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="c5a9a-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a9a-129">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="c5a9a-129">Source IP address</span></span></th>
<th><span data-ttu-id="c5a9a-130">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="c5a9a-130">Destination IP address</span></span></th>
<th><span data-ttu-id="c5a9a-131">Note</span><span class="sxs-lookup"><span data-stu-id="c5a9a-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a9a-132">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a9a-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-133">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="c5a9a-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-134">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c5a9a-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-135">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a9a-136">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a9a-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-137">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c5a9a-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-138">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="c5a9a-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-139">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a9a-140">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a9a-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-141">Client</span><span class="sxs-lookup"><span data-stu-id="c5a9a-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-142">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c5a9a-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-143">Traffico SIP da client a server per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a9a-144">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c5a9a-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-145">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c5a9a-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-146">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5a9a-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-147">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a9a-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a9a-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-149">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c5a9a-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-150">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5a9a-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-151">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a9a-152">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a9a-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-153">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5a9a-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-154">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c5a9a-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-155">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="c5a9a-156">Riepilogo del firewall-protocollo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="c5a9a-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a9a-157">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="c5a9a-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a9a-158">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="c5a9a-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="c5a9a-159">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="c5a9a-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c5a9a-160">Commenti</span><span class="sxs-lookup"><span data-stu-id="c5a9a-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a9a-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c5a9a-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c5a9a-162">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-163">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="c5a9a-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-164">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c5a9a-165">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="c5a9a-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a9a-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c5a9a-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-167">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="c5a9a-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-168">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c5a9a-168">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-169">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="c5a9a-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c5a9a-170">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="c5a9a-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a9a-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="c5a9a-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-172">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c5a9a-172">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-173">IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="c5a9a-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="c5a9a-174">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="c5a9a-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5a9a-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5a9a-175">See Also</span></span>


[<span data-ttu-id="c5a9a-176">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a9a-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="c5a9a-177">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a9a-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="c5a9a-178">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a9a-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

