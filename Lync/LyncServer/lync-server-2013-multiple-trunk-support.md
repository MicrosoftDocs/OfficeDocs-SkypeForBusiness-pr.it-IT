---
title: 'Lync Server 2013: supporto per più trunk'
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
ms.openlocfilehash: 4a2f8e9bea40532486d75e76887e35b496df8631
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="9b75d-102">Supporto per più trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b75d-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b75d-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9b75d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9b75d-104">La funzionalità di Lync Server 2013 supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9b75d-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="9b75d-105">Queste associazioni vengono eseguite definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="9b75d-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="9b75d-106">Utilizzare il generatore di topologie per associare i gateway a Mediation Server (ovvero Trunks).</span><span class="sxs-lookup"><span data-stu-id="9b75d-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="9b75d-107">Per assegnare o rimuovere un trunk in Lync Server 2013, è innanzitutto necessario definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9b75d-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="9b75d-108">Un trunk è costituito dai seguenti elementi: Mediation Server Fully Qualified Domain Name (FQDN), la porta di attesa Mediation Server, il nome di dominio completo del gateway e la porta di attesa del gateway.</span><span class="sxs-lookup"><span data-stu-id="9b75d-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="9b75d-109">Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9b75d-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="9b75d-110">Questo fornisce ulteriore resilienza all'infrastruttura VoIP aziendale, che è particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="9b75d-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="9b75d-111">Dopo essere stato definito, il trunk deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="9b75d-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="9b75d-112">Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9b75d-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="9b75d-113">Questo nome semplice viene utilizzato come nome del trunk nel pannello di controllo di Lync Server, dove Trunks può essere associato a route.</span><span class="sxs-lookup"><span data-stu-id="9b75d-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="9b75d-114">Il nome del trunk semplice viene utilizzato come nome del gateway da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9b75d-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="9b75d-115">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9b75d-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="9b75d-116">Dal generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9b75d-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="9b75d-117">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9b75d-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="9b75d-118">Nel diagramma seguente vengono illustrati i trunk multipli definiti per ogni Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="9b75d-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="9b75d-119">**Routing con trunk M-N**</span><span class="sxs-lookup"><span data-stu-id="9b75d-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="9b75d-120">![Più assegnazioni di trunk.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Più assegnazioni di trunk.")</span><span class="sxs-lookup"><span data-stu-id="9b75d-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

