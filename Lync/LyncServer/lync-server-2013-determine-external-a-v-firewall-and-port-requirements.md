---
title: 'Lync Server 2013: determinare i requisiti di porte e firewall A/V esterni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30492bed8deeb2a24dd136355e8f21f82e28a903
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42132569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="5d9ea-102">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d9ea-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d9ea-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5d9ea-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5d9ea-104">La comunicazione audio/video (A/V) può essere complessa.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="5d9ea-105">A causa della natura dei protocolli utilizzati in A/V e in che modo i client e i server utilizzano i protocolli, viene garantita una sezione speciale che spiega le differenze tra le versioni client e server.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="5d9ea-106">Utilizzare la seguente tabella di porte e firewall a/V per determinare i requisiti del firewall e le porte da aprire.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="5d9ea-107">Rivedere quindi la terminologia relativa alla conversione NAT (Network Address Translation) perché quest'ultima può essere implementata in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="5d9ea-108">Per un esempio dettagliato delle impostazioni delle porte del firewall, vedere le architetture di riferimento in [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5d9ea-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="5d9ea-109">Utilizzo di protocollo generale per UDP e TCP in audio/video e traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="5d9ea-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d9ea-110">Trasporto audio/video</span><span class="sxs-lookup"><span data-stu-id="5d9ea-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="5d9ea-111">Usage</span><span class="sxs-lookup"><span data-stu-id="5d9ea-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d9ea-112">UDP</span><span class="sxs-lookup"><span data-stu-id="5d9ea-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-113">Protocollo di trasporto Layer preferito per audio e video</span><span class="sxs-lookup"><span data-stu-id="5d9ea-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d9ea-114">TCP</span><span class="sxs-lookup"><span data-stu-id="5d9ea-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-115">Protocollo di livello di trasporto di fallback per audio e video</span><span class="sxs-lookup"><span data-stu-id="5d9ea-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="5d9ea-116">Protocollo di trasporto Layer obbligatorio per la condivisione di applicazioni in Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d9ea-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="5d9ea-117">Protocollo di trasporto Layer obbligatorio per il trasferimento di file in Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d9ea-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="5d9ea-118">Requisiti delle porte dei firewall A/V esterni per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="5d9ea-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="5d9ea-119">I requisiti delle porte del firewall per le interfacce SIP e di conferenza esterne (e interne) sono coerenti, indipendentemente dalla versione del client o dalla versione del partner federativo.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="5d9ea-120">Non si applicano gli stessi requisiti per l'interfaccia esterna Audio/Video Edge.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="5d9ea-121">Per la Federazione con Office Communications Server 2007, è necessario che il servizio A/V Edge richieda che le regole del firewall esterno consentano il traffico RTP/TCP e RTP/UDP nell'intervallo di porte da 50.000 a 59.999 per il flusso in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="5d9ea-122">La tabella precedente presuppone che Lync Server 2013 sia il partner federativo principale e che sia configurato per la comunicazione con uno degli altri tipi di partner di Federazione elencati.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="5d9ea-123">Se si configura l'intervallo di porte audio/video di 50000-59.999, è necessario tenere presente che l'intervallo di porte conterrà le porte di origine per le comunicazioni ai partner federativi.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="5d9ea-124">In dettaglio, considerare che una comunicazione viene avviata da un partner federativo.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="5d9ea-125">La comunicazione dalle porte del servizio A/V Edge nell'intervallo 50000-59.999 si collegherà alla porta prevista TCP 443 del servizio A/V Edge del partner.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="5d9ea-126">Al contrario, il traffico in ingresso alla porta del servizio A/V Edge TCP 443 avrà una porta di origine nell'intervallo di 50000-59.999.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="5d9ea-127">Diversi firewall e criteri per l'amministrazione del firewall possono richiedere la configurazione delle sole regole di destinazione oppure richiedono la configurazione di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="5d9ea-128">Se i requisiti sono solo per le porte di destinazione, i requisiti audio/video sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9ea-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d9ea-129">IP origine</span><span class="sxs-lookup"><span data-stu-id="5d9ea-129">Source IP</span></span></th>
<th><span data-ttu-id="5d9ea-130">IP destinazione</span><span class="sxs-lookup"><span data-stu-id="5d9ea-130">Destination IP</span></span></th>
<th><span data-ttu-id="5d9ea-131">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="5d9ea-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d9ea-132">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-133">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5d9ea-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d9ea-135">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-136">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-136">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5d9ea-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d9ea-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-138">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-139">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5d9ea-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d9ea-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-141">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-142">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5d9ea-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5d9ea-144">Se i criteri richiedono le definizioni delle regole del firewall in ingresso e in uscita, i requisiti audio/video sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9ea-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d9ea-145">IP origine</span><span class="sxs-lookup"><span data-stu-id="5d9ea-145">Source IP</span></span></th>
<th><span data-ttu-id="5d9ea-146">IP destinazione</span><span class="sxs-lookup"><span data-stu-id="5d9ea-146">Destination IP</span></span></th>
<th><span data-ttu-id="5d9ea-147">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="5d9ea-147">Source Port</span></span></th>
<th><span data-ttu-id="5d9ea-148">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="5d9ea-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d9ea-149">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-150">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-151">TCP 50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5d9ea-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5d9ea-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d9ea-153">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-154">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5d9ea-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5d9ea-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d9ea-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-157">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-158">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-159">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5d9ea-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d9ea-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-161">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-162">Interfaccia del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5d9ea-163">Any</span></span></p></td>
<td><p><span data-ttu-id="5d9ea-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5d9ea-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="5d9ea-165">Microsoft Office Communications Server 2007 richiede una configurazione leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="5d9ea-166">L'intervallo di porte TCP e UDP di 50000-59.999 deve essere aperto in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="5d9ea-167">Questo requisito è solo per Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="5d9ea-168">Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013 richiedono solo l'intervallo TCP 50000-59.999 aperto in uscita.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="5d9ea-169">Requisiti NAT per il servizio Edge</span><span class="sxs-lookup"><span data-stu-id="5d9ea-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="5d9ea-170">Se si sceglie di configurare gli indirizzi IP privati non instradabili per il servizio Edge, si applicano i requisiti NAT seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9ea-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="5d9ea-171">NAT può essere utilizzato solo con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="5d9ea-172">NAT non è supportato con una topologia Edge di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="5d9ea-173">NAT può essere utilizzato solo nell'interfaccia perimetrale esterna.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="5d9ea-174">NAT non è supportato per l'interfaccia perimetrale interna.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="5d9ea-175">NAT deve essere simmetrico per il traffico in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="5d9ea-176">Per il traffico proveniente da Internet, NAT deve modificare l'indirizzo IP di destinazione dall'indirizzo IP pubblico abilitato NAT del servizio a/V Edge all'indirizzo IP esterno.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="5d9ea-177">L'indirizzo IP di origine deve rimanere intatto, in modo che il servizio A/V Edge possa trovare il percorso multimediale ottimale.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="5d9ea-178">Ad esempio, nella direzione in ingresso nella figura seguente, l'indirizzo IP pubblico 131.107.155.30 è stato modificato nell'indirizzo IP esterno (privato) 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="5d9ea-179">L'indirizzo IP di origine è rimasto invariato.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="5d9ea-180">Per il traffico proveniente dal servizio a/V Edge a Internet, NAT deve modificare l'indirizzo IP di origine dall'indirizzo IP esterno del servizio a/V Edge all'indirizzo IP pubblico abilitato per NAT.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="5d9ea-181">Ad esempio, nella direzione in uscita della figura seguente, l'indirizzo IP esterno (privato) 10.45.16.10 è stato modificato nell'indirizzo IP pubblico 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="5d9ea-182">**Nella figura seguente viene illustrato il modo in cui NAT cambia l'indirizzo IP di destinazione per il traffico in ingresso e l'indirizzo IP di origine per il traffico in uscita.**</span><span class="sxs-lookup"><span data-stu-id="5d9ea-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="5d9ea-183">![Modifica degli indirizzi IP di destinazione/origine](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modifica degli indirizzi IP di destinazione/origine")</span><span class="sxs-lookup"><span data-stu-id="5d9ea-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="5d9ea-184">I punti principali sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9ea-184">The key points are:</span></span>

  - <span data-ttu-id="5d9ea-185">Traffico in ingresso al server che esegue il servizio A/V Edge, l'indirizzo IP di origine non cambia ma l'indirizzo IP di destinazione cambia da 131.107.155.30 all'indirizzo IP convertito di 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="5d9ea-186">Il traffico in uscita dal server che esegue il servizio A/V Edge torna alla workstation, l'indirizzo IP di origine cambia dall'indirizzo IP pubblico del server all'indirizzo IP pubblico del server che esegue il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="5d9ea-187">L'IP di destinazione rimane l'indirizzo IP pubblico della workstation.</span><span class="sxs-lookup"><span data-stu-id="5d9ea-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="5d9ea-188">Dopo che il pacchetto ha lasciato il primo dispositivo NAT in uscita, la regola sul dispositivo NAT cambia l'indirizzo IP di origine del server che esegue l'indirizzo IP dell'interfaccia esterna del servizio A/V Edge (10.45.16.10) al relativo indirizzo IP pubblico (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="5d9ea-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

