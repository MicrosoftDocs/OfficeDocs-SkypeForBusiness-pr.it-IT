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
ms.openlocfilehash: 9d13ca1a28fd28a6d280ddf3a18e57e09376e668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="95266-102">Supporto per più trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95266-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95266-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="95266-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="95266-104">La funzionalità Lync Server 2013 supporta più associazioni tra gateway e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="95266-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="95266-105">Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="95266-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="95266-106">Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).</span><span class="sxs-lookup"><span data-stu-id="95266-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="95266-107">Per assegnare o rimuovere un trunk in Lync Server 2013, è prima di tutto necessario definire un trunk in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="95266-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="95266-108">Un trunk è costituito dall'associazione seguente: Mediation Server Fully Qualified Domain Name (FQDN), la porta di ascolto di Mediation Server, il nome di dominio completo del gateway e la porta di ascolto del gateway.</span><span class="sxs-lookup"><span data-stu-id="95266-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="95266-109">Per configurare più Trunks, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="95266-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="95266-110">In questo modo è disponibile un'ulteriore resilienza dell'infrastruttura VoIP aziendale, che risulta particolarmente utile negli scenari di interoperabilità del PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="95266-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="95266-111">Quando viene definito un trunk, deve essere associato a una route.</span><span class="sxs-lookup"><span data-stu-id="95266-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="95266-112">Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="95266-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="95266-113">Questo nome semplice viene usato come nome del trunk nel pannello di controllo di Lync Server, dove Trunks può essere associato alle route.</span><span class="sxs-lookup"><span data-stu-id="95266-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="95266-114">Il nome trunk semplice viene usato come nome del gateway da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="95266-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="95266-115">L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="95266-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="95266-116">In Generatore di topologie fare clic con il pulsante destro del mouse sul server di mediazione associato e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="95266-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="95266-117">Specificare il gateway predefinito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="95266-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="95266-118">Il diagramma seguente illustra i trunk più definiti per ogni Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="95266-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="95266-119">**Routing Trunk M-N**</span><span class="sxs-lookup"><span data-stu-id="95266-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="95266-120">![Assegnazioni di più trunk.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Assegnazioni di più trunk.")</span><span class="sxs-lookup"><span data-stu-id="95266-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

