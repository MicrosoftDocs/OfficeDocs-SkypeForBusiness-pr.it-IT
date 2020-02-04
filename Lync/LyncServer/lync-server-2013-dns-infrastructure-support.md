---
title: "Lync Server 2013: Supporto dell'infrastruttura DNS (Domain Name System)"
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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="1d86c-102">Supporto dell'infrastruttura DNS (Domain Name System) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d86c-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d86c-103">_**Argomento Ultima modifica:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="1d86c-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="1d86c-104">Lync Server 2013 richiede DNS (Domain Name System) e lo usa nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d86c-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="1d86c-105">Per individuare i server o i pool interni per le comunicazioni da server a server.</span><span class="sxs-lookup"><span data-stu-id="1d86c-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="1d86c-106">Per consentire ai client di individuare il pool Front-end o il server Standard Edition usato per varie transazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="1d86c-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="1d86c-107">Per associare gli URL semplici per le conferenze con i server che ospitano tali conferenze.</span><span class="sxs-lookup"><span data-stu-id="1d86c-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="1d86c-108">Per consentire ai server e ai client esterni di connettersi a Edge Server o al proxy inverso HTTP per la messaggistica istantanea o i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="1d86c-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="1d86c-109">Per abilitare i dispositivi Unified Communications (UC) che non hanno eseguito l'accesso per individuare il pool Front end o il server Standard Edition che esegue il servizio Web Update Device, ottenere gli aggiornamenti e inviare i log.</span><span class="sxs-lookup"><span data-stu-id="1d86c-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="1d86c-110">Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d86c-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="1d86c-111">Per il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="1d86c-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d86c-112">Lync Server 2013 non supporta i nomi di dominio internazionalizzati (IDN).</span><span class="sxs-lookup"><span data-stu-id="1d86c-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1d86c-113">Il nome specificato deve essere uguale al nome del computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="1d86c-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="1d86c-114">Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome breve e non un nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="1d86c-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1d86c-115">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="1d86c-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="1d86c-116">Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio.</span><span class="sxs-lookup"><span data-stu-id="1d86c-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1d86c-117"><STRONG>Usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool.</span><span class="sxs-lookup"><span data-stu-id="1d86c-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="1d86c-118">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="1d86c-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1d86c-119">I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche, ovvero quando il nome di dominio completo deve essere assegnato a SN nel certificato.</span><span class="sxs-lookup"><span data-stu-id="1d86c-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

