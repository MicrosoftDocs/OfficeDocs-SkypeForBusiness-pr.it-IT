---
title: 'Lync Server 2013: Pianificazione del bypass multimediale'
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
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="5b0ad-102">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b0ad-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5b0ad-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5b0ad-104">Il bypass multimediale si riferisce alla rimozione del Mediation Server dal percorso multimediale ogni volta che è possibile per le chiamate il cui segnale attraversa il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="5b0ad-105">Il bypass multimediale può migliorare la qualità della voce riducendo la latenza, la traduzione inutile, la possibilità di perdita di pacchetti e il numero di punti di potenziale errore.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="5b0ad-106">La scalabilità può essere migliorata perché l'eliminazione dell'elaborazione multimediale per le chiamate bypassate riduce il carico sul server Mediation.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="5b0ad-107">Questa riduzione del carico complementa la capacità del server Mediation di controllare più gateway.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="5b0ad-108">Se un sito di succursale senza un Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito della larghezza di banda consentendo agli elementi multimediali di un client in un sito di succursale di scorrere direttamente nel gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="5b0ad-109">Attenuando il Mediation Server dall'elaborazione multimediale, il bypass multimediale può anche ridurre il numero di server di mediazione necessari per l'infrastruttura VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="5b0ad-110">Nella figura seguente vengono illustrati i percorsi multimediali e di segnalazione di base nelle topologie con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="5b0ad-111">**Percorsi multimediali e di segnalazione con e senza bypass multimediale**</span><span class="sxs-lookup"><span data-stu-id="5b0ad-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="5b0ad-112">![Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni")</span><span class="sxs-lookup"><span data-stu-id="5b0ad-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="5b0ad-113">Come regola generale, abilitare il bypass multimediale ovunque sia possibile.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b0ad-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5b0ad-114">In This Section</span></span>

  - [<span data-ttu-id="5b0ad-115">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="5b0ad-116">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="5b0ad-117">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="5b0ad-118">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="5b0ad-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5b0ad-119">Related Sections</span></span>

[<span data-ttu-id="5b0ad-120">Distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b0ad-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b0ad-121">See Also</span></span>


[<span data-ttu-id="5b0ad-122">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="5b0ad-123">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0ad-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

