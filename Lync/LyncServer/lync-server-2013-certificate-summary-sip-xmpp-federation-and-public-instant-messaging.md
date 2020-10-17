---
title: Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica
description: Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572142"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="41b46-103">Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-103">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41b46-104">_**Ultimo argomento modificato:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="41b46-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="41b46-105">I certificati necessari per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server vengono in genere soddisfatti dai certificati che vengono configurati, richiesti e assegnati al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="41b46-105">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="41b46-106">I requisiti dei certificati per l'abilitazione e la creazione di comunicazioni con i partner di protocollo XMPP (Extensible Messaging and Presence Protocol) richiedono l'aggiunta di voci per i domini XMPP.</span><span class="sxs-lookup"><span data-stu-id="41b46-106">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="41b46-107">Il record incluso nel certificato come nome alternativo del soggetto (SAN) corrisponderà al dominio che può partecipare alle comunicazioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="41b46-107">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="41b46-108">Il dominio può essere a livello della radice (ad esempio, contoso.com) se si desidera abilitare XMPP per l'intero dominio oppure può corrispondere a domini figlio selezionati (ad esempio, corp.contoso.com, finance.contoso.com) se si desidera abilitare XMPP per un sottoinsieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="41b46-108">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="41b46-109">Per configurare i certificati per la connettività per la messaggistica istantanea pubblica, tenere presente che non vi sono elementi diversi da altri tipi di federazione SIP o persino certificati del server perimetrale standard, tranne per il fatto che America Online (AOL) richiede il certificato o i certificati (nel caso di un pool di server perimetrali) per contenere anche l'EKU del client.</span><span class="sxs-lookup"><span data-stu-id="41b46-109">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="41b46-110">L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="41b46-110">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="41b46-111">Per verificare di aver soddisfatto i requisiti di certificato corretti per la distribuzione del server perimetrale, esaminare gli argomenti elencati nella sezione **vedere anche**.</span><span class="sxs-lookup"><span data-stu-id="41b46-111">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41b46-112">Componente</span><span class="sxs-lookup"><span data-stu-id="41b46-112">Component</span></span></th>
<th><span data-ttu-id="41b46-113">Nome soggetto</span><span class="sxs-lookup"><span data-stu-id="41b46-113">Subject name</span></span></th>
<th><span data-ttu-id="41b46-114">Nomi alternativi soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="41b46-114">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="41b46-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="41b46-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41b46-116">Perimetro esterno/Access Edge</span><span class="sxs-lookup"><span data-stu-id="41b46-116">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="41b46-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41b46-117">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41b46-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41b46-118">sip.contoso.com</span></span></p>
<p><span data-ttu-id="41b46-119">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41b46-119">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="41b46-120">contoso.com</span><span class="sxs-lookup"><span data-stu-id="41b46-120">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="41b46-121">Per supportare lo spazio dei nomi XMPP di contoso.com</span><span class="sxs-lookup"><span data-stu-id="41b46-121">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="41b46-122">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41b46-122">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="41b46-123">Per supportare lo spazio dei nomi SIP di fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41b46-123">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="41b46-124">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41b46-124">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="41b46-125">Per supportare lo spazio dei nomi XMPP di fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41b46-125">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="41b46-126">Il certificato deve provenire da un'autorità di certificazione pubblica e deve disporre del server EKU e del client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL.</span><span class="sxs-lookup"><span data-stu-id="41b46-126">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="41b46-127">Il certificato viene assegnato alle interfacce del server perimetrale esterno per:</span><span class="sxs-lookup"><span data-stu-id="41b46-127">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="41b46-128">Servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="41b46-128">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="41b46-129">Servizio Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="41b46-129">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="41b46-130">Servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="41b46-130">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="41b46-131">Tecnicamente, un certificato non viene assegnato all'a/V Edge.</span><span class="sxs-lookup"><span data-stu-id="41b46-131">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="41b46-132">La comunicazione e l'autenticazione sicure sono gestite tramite il servizio di autenticazione Media Relay (MRAS).</span><span class="sxs-lookup"><span data-stu-id="41b46-132">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="41b46-133">MRAS utilizza il certificato assegnato all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="41b46-133">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="41b46-p105">Si noti che i SAN vengono aggiunti automaticamente al certificato in base alle definizioni fornite nel Generatore di topologie. Le voci SAN vengono aggiunte in base alle esigenze per i domini SIP aggiuntivi e per altre voci di cui è richiesto il supporto. Il nome soggetto viene replicato nel SAN e deve essere presente per il funzionamento corretto.</span><span class="sxs-lookup"><span data-stu-id="41b46-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41b46-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41b46-137">See Also</span></span>


[<span data-ttu-id="41b46-138">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="41b46-138">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="41b46-139">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-139">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="41b46-140">Riepilogo dei certificati-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-140">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="41b46-141">Riepilogo dei certificati-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-141">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="41b46-142">Riepilogo dei certificati-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-142">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="41b46-143">Riepilogo dei certificati-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-143">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="41b46-144">Riepilogo dei certificati-perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41b46-144">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

