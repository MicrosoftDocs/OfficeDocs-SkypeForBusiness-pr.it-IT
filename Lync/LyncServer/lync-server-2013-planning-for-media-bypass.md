---
title: 'Lync Server 2013: pianificazione del bypass multimediale'
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
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="93347-102">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93347-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="93347-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="93347-104">Il termine bypass multimediale indica la rimozione del Mediation Server dal percorso multimediale in tutti i casi possibili per le chiamate con segnale che attraversa il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="93347-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="93347-105">Media Bypass consente di migliorare la qualità vocale riducendo la latenza, le conversioni inutili, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore.</span><span class="sxs-lookup"><span data-stu-id="93347-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="93347-106">Può inoltre essere migliorata la scalabilità, in quanto l'eliminazione dell'elaborazione multimediale per le chiamate ignorate consente di ridurre il carico di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="93347-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="93347-107">Questa riduzione del carico è complementare alla capacità del Mediation Server di controllare più gateway.</span><span class="sxs-lookup"><span data-stu-id="93347-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="93347-108">Se un sito di succursale privo di Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito di larghezza di banda consentendo agli elementi multimediali provenienti da un client in un sito di succursale di fluire direttamente sul gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa.</span><span class="sxs-lookup"><span data-stu-id="93347-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="93347-109">Se si allevia il Mediation Server dall'elaborazione multimediale, il bypass multimediale potrebbe anche ridurre il numero di server Mediation che un'infrastruttura VoIP aziendale richiede.</span><span class="sxs-lookup"><span data-stu-id="93347-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="93347-110">Nella figura seguente sono illustrati i percorsi multimediali e di segnalazione di base in topologie con e senza Media Bypass.</span><span class="sxs-lookup"><span data-stu-id="93347-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="93347-111">**Percorsi multimediali e di segnalazione con e senza Media Bypass**</span><span class="sxs-lookup"><span data-stu-id="93347-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="93347-112">![Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC")</span><span class="sxs-lookup"><span data-stu-id="93347-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="93347-113">In generale, è consigliabile abilitare Media Bypass quando possibile.</span><span class="sxs-lookup"><span data-stu-id="93347-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93347-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="93347-114">In This Section</span></span>

  - [<span data-ttu-id="93347-115">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="93347-116">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="93347-117">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="93347-118">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="93347-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="93347-119">Related Sections</span></span>

[<span data-ttu-id="93347-120">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93347-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93347-121">See Also</span></span>


[<span data-ttu-id="93347-122">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="93347-123">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93347-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

