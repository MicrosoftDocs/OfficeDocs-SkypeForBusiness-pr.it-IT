---
title: Distribuzione di un Survivable Branch Appliance o di un'attività del sito server centrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced7b5262880b23540bf3465f787f6512781f2e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="9f3b6-102">Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013-attività del sito centrale</span><span class="sxs-lookup"><span data-stu-id="9f3b6-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f3b6-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9f3b6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9f3b6-104">Le attività indicate in questa sezione devono essere eseguite presso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="9f3b6-105">Se si sta distribuendo un Survivable Branch Server, ignorare la prima attività.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9f3b6-106">Prima di eseguire le attività descritte in questa sezione, è necessario soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f3b6-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9f3b6-107">È necessario configurare Lync Server nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="9f3b6-108">Al gruppo RTCUniversalSBATechnicians deve essere aggiunto un tecnico addetto all'installazione presso il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="9f3b6-109">È inoltre consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f3b6-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="9f3b6-110">Distribuire un server DHCP in ogni sito di succursale per consentire ai client di ottenere gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="9f3b6-111">In alternativa alla distribuzione di un server DHCP in ogni sito di succursale, abilitare Lync Server DHCP nel Survivable Branch Appliance o Survivable Branch Server utilizzando il cmdlet <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $True</STRONG>di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="9f3b6-112">Per informazioni dettagliate, vedere la sezione "requisiti hardware e software" <A href="lync-server-2013-branch-site-resiliency-requirements.md">per i requisiti di resilienza dei siti di succursale per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9f3b6-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9f3b6-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="9f3b6-113">In This Section</span></span>

  - [<span data-ttu-id="9f3b6-114">Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f3b6-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="9f3b6-115">Aggiungere siti di succursale alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f3b6-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="9f3b6-116">Definire un Survivable Branch Appliance o un server di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f3b6-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

