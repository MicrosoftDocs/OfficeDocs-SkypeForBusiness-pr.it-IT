---
title: 'Lync Server 2013: fornitura di connettività PSTN in un sito di succursale'
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
ms.openlocfilehash: a9fe25fc10da3ffc27b882b7d41aac0ad97677f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="556a3-102">Fornitura di connettività PSTN in un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="556a3-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="556a3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="556a3-104">È consigliabile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per aggiungere siti di succursale alla topologia e configurare l'infrastruttura vocale nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="556a3-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="556a3-105">Se non si utilizza lo strumento di pianificazione, utilizzare le procedure illustrate negli argomenti di questa sezione, in primo luogo, per aggiungere i siti di succursale e quindi per configurare l'infrastruttura vocale definendo il gateway PSTN (IP/Public Switched Telephone Network) e/o configurando il trunk SIP (con o senza bypass multimediale).</span><span class="sxs-lookup"><span data-stu-id="556a3-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="556a3-106">La connessione di un sistema PBX (Private Branch Exchange) al sito di succursale è un'altra opzione.</span><span class="sxs-lookup"><span data-stu-id="556a3-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="556a3-107">Se si desidera fornire la resilienza dei siti di succursale, è necessario distribuire un Survivable Branch Appliance, un Survivable Branch Server o un server Standard Edition nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="556a3-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="556a3-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, a seconda dei casi, nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="556a3-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="556a3-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="556a3-109">In This Section</span></span>

  - [<span data-ttu-id="556a3-110">Aggiungere siti di succursale alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="556a3-111">Definire un gateway PSTN per un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="556a3-112">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="556a3-113">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="556a3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="556a3-114">See Also</span></span>


[<span data-ttu-id="556a3-115">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="556a3-116">Pianificazione della connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a3-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

