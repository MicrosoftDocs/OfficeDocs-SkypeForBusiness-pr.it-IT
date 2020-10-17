---
title: 'Lync Server 2013: requisiti tecnici per il bypass multimediale'
description: 'Lync Server 2013: requisiti tecnici per il bypass multimediale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee594139031966342fcec2bc1296a603055b4cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559442"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="75a4d-103">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a4d-103">Technical requirements for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75a4d-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="75a4d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="75a4d-105">Per ogni chiamata alla rete PSTN, Mediation Server determina se i supporti provenienti dall'endpoint Lync di origine possono essere inviati direttamente a un peer di Mediation Server senza attraversare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="75a4d-105">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="75a4d-106">Il peer può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet (ITSP) associato al trunk tra il Mediation Server in cui viene instradata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="75a4d-106">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="75a4d-107">Il bypass multimediale può essere utilizzato quando vengono soddisfatti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="75a4d-107">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="75a4d-108">Un peer di Mediation Server deve supportare le funzionalità necessarie per il bypass multimediale, la più importante è la possibilità di gestire più risposte a forcella (note come "finestre di dialogo anticipate").</span><span class="sxs-lookup"><span data-stu-id="75a4d-108">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="75a4d-109">Rivolgersi al produttore del gateway o del PBX o al provider di servizi di telefonia Internet per ottenere il numero massimo di dialoghi anticipati accettato da gateway, PBX o SBC.</span><span class="sxs-lookup"><span data-stu-id="75a4d-109">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="75a4d-110">Il peer Mediation Server deve accettare il traffico multimediale direttamente dagli endpoint di Lync.</span><span class="sxs-lookup"><span data-stu-id="75a4d-110">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="75a4d-111">Molte ITSPs consentono all'SBC di ricevere traffico solo dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="75a4d-111">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="75a4d-112">Contattare il ITSP per determinare se il relativo SBC accetta il traffico multimediale direttamente dagli endpoint di Lync.</span><span class="sxs-lookup"><span data-stu-id="75a4d-112">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="75a4d-113">I client Lync e un peer di Mediation Server devono essere ben connessi, nel senso che si trovano nella stessa area di rete o nei siti di rete che si connettono all'area su collegamenti WAN privi di vincoli di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="75a4d-113">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="75a4d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75a4d-114">See Also</span></span>


[<span data-ttu-id="75a4d-115">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a4d-115">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="75a4d-116">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a4d-116">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

