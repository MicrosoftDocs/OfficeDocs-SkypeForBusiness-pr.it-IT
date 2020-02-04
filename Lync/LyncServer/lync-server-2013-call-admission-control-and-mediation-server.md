---
title: 'Lync Server 2013: Controllo di ammissione di chiamata e Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="a9eac-102">Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9eac-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9eac-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a9eac-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a9eac-104">Il controllo di ammissione alle chiamate (CAC), introdotto per la prima volta in Lync Server 2010, gestisce lo stabilimento in tempo reale della sessione, basato sulla larghezza di banda disponibile, per evitare la scarsa qualità dell'esperienza (QoE) per gli utenti sulle reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="a9eac-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="a9eac-105">Per supportare questa funzionalità, il Mediation Server, che consente la traduzione di segnali e elementi multimediali tra l'infrastruttura VoIP aziendale e un gateway o un provider di trunking SIP, è responsabile della gestione della larghezza di banda per le due interazioni in Lync Lato server e lato gateway.</span><span class="sxs-lookup"><span data-stu-id="a9eac-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="a9eac-106">In controllo di ammissione di chiamata, l'entità di terminazione per una chiamata gestisce la prenotazione della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="a9eac-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="a9eac-107">I peer gateway (gateway PSTN, IP-PBX, SBC) con cui interagisce il Mediation Server sul lato gateway non supportano il controllo di ammissione alle chiamate di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9eac-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="a9eac-108">Pertanto, il Mediation Server deve gestire le interazioni di larghezza di banda per conto del peer del gateway.</span><span class="sxs-lookup"><span data-stu-id="a9eac-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="a9eac-109">Quando possibile, il Mediation Server riserva la larghezza di banda in anticipo.</span><span class="sxs-lookup"><span data-stu-id="a9eac-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="a9eac-110">Se non è possibile, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer del gateway, la larghezza di banda viene riservata quando viene inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9eac-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="a9eac-111">Questo comportamento può causare un sovraabbonamento della larghezza di banda, ma è l'unico modo per evitare anelli falsi.</span><span class="sxs-lookup"><span data-stu-id="a9eac-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="a9eac-112">Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="a9eac-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="a9eac-113">Se per una chiamata viene impiegato un bypass multimediale, il controllo di ammissione delle chiamate non viene eseguito per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9eac-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="a9eac-114">Il presupposto è che non ci sono collegamenti con larghezza di banda limitata coinvolta nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9eac-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="a9eac-115">Se per una determinata chiamata viene usato il controllo di ammissione alle chiamate che coinvolge il Mediation Server, tale chiamata non può impiegare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="a9eac-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="a9eac-116">Per informazioni dettagliate sul controllo di bypass multimediale o sull'ammissione alle chiamate, vedere [pianificazione di un bypass multimediale in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [pianificazione per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a9eac-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

