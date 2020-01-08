---
title: 'Lync Server 2013: Determinare i requisiti di porte e firewall A/V esterni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="32014-102">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32014-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32014-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="32014-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="32014-104">La comunicazione audio/video (A/V) può essere complessa.</span><span class="sxs-lookup"><span data-stu-id="32014-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="32014-105">A causa della natura dei protocolli usati in A/V e in che modo i client e i server usano i protocolli, è garantita una sezione speciale per spiegare le differenze tra le versioni client e server.</span><span class="sxs-lookup"><span data-stu-id="32014-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="32014-106">Usare la tabella a/V del firewall e della porta seguente per determinare i requisiti del firewall e le porte da aprire.</span><span class="sxs-lookup"><span data-stu-id="32014-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="32014-107">Esaminare quindi la terminologia NAT (Network Address Translation) perché NAT può essere implementato in molti modi diversi.</span><span class="sxs-lookup"><span data-stu-id="32014-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="32014-108">Per un esempio dettagliato delle impostazioni della porta del firewall, vedere le architetture di riferimento in [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="32014-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="32014-109">Utilizzo di protocolli generali per UDP e TCP nel traffico audio/video e multimediale</span><span class="sxs-lookup"><span data-stu-id="32014-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32014-110">Trasporto audio/video</span><span class="sxs-lookup"><span data-stu-id="32014-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="32014-111">L'uso</span><span class="sxs-lookup"><span data-stu-id="32014-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32014-112">UDP</span><span class="sxs-lookup"><span data-stu-id="32014-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="32014-113">Protocollo di livello di trasporto preferito per audio e video</span><span class="sxs-lookup"><span data-stu-id="32014-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32014-114">TCP</span><span class="sxs-lookup"><span data-stu-id="32014-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="32014-115">Protocollo di livello di trasporto di fallback per audio e video</span><span class="sxs-lookup"><span data-stu-id="32014-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="32014-116">Protocollo di livello di trasporto obbligatorio per la condivisione delle applicazioni in Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32014-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="32014-117">Protocollo di livello di trasporto obbligatorio per il trasferimento di file in Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32014-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="32014-118">Requisiti della porta firewall esterni A/V per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="32014-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="32014-119">I requisiti della porta del firewall per le interfacce SIP e per le conferenze esterne (e interne) sono coerenti, indipendentemente dalla versione del client o dalla versione del partner federativo.</span><span class="sxs-lookup"><span data-stu-id="32014-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="32014-120">Lo stesso non è vero per l'interfaccia esterna del bordo audio/video.</span><span class="sxs-lookup"><span data-stu-id="32014-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="32014-121">Per la Federazione con Office Communications Server 2007, l'A/V Edge Service richiede che le regole del firewall esterno consentano il traffico RTP/TCP e RTP/UDP nell'intervallo di porte da 50.000 a 59.999 per il flusso in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="32014-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="32014-122">La tabella precedente presuppone che Lync Server 2013 sia il partner principale della Federazione e sia configurato per comunicare con uno degli altri tipi di partner federativi elencati.</span><span class="sxs-lookup"><span data-stu-id="32014-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="32014-123">La configurazione dell'intervallo di porte audio/video di 50000-59.999 deve tenere presente che l'intervallo di porte conterrà le porte di origine per le comunicazioni ai partner federativi.</span><span class="sxs-lookup"><span data-stu-id="32014-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="32014-124">In dettaglio, tenere presente che una comunicazione viene avviata da un partner federativo.</span><span class="sxs-lookup"><span data-stu-id="32014-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="32014-125">La comunicazione dalle porte a/V Edge service nell'intervallo 50000-59.999 si connetterà alla porta prevista TCP 443 dell'A/V Edge del partner.</span><span class="sxs-lookup"><span data-stu-id="32014-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="32014-126">Viceversa, il traffico in entrata per la porta del servizio a/V Edge TCP 443 avrà una porta di origine nell'intervallo di 50000-59.999.</span><span class="sxs-lookup"><span data-stu-id="32014-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="32014-127">I diversi firewall e criteri per l'amministrazione del firewall possono richiedere la configurazione di sole regole di destinazione oppure possono richiedere sia la configurazione dell'origine che quella della destinazione.</span><span class="sxs-lookup"><span data-stu-id="32014-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="32014-128">Se i requisiti sono solo per le porte di destinazione, i requisiti audio/video sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="32014-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32014-129">IP di origine</span><span class="sxs-lookup"><span data-stu-id="32014-129">Source IP</span></span></th>
<th><span data-ttu-id="32014-130">IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="32014-130">Destination IP</span></span></th>
<th><span data-ttu-id="32014-131">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="32014-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32014-132">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-133">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="32014-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32014-135">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-136">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-136">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="32014-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32014-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-138">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-139">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="32014-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32014-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-141">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-142">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="32014-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32014-144">Se i criteri richiedono definizioni di regole firewall in ingresso e in uscita, i requisiti audio/video sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="32014-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32014-145">IP di origine</span><span class="sxs-lookup"><span data-stu-id="32014-145">Source IP</span></span></th>
<th><span data-ttu-id="32014-146">IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="32014-146">Destination IP</span></span></th>
<th><span data-ttu-id="32014-147">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="32014-147">Source Port</span></span></th>
<th><span data-ttu-id="32014-148">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="32014-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32014-149">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-150">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-151">TCP 50000-59.999</span><span class="sxs-lookup"><span data-stu-id="32014-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="32014-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="32014-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32014-153">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-154">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="32014-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="32014-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="32014-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32014-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-157">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-158">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-159">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="32014-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32014-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-161">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-162">Interfaccia A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="32014-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="32014-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="32014-163">Any</span></span></p></td>
<td><p><span data-ttu-id="32014-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="32014-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="32014-165">Microsoft Office Communications Server 2007 richiede una configurazione leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="32014-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="32014-166">L'intervallo di porte TCP e UDP di 50000-59.999 deve essere aperto in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="32014-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="32014-167">Questo requisito è solo per Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="32014-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="32014-168">Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013 richiedono solo l'intervallo TCP 50000-59.999 aperto in uscita.</span><span class="sxs-lookup"><span data-stu-id="32014-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="32014-169">Requisiti NAT per il servizio Edge</span><span class="sxs-lookup"><span data-stu-id="32014-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="32014-170">I requisiti NAT seguenti si applicano se si sceglie di configurare indirizzi IP privati non instradabili per il servizio Edge:</span><span class="sxs-lookup"><span data-stu-id="32014-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="32014-171">NAT può essere usato solo con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="32014-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="32014-172">NAT non è supportato con una topologia di Edge di bilanciamento del carico hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="32014-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="32014-173">NAT può essere usato solo nell'interfaccia esterna di Edge.</span><span class="sxs-lookup"><span data-stu-id="32014-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="32014-174">NAT non è supportato nell'interfaccia Edge interna.</span><span class="sxs-lookup"><span data-stu-id="32014-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="32014-175">NAT deve essere simmetrico per il traffico in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="32014-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="32014-176">Per il traffico da Internet, NAT deve cambiare l'indirizzo IP di destinazione dall'indirizzo IP pubblico abilitato per NAT del servizio a/V Edge all'indirizzo IP esterno.</span><span class="sxs-lookup"><span data-stu-id="32014-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="32014-177">L'indirizzo IP di origine deve rimanere intatto, in modo che il servizio A/V Edge sia in grado di trovare il percorso multimediale ottimale.</span><span class="sxs-lookup"><span data-stu-id="32014-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="32014-178">Ad esempio, nella direzione in entrata della figura seguente l'indirizzo IP pubblico 131.107.155.30 è stato modificato in 10.45.16.10 indirizzo IP (privato) esterno.</span><span class="sxs-lookup"><span data-stu-id="32014-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="32014-179">L'indirizzo IP di origine rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="32014-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="32014-180">Per il traffico dal servizio a/V Edge a Internet, NAT deve modificare l'indirizzo IP di origine dall'indirizzo IP esterno dell'a/V Edge service all'indirizzo IP pubblico abilitato per NAT.</span><span class="sxs-lookup"><span data-stu-id="32014-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="32014-181">Ad esempio, nella direzione in uscita della figura seguente, l'indirizzo IP esterno (privato) 10.45.16.10 è stato modificato nell'indirizzo IP pubblico 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="32014-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="32014-182">**La figura seguente mostra il modo in cui NAT cambia l'indirizzo IP di destinazione per il traffico in entrata e l'indirizzo IP di origine per il traffico in uscita.**</span><span class="sxs-lookup"><span data-stu-id="32014-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="32014-183">![Modifica degli indirizzi IP di destinazione/origine]per la(images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "modifica degli indirizzi IP di destinazione/origine")</span><span class="sxs-lookup"><span data-stu-id="32014-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="32014-184">I punti chiave sono:</span><span class="sxs-lookup"><span data-stu-id="32014-184">The key points are:</span></span>

  - <span data-ttu-id="32014-185">Traffico in ingresso al server che esegue il servizio A/V Edge, l'indirizzo IP di origine non cambia, ma l'indirizzo IP di destinazione cambia da 131.107.155.30 all'indirizzo IP tradotto di 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="32014-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="32014-186">Traffico in uscita dal server che riporta il servizio a/V Edge alla workstation, l'indirizzo IP di origine viene modificato dall'indirizzo IP pubblico del server all'indirizzo IP pubblico del server in cui è in uso il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="32014-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="32014-187">L'IP di destinazione rimane l'indirizzo IP pubblico della workstation.</span><span class="sxs-lookup"><span data-stu-id="32014-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="32014-188">Dopo che il pacchetto ha lasciato il primo dispositivo NAT in uscita, la regola sul dispositivo NAT cambia l'indirizzo IP di origine del server che gestisce l'indirizzo IP dell'interfaccia esterna del servizio A/V (10.45.16.10) con l'indirizzo IP pubblico (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="32014-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

