---
title: Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica
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
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="fce89-102">Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fce89-103">_**Argomento Ultima modifica:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="fce89-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="fce89-104">I certificati necessari per la Federazione con Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server verranno in genere soddisfatti dai certificati configurati, richiesti e assegnati al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="fce89-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="fce89-105">I requisiti di certificato per l'abilitazione e la creazione di comunicazioni con i partner del protocollo XMPP (Extensible Messaging and Presence Protocol) richiedono l'aggiunta di voci per i domini XMPP.</span><span class="sxs-lookup"><span data-stu-id="fce89-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="fce89-106">Il record incluso nel certificato come nome alternativo soggetto (SAN) sarà il dominio che può partecipare alle comunicazioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="fce89-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="fce89-107">Il dominio può essere il dominio a livello di radice (ad esempio contoso.com) se si vuole abilitare XMPP per l'intero dominio oppure i domini figlio selezionati, ad esempio corp.contoso.com, finance.contoso.com, se si Abilita XMPP per un sottoinsieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="fce89-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="fce89-108">Per configurare i certificati per la connettività pubblica per la messaggistica istantanea, tenere presente che non sono presenti elementi diversi da altri tipi federativi SIP o da certificati standard del server Edge, ad eccezione del fatto che America Online (AOL) richiede un certificato o i certificati (in il caso di un pool di bordi) per contenere anche l'EKU client.</span><span class="sxs-lookup"><span data-stu-id="fce89-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="fce89-109">L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="fce89-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="fce89-110">Per verificare di avere soddisfatto i requisiti di certificato corretti per la distribuzione di Edge Server, esaminare gli argomenti elencati nella sezione **vedere anche**.</span><span class="sxs-lookup"><span data-stu-id="fce89-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="fce89-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fce89-111">Component</span></span></th>
<th><span data-ttu-id="fce89-112">Nome oggetto</span><span class="sxs-lookup"><span data-stu-id="fce89-112">Subject name</span></span></th>
<th><span data-ttu-id="fce89-113">Nomi alternativi oggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="fce89-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="fce89-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="fce89-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fce89-115">Esterno/bordo di accesso</span><span class="sxs-lookup"><span data-stu-id="fce89-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="fce89-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fce89-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fce89-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fce89-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="fce89-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fce89-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="fce89-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fce89-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="fce89-120">Per supportare lo spazio dei nomi XMPP contoso.com</span><span class="sxs-lookup"><span data-stu-id="fce89-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="fce89-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fce89-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="fce89-122">Per supportare lo spazio dei nomi SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fce89-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="fce89-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fce89-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="fce89-124">Per supportare lo spazio dei nomi XMPP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fce89-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="fce89-125">Il certificato deve provenire da una CA pubblica e deve avere il server EKU e il client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL.</span><span class="sxs-lookup"><span data-stu-id="fce89-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="fce89-126">Il certificato viene assegnato alle interfacce di Edge Server esterne per:</span><span class="sxs-lookup"><span data-stu-id="fce89-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="fce89-127">Access Edge Services</span><span class="sxs-lookup"><span data-stu-id="fce89-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="fce89-128">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="fce89-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="fce89-129">A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="fce89-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="fce89-130">Tecnicamente, un certificato non viene assegnato al bordo A/V.</span><span class="sxs-lookup"><span data-stu-id="fce89-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="fce89-131">La sicurezza delle comunicazioni e dell'autenticazione è gestita tramite il servizio di autenticazione di MRA (Media Relay Authentication Service).</span><span class="sxs-lookup"><span data-stu-id="fce89-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="fce89-132">MRA usa il certificato assegnato all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="fce89-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="fce89-133">Tieni presente che i SANs vengono aggiunti automaticamente al certificato in base alle tue definizioni in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fce89-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="fce89-134">Si aggiungono le voci SAN in base alle esigenze per altri domini SIP e altre voci che è necessario supportare.</span><span class="sxs-lookup"><span data-stu-id="fce89-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="fce89-135">Il nome del soggetto viene replicato nella SAN e deve essere presente per il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="fce89-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fce89-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fce89-136">See Also</span></span>


[<span data-ttu-id="fce89-137">Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="fce89-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="fce89-138">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="fce89-139">Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="fce89-140">Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="fce89-141">Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="fce89-142">Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="fce89-143">Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce89-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

