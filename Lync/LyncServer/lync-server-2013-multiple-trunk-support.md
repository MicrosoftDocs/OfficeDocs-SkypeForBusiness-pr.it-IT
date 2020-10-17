---
title: 'Lync Server 2013: supporto per più trunk'
description: 'Lync Server 2013: supporto per più trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552422"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="aed95-103">Supporto per più trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aed95-103">Multiple trunk support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aed95-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aed95-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aed95-105">La funzionalità di Lync Server 2013 supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="aed95-105">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="aed95-106">Queste associazioni vengono eseguite definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="aed95-106">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="aed95-107">Utilizzare il generatore di topologie per associare i gateway a Mediation Server (ovvero Trunks).</span><span class="sxs-lookup"><span data-stu-id="aed95-107">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="aed95-108">Per assegnare o rimuovere un trunk in Lync Server 2013, è innanzitutto necessario definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="aed95-108">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="aed95-109">Un trunk è costituito dai seguenti elementi: Mediation Server Fully Qualified Domain Name (FQDN), la porta di attesa Mediation Server, il nome di dominio completo del gateway e la porta di attesa del gateway.</span><span class="sxs-lookup"><span data-stu-id="aed95-109">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="aed95-110">Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="aed95-110">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="aed95-111">Questo fornisce ulteriore resilienza all'infrastruttura VoIP aziendale, che è particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="aed95-111">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="aed95-112">Dopo essere stato definito, il trunk deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="aed95-112">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="aed95-113">Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="aed95-113">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="aed95-114">Questo nome semplice viene utilizzato come nome del trunk nel pannello di controllo di Lync Server, dove Trunks può essere associato a route.</span><span class="sxs-lookup"><span data-stu-id="aed95-114">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="aed95-115">Il nome del trunk semplice viene utilizzato come nome del gateway da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aed95-115">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="aed95-116">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="aed95-116">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="aed95-117">Dal generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aed95-117">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="aed95-118">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="aed95-118">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="aed95-119">Nel diagramma seguente vengono illustrati i trunk multipli definiti per ogni Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="aed95-119">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="aed95-120">**Routing con trunk M-N**</span><span class="sxs-lookup"><span data-stu-id="aed95-120">**M-N Trunk Routing**</span></span>

<span data-ttu-id="aed95-121">![Più assegnazioni di trunk.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Più assegnazioni di trunk.")</span><span class="sxs-lookup"><span data-stu-id="aed95-121">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

