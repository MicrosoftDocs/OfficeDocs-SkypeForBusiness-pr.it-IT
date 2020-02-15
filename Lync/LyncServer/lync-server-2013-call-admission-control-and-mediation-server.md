---
title: 'Lync Server 2013: controllo di ammissione di chiamata e Mediation Server'
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
ms.openlocfilehash: 16158c8920279d95cfe3deed37f789eaedccc8b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="a0a3e-102">Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0a3e-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0a3e-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a0a3e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a0a3e-104">Il controllo di ammissione di chiamata (CAC), introdotto per la prima volta in Lync Server 2010, gestisce l'establishment delle sessioni in tempo reale, in base alla larghezza di banda disponibile, per evitare la scarsa qualità dell'esperienza (QoE) per gli utenti nelle reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="a0a3e-105">Per supportare questa funzionalità, il Mediation Server, che fornisce la segnalazione e la traduzione multimediale tra l'infrastruttura VoIP aziendale e un gateway o un provider di trunking SIP, è responsabile della gestione della larghezza di banda per le sue due interazioni su Lync. Parte del server e sul fianco del gateway.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="a0a3e-106">Nel controllo di ammissione di chiamata, l'entità di terminazione di una chiamata deve gestire la prenotazione della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="a0a3e-107">I peer gateway (gateway PSTN, IP-PBX, SBC) su cui interagiscono i Mediation Server con il gateway non supportano il controllo di ammissione di chiamata di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="a0a3e-108">Pertanto, il Mediation Server deve gestire le interazioni di larghezza di banda per conto del peer gateway.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="a0a3e-109">Quando possibile, il Mediation Server riserva la larghezza di banda in anticipo.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="a0a3e-110">In caso contrario, ad esempio se la località dell'endpoint multimediale finale sul lato del gateway non è nota per una chiamata in uscita al peer gateway, la larghezza di banda viene riservata al momento dell'esecuzione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="a0a3e-111">Questo comportamento può causare una richiesta eccessiva di larghezza di banda, ma è l'unico modo per impedire squilli falsi..</span><span class="sxs-lookup"><span data-stu-id="a0a3e-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="a0a3e-112">Il bypass multimediale e la prenotazione della larghezza di banda si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="a0a3e-113">Se per una chiamata viene utilizzato il bypass multimediale, non è possibile effettuare il controllo di ammissione di chiamata per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="a0a3e-114">Il concetto alla base di questo comportamento è che non vi sono collegamenti con larghezza di banda limitata interessati dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="a0a3e-115">Se il controllo di ammissione di chiamata viene utilizzato per una chiamata specifica che implica il Mediation Server, la chiamata non può impiegare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="a0a3e-116">Per informazioni dettagliate sul bypass multimediale o sul controllo di ammissione di chiamata, vedere [Planning for Media Bypass in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a0a3e-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

