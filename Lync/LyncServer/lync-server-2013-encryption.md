---
title: 'Lync Server 2013: crittografia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="11801-102">Crittografia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11801-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11801-103">_**Argomento Ultima modifica:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="11801-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="11801-104">Microsoft Lync Server 2013 usa TLS e MTLS per crittografare i messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="11801-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="11801-105">Tutto il traffico da un server all'altro richiede MTLS, indipendentemente dal fatto che il traffico sia confinato alla rete interna o attraversi il perimetro della rete interna.</span><span class="sxs-lookup"><span data-stu-id="11801-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="11801-106">TLS è facoltativo ma è fortemente consigliato tra Mediation Server e media gateway.</span><span class="sxs-lookup"><span data-stu-id="11801-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="11801-107">Se TLS è configurato su questo collegamento, MTLS è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="11801-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="11801-108">Di conseguenza, il gateway deve essere configurato con un certificato di una CA considerata attendibile dal server Mediation.</span><span class="sxs-lookup"><span data-stu-id="11801-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11801-109">Un Advisory sulla sicurezza per SSL 3,0 è stato pubblicato in 2014.</span><span class="sxs-lookup"><span data-stu-id="11801-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="11801-110">La disabilitazione di SSL 3,0 in Lync Server 2013 è un'opzione supportata.</span><span class="sxs-lookup"><span data-stu-id="11801-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="11801-111">Per ulteriori informazioni sull'advisory sulla sicurezza, vedere <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span><span class="sxs-lookup"><span data-stu-id="11801-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="11801-113">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="11801-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="11801-114">Per assicurarsi che venga usato il protocollo crittografico più forte, Lync Server 2013 offrirà ai client protocolli di crittografia TLS con l'ordine seguente: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="11801-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="11801-115">TLS è un aspetto critico di Lync Server 2013 e quindi è necessario per mantenere un ambiente supportato.</span><span class="sxs-lookup"><span data-stu-id="11801-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="11801-116">I requisiti per il traffico da client a client variano a seconda che il traffico attraversi il firewall aziendale interno.</span><span class="sxs-lookup"><span data-stu-id="11801-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="11801-117">Il traffico strettamente interno può usare TLS, in questo caso il messaggio istantaneo è crittografato o TCP, in questo caso non lo è.</span><span class="sxs-lookup"><span data-stu-id="11801-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="11801-118">La tabella seguente riepiloga i requisiti di protocollo per ogni tipo di traffico.</span><span class="sxs-lookup"><span data-stu-id="11801-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="11801-119">Protezione del traffico</span><span class="sxs-lookup"><span data-stu-id="11801-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11801-120">Tipologia di traffico</span><span class="sxs-lookup"><span data-stu-id="11801-120">Traffic type</span></span></th>
<th><span data-ttu-id="11801-121">Protetto da</span><span class="sxs-lookup"><span data-stu-id="11801-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11801-122">Da server a server</span><span class="sxs-lookup"><span data-stu-id="11801-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="11801-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="11801-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11801-124">Da client a server</span><span class="sxs-lookup"><span data-stu-id="11801-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="11801-125">TLS</span><span class="sxs-lookup"><span data-stu-id="11801-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11801-126">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="11801-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="11801-127">TLS (se configurato per TLS)</span><span class="sxs-lookup"><span data-stu-id="11801-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11801-128">Audio e video e condivisione desktop di file multimediali</span><span class="sxs-lookup"><span data-stu-id="11801-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="11801-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="11801-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11801-130">Condivisione desktop (segnalazione)</span><span class="sxs-lookup"><span data-stu-id="11801-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="11801-131">TLS</span><span class="sxs-lookup"><span data-stu-id="11801-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11801-132">Conferenza Web</span><span class="sxs-lookup"><span data-stu-id="11801-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="11801-133">TLS</span><span class="sxs-lookup"><span data-stu-id="11801-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11801-134">Download contenuto della riunione, download rubrica, espansione gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="11801-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="11801-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11801-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="11801-136">Crittografia file multimediali</span><span class="sxs-lookup"><span data-stu-id="11801-136">Media Encryption</span></span>

<span data-ttu-id="11801-137">Il traffico di file multimediali viene crittografato tramite Secure RTP (SRTP), un profilo di Real-Time Transport Protocol (RTP) che offre riservatezza, autenticazione e protezione dagli attacchi di riproduzione al traffico RTP.</span><span class="sxs-lookup"><span data-stu-id="11801-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="11801-138">Inoltre, i file multimediali che scorrono in entrambe le direzioni tra il Mediation Server e il suo hop successivo interno sono crittografati anche tramite SRTP.</span><span class="sxs-lookup"><span data-stu-id="11801-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="11801-139">Il flusso multimediale in entrambe le direzioni tra il Mediation Server e un gateway multimediale non viene crittografato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="11801-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="11801-140">Il Mediation Server può supportare la crittografia per il gateway multimediale, ma il gateway deve supportare MTLS e lo spazio di archiviazione di un certificato.</span><span class="sxs-lookup"><span data-stu-id="11801-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11801-141">Audio/video (A/V) è supportato con la nuova versione di Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="11801-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="11801-142">Se stai implementando una Federazione A/V con Windows Live Messenger, devi anche modificare il livello di crittografia del server Lync.</span><span class="sxs-lookup"><span data-stu-id="11801-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="11801-143">Per impostazione predefinita, il livello di crittografia è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="11801-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="11801-144">È necessario modificare questa impostazione in supportato tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="11801-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="11801-145">Per altre informazioni, vedere <A href="lync-server-2013-deploying-external-user-access.md">distribuzione dell'accesso degli utenti esterni in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="11801-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="11801-146">Il traffico multimediale audio e video non viene crittografato tra i client Microsoft Lync 2013 e Windows Live.</span><span class="sxs-lookup"><span data-stu-id="11801-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="11801-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="11801-147">FIPS</span></span>

<span data-ttu-id="11801-148">Lync Server 2013 e Microsoft Exchange Server 2013 funzionano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server sono configurati per l'uso degli algoritmi FIPS 140-2 per la crittografia di sistema.</span><span class="sxs-lookup"><span data-stu-id="11801-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="11801-149">Per implementare il supporto FIPS, è necessario configurare ogni server in cui è in esecuzione Lync Server 2013 per supportarlo.</span><span class="sxs-lookup"><span data-stu-id="11801-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="11801-150">Per informazioni dettagliate sull'uso degli algoritmi conformi allo standard FIPS e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge base sugli effetti dell'abilitazione della "crittografia del sistema: usare gli algoritmi conformi agli standard FIPS per la crittografia, l'hashing e la firma" in Windows XP e [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)nelle versioni successive di Windows at.</span><span class="sxs-lookup"><span data-stu-id="11801-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="11801-151">Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere Exchange 2010 SP1 e supporto degli algoritmi conformi a [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)FIPS.</span><span class="sxs-lookup"><span data-stu-id="11801-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

