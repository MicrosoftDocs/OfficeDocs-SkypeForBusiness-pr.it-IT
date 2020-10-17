---
title: 'Lync Server 2013: Componenti VoIP della rete perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c823d290c52f91d8a25e2b9f76c36bf54c9145
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524333"
---
# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="6fd8e-102">Componenti VoIP della rete perimetrale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fd8e-102">Perimeter network VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd8e-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6fd8e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6fd8e-104">I chiamanti esterni che utilizzano client per le comunicazioni unificate per le chiamate individuali o congressuali si basano sul server perimetrale per la comunicazione vocale con i collaboratori.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="6fd8e-105">In un server perimetrale, il servizio Access Edge fornisce la segnalazione SIP per le chiamate provenienti da utenti di Lync che si trovano all'esterno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="6fd8e-106">Il servizio A/V Edge consente l'attraversamento del contenuto multimediale in NAT e nei firewall.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="6fd8e-107">Un chiamante che utilizza un client per le comunicazioni unificate dall'esterno del firewall aziendale utilizza il servizio A/V Edge per singole chiamate e conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="6fd8e-p102">Il servizio di autenticazione A/V si trova nella stessa posizione del servizio A/V Edge e offre servizi di autenticazione per questo servizio. Gli utenti esterni che tentano di connettersi al servizio A/V Edge devono disporre di un token di autenticazione fornito dal servizio di autenticazione A/V prima di poter effettuare le proprie chiamate.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

