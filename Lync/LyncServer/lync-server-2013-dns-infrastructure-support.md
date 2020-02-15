---
title: "Lync Server 2013: supporto dell'infrastruttura DNS"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190e0160532ca0ac26ce4f818f260848ea68f0a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="85891-102">Supporto dell'infrastruttura DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85891-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85891-103">_**Ultimo argomento modificato:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="85891-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="85891-104">Lync Server 2013 richiede DNS (Domain Name System) e lo utilizza nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85891-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="85891-105">Per individuare i pool o i server interni per le comunicazioni tra server.</span><span class="sxs-lookup"><span data-stu-id="85891-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="85891-106">Per consentire ai client di individuare il pool Front End o il server Standard Edition utilizzato per diverse transazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="85891-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="85891-107">Per associare gli URL semplici per conferenze ai server che ospitano le conferenze.</span><span class="sxs-lookup"><span data-stu-id="85891-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="85891-108">Per consentire ai server e ai client esterni di connettersi ai server perimetrali o al proxy inverso HTTP per i servizi di messaggistica istantanea o conferenza.</span><span class="sxs-lookup"><span data-stu-id="85891-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="85891-109">Per consentire ai dispositivi per comunicazioni unificate non connessi di individuare il pool Front End o il server Standard Edition che esegue il servizio Web Aggiornamento dispositivi, ottenere gli aggiornamenti e inviare i registri.</span><span class="sxs-lookup"><span data-stu-id="85891-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="85891-110">Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="85891-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="85891-111">Per il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="85891-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85891-112">Lync Server 2013 non supporta i nomi di dominio internazionalizzati (Internationalized Domain Name).</span><span class="sxs-lookup"><span data-stu-id="85891-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85891-113">Il nome specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="85891-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="85891-114">Per impostazione predefinita, il nome del computer di un computer che non è aggiunto a un dominio è un nome breve e non un nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="85891-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="85891-115">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="85891-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="85891-116">Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="85891-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="85891-117">Quando si assegnano FQDN dei server Lync, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno).</span><span class="sxs-lookup"><span data-stu-id="85891-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="85891-118">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="85891-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="85891-119">I caratteri non standard in un FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="85891-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

