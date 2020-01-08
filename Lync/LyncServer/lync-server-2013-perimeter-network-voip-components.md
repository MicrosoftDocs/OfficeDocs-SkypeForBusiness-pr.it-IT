---
title: 'Lync Server 2013: Componenti VoIP della rete perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605cee3c683ea9b22998de6c218978954907ca52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="d02d3-102">Componenti VoIP della rete perimetrale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d02d3-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d02d3-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d02d3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d02d3-104">I chiamanti esterni che usano client di comunicazioni unificate per chiamate singole o conferenze si basano su Edge Server per la comunicazione vocale con i colleghi.</span><span class="sxs-lookup"><span data-stu-id="d02d3-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="d02d3-105">In un server perimetrale, il servizio Access Edge offre una segnalazione SIP per le chiamate degli utenti di Lync che si trovano al di fuori del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d02d3-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="d02d3-106">L'A/V Edge Services consente l'attraversamento multimediale di NAT e firewall.</span><span class="sxs-lookup"><span data-stu-id="d02d3-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="d02d3-107">Un chiamante che usa un client Unified Communications (UC) all'esterno del firewall aziendale si basa sul servizio A/V Edge sia per le singole che per le conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="d02d3-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="d02d3-108">Il servizio di autenticazione A/V è collocato e fornisce servizi di autenticazione per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="d02d3-108">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="d02d3-109">Gli utenti esterni che tentano di connettersi al servizio a/V Edge richiedono un token di autenticazione fornito dal servizio di autenticazione A/V prima che le chiamate possano passare.</span><span class="sxs-lookup"><span data-stu-id="d02d3-109">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

