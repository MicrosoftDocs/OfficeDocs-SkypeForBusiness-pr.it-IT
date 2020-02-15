---
title: Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica
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
ms.openlocfilehash: 2512b49f9e0bcdc092354a5f43cb234c7e4d5445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="fb3ca-102">Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb3ca-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb3ca-103">_**Ultimo argomento modificato:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="fb3ca-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="fb3ca-104">I requisiti relativi a porte, protocolli e firewall per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server sono simili a quelli per il server perimetrale distribuito.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="fb3ca-105">I client avviano la comunicazione con il servizio Access Edge tramite TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="fb3ca-106">I partner federati, tuttavia, avvierà le comunicazioni al servizio Access Edge su MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="fb3ca-107">Per configurare il firewall per le porte e i protocolli necessari per supportare la connettività di messaggistica istantanea pubblica, è necessario tenere presente che SIP/MTLS/TCP 5061 è bidirezionale per tenere conto della capacità dei contatti nel provider di messaggistica istantanea pubblica di contattare i client Lync o di contattare i contatti di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="fb3ca-108">Windows Live Messenger è in grado di partecipare alle comunicazioni audio/video con i client Lync.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="fb3ca-109">Questo account per la porta del firewall molto simile e la configurazione del protocollo che in genere si dispone sul firewall per supportare i client Lync come utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="fb3ca-110">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="fb3ca-111">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL (Client Access License) di Lync standard.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="fb3ca-112">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="fb3ca-113">La Federazione con i contatti client di Messenger finirà ufficialmente il 15 marzo 2013, tranne che per la Cina continentale.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="fb3ca-114">Skype diventerà il client federativo per gli utenti federati che in precedenza utilizzavano Messenger.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="fb3ca-115">Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuiti nel server perimetrale consentono la comunicazione dal partner federato XMPP al server perimetrale e consentono anche la comunicazione dal server perimetrale al sistema XMPP. partner federato.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="fb3ca-116">Una regola viene definita anche nel firewall con accesso interno dal front end server o dal pool Front end al server perimetrale o al pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="fb3ca-117">Riepilogo del firewall-federazione SIP</span><span class="sxs-lookup"><span data-stu-id="fb3ca-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb3ca-118">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="fb3ca-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fb3ca-119">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="fb3ca-119">Source IP address</span></span></th>
<th><span data-ttu-id="fb3ca-120">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="fb3ca-120">Destination IP address</span></span></th>
<th><span data-ttu-id="fb3ca-121">Notes</span><span class="sxs-lookup"><span data-stu-id="fb3ca-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb3ca-122">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fb3ca-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-123">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="fb3ca-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-124">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="fb3ca-124">Any</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-125">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="fb3ca-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="fb3ca-126">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="fb3ca-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb3ca-127">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="fb3ca-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fb3ca-128">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="fb3ca-128">Source IP address</span></span></th>
<th><span data-ttu-id="fb3ca-129">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="fb3ca-129">Destination IP address</span></span></th>
<th><span data-ttu-id="fb3ca-130">Notes</span><span class="sxs-lookup"><span data-stu-id="fb3ca-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb3ca-131">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fb3ca-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-132">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="fb3ca-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-133">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="fb3ca-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-134">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb3ca-135">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fb3ca-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-136">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="fb3ca-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-137">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="fb3ca-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-138">Per la connettività di messaggistica istantanea pubblica e federata che utilizzano SIP.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb3ca-139">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="fb3ca-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-140">Client</span><span class="sxs-lookup"><span data-stu-id="fb3ca-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-141">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="fb3ca-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-142">Traffico SIP da client a server per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb3ca-143">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="fb3ca-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-144">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="fb3ca-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-145">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="fb3ca-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-146">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb3ca-147">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fb3ca-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-148">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="fb3ca-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-149">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="fb3ca-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-150">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb3ca-151">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fb3ca-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-152">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="fb3ca-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-153">Interfaccia di accesso ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="fb3ca-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-154">Necessario per la connettività di messaggistica istantanea pubblica con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="fb3ca-155">Riepilogo del firewall-protocollo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="fb3ca-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb3ca-156">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="fb3ca-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fb3ca-157">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="fb3ca-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="fb3ca-158">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="fb3ca-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="fb3ca-159">Commenti</span><span class="sxs-lookup"><span data-stu-id="fb3ca-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb3ca-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="fb3ca-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="fb3ca-161">Any</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-162">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="fb3ca-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-163">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="fb3ca-164">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="fb3ca-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb3ca-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="fb3ca-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-166">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="fb3ca-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-167">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="fb3ca-167">Any</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-168">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="fb3ca-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="fb3ca-169">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="fb3ca-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb3ca-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="fb3ca-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="fb3ca-171">Any</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-172">IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="fb3ca-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="fb3ca-173">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="fb3ca-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb3ca-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb3ca-174">See Also</span></span>


[<span data-ttu-id="fb3ca-175">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb3ca-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="fb3ca-176">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb3ca-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="fb3ca-177">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb3ca-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

