---
title: 'Lync Server 2013: Enhanced 9-1-1 (E9-1-1) e Mediation Server'
description: 'Lync Server 2013: Enhanced 9-1-1 (E9-1-1) e Mediation Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fb6da8e69883e321f23a53e8dc5067817d5aa66
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575532"
---
# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="8accc-103">Enhanced 9-1-1 (E9-1-1) e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8accc-103">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8accc-104">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8accc-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8accc-105">Il Mediation Server dispone di funzionalità estese che consentono di interagire correttamente con i provider di servizi Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="8accc-105">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="8accc-106">Non è necessaria alcuna configurazione speciale sul Mediation Server; le estensioni SIP richieste per l'interazione E9-1-1 sono, per impostazione predefinita, incluse nel protocollo SIP del Mediation Server per le interazioni con un peer gateway (gateway PSTN, IP-PBX o SBC di un provider di servizi di telefonia Internet, inclusi i provider di servizi E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="8accc-106">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="8accc-107">Se il trunk SIP di un provider di servizi E9-1-1 può essere interrotto su un pool di Mediation Server esistente o richiederà Mediation Server autonomi, dipenderà dalla possibilità di interagire con un pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8accc-107">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="8accc-108">Per informazioni dettagliate, vedere [Trunk M:N in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="8accc-108">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

