---
title: "Lync Server 2013: Stima dell'utilizzo e del traffico vocale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf321dc7668682e2c41765955c348a7e155214ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="52d13-102">Stima dell'utilizzo e del traffico vocale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d13-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d13-103">_**Argomento Ultima modifica:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="52d13-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="52d13-104">Microsoft Lync Server 2013, strumento di pianificazione usa la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.</span><span class="sxs-lookup"><span data-stu-id="52d13-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="52d13-105">Per il **traffico leggero** (una chiamata PSTN per utente per ora), figura 15 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="52d13-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="52d13-106">Per il **traffico medio** (2 chiamate PSTN per utente per ora), figura 10 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="52d13-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="52d13-107">Per **traffico intenso** (3 o più chiamate PSTN per utente per ora), figura 5 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="52d13-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="52d13-108">Il numero di porte determina a sua volta il numero di server di mediazione e gateway che saranno necessari.</span><span class="sxs-lookup"><span data-stu-id="52d13-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="52d13-109">I gateway PSTN (Public Switched Telephone Network) che la maggior parte delle organizzazioni considerano la distribuzione di intervalli di dimensioni da 2 porte fino a un numero di porte di 960.</span><span class="sxs-lookup"><span data-stu-id="52d13-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="52d13-110">Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="52d13-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="52d13-111">Ad esempio, un'organizzazione con gli utenti di 10.000 e il traffico medio richiederebbe porte 1000.</span><span class="sxs-lookup"><span data-stu-id="52d13-111">For example, an organization with 10,000 users and medium traffic would require 1000 ports.</span></span> <span data-ttu-id="52d13-112">Il numero di gateway necessari sarebbe uguale al numero totale di porte richieste come determinato dalla capacità totale dei gateway.</span><span class="sxs-lookup"><span data-stu-id="52d13-112">The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

