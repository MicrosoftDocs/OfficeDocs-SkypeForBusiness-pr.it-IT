---
title: 'Lync Server 2013: Bypass multimediale e Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="c138a-102">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c138a-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c138a-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c138a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c138a-104">Il bypass multimediale è una funzionalità di Lync Server che consente a un amministratore di configurare il routing delle chiamate per il flusso diretto tra l'endpoint utente e il gateway PSTN (Public Switched Telephone Network) senza attraversare il server Mediation.</span><span class="sxs-lookup"><span data-stu-id="c138a-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="c138a-105">Il bypass multimediale migliora la qualità delle chiamate riducendo la latenza, la traduzione non necessaria, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore.</span><span class="sxs-lookup"><span data-stu-id="c138a-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="c138a-106">Se un sito remoto senza un Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il fabbisogno di larghezza di banda consentendo agli elementi multimediali di un client in un sito remoto di scorrere direttamente nel gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa. Questa riduzione dell'elaborazione multimediale completa inoltre la capacità del server mediatore di controllare più gateway.</span><span class="sxs-lookup"><span data-stu-id="c138a-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="c138a-107">Il bypass multimediale e il controllo di ammissione delle chiamate (CAC) si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="c138a-107">Media bypass and call admission control (CAC) are mutually exclusive.</span></span> <span data-ttu-id="c138a-108">Se per una chiamata viene usato il bypass multimediale, CAC non viene eseguito per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c138a-108">If media bypass is employed for a call, CAC is not performed for that call.</span></span> <span data-ttu-id="c138a-109">Il presupposto è che non ci sono collegamenti con larghezza di banda vincolata coinvolta nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="c138a-109">The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c138a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c138a-110">See Also</span></span>


[<span data-ttu-id="c138a-111">Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c138a-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="c138a-112">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c138a-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

