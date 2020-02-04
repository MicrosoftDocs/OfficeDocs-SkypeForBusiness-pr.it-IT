---
title: 'Lync Server 2013: Implementazione della connettività PSTN in un sito di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dfc039b0b1cd2995d0a658f1c1c78e0941d405d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="a6865-102">Implementazione della connettività PSTN in un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6865-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a6865-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a6865-104">È consigliabile usare Microsoft Lync Server 2013, strumento di pianificazione per aggiungere siti di succursale alla topologia e configurare l'infrastruttura vocale in siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="a6865-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="a6865-105">Se non si usa lo strumento di pianificazione, usare le procedure descritte negli argomenti di questa sezione, prima di tutto, per aggiungere i siti di succursale e quindi per configurare l'infrastruttura vocale definendo il gateway PSTN (IP/Public Switched Telephone Network) e/o configurando il trunk SIP (con o senza bypass multimediale).</span><span class="sxs-lookup"><span data-stu-id="a6865-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="a6865-106">La connessione di un PBX (Private Branch Exchange) al sito di succursale è un'altra opzione.</span><span class="sxs-lookup"><span data-stu-id="a6865-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6865-107">Se si vuole specificare la resilienza del sito filiale, è necessario distribuire un Survivable Branch Appliance, un Survivable Branch Server o un server Standard Edition presso il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="a6865-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="a6865-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">distribuzione di un Survivable Branch Appliance o server con Lync server 2013</A> o <A href="lync-server-2013-deploying-lync-server.md">distribuzione di Lync Server 2013</A>, in base alle esigenze, nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6865-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a6865-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a6865-109">In This Section</span></span>

  - [<span data-ttu-id="a6865-110">Aggiungere siti di succursale alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="a6865-111">Definire un gateway PSTN per un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="a6865-112">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="a6865-113">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6865-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6865-114">See Also</span></span>


[<span data-ttu-id="a6865-115">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="a6865-116">Pianificazione della connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6865-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

