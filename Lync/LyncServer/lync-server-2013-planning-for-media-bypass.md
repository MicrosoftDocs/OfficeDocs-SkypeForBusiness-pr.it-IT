---
title: 'Lync Server 2013: pianificazione del bypass multimediale'
description: 'Lync Server 2013: pianificazione del bypass multimediale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549442"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="57b14-103">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57b14-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="57b14-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="57b14-105">Il termine bypass multimediale indica la rimozione del Mediation Server dal percorso multimediale in tutti i casi possibili per le chiamate con segnale che attraversa il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="57b14-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="57b14-106">Media Bypass consente di migliorare la qualità vocale riducendo la latenza, le conversioni inutili, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore.</span><span class="sxs-lookup"><span data-stu-id="57b14-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="57b14-107">Può inoltre essere migliorata la scalabilità, in quanto l'eliminazione dell'elaborazione multimediale per le chiamate ignorate consente di ridurre il carico di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="57b14-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="57b14-108">Questa riduzione del carico è complementare alla capacità del Mediation Server di controllare più gateway.</span><span class="sxs-lookup"><span data-stu-id="57b14-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="57b14-109">Se un sito di succursale privo di Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito di larghezza di banda consentendo agli elementi multimediali provenienti da un client in un sito di succursale di fluire direttamente sul gateway locale senza prima dover fluire sul collegamento WAN a un Mediation Server nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="57b14-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="57b14-110">Se si allevia il Mediation Server dall'elaborazione multimediale, il bypass multimediale potrebbe anche ridurre il numero di server Mediation che un'infrastruttura VoIP aziendale richiede.</span><span class="sxs-lookup"><span data-stu-id="57b14-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="57b14-111">Nella figura seguente sono illustrati i percorsi multimediali e di segnalazione di base in topologie con e senza Media Bypass.</span><span class="sxs-lookup"><span data-stu-id="57b14-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="57b14-112">**Percorsi multimediali e di segnalazione con e senza Media Bypass**</span><span class="sxs-lookup"><span data-stu-id="57b14-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="57b14-113">![Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC")</span><span class="sxs-lookup"><span data-stu-id="57b14-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="57b14-114">In generale, è consigliabile abilitare Media Bypass quando possibile.</span><span class="sxs-lookup"><span data-stu-id="57b14-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57b14-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="57b14-115">In This Section</span></span>

  - [<span data-ttu-id="57b14-116">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="57b14-117">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="57b14-118">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="57b14-119">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="57b14-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="57b14-120">Related Sections</span></span>

[<span data-ttu-id="57b14-121">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57b14-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57b14-122">See Also</span></span>


[<span data-ttu-id="57b14-123">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="57b14-124">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

