---
title: 'Lync Server 2013: bypass multimediale e Mediation Server'
description: 'Lync Server 2013: bypass multimediale e Mediation Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb005d3d52fa9e5a38fdf56a65dfcbd73616d87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556432"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="b6919-103">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6919-103">Media bypass and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6919-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b6919-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b6919-105">Il bypass multimediale è una funzionalità di Lync Server che consente a un amministratore di configurare il routing delle chiamate per il flusso direttamente tra l'endpoint utente e il gateway PSTN (Public Switched Telephone Network) senza attraversare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b6919-105">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="b6919-106">Il bypass multimediale consente di migliorare la qualità delle chiamate riducendo la latenza, la traduzione non necessaria, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore.</span><span class="sxs-lookup"><span data-stu-id="b6919-106">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="b6919-107">Se un sito remoto senza Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito di larghezza di banda consentendo agli elementi multimediali provenienti da un client in un sito remoto di fluire direttamente sul gateway locale senza prima dover fluire sul collegamento WAN a un Mediation Server nel sito centrale e viceversa. Questa riduzione dell'elaborazione multimediale integra inoltre la capacità del Mediation Server di controllare più gateway.</span><span class="sxs-lookup"><span data-stu-id="b6919-107">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="b6919-p102">Le funzionalità di bypass multimediale e controllo di ammissione di chiamata (CAC) si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, il controllo di ammissione di chiamate per tale chiamata non viene eseguito. Il presupposto è che nella chiamata non siano coinvolti link con larghezza di banda limitata.</span><span class="sxs-lookup"><span data-stu-id="b6919-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b6919-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6919-111">See Also</span></span>


[<span data-ttu-id="b6919-112">Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6919-112">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="b6919-113">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6919-113">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

