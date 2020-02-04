---
title: Distribuzione di Survivable Branch Appliance o Survivable Branch Server - Attività presso il sito centrale
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
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="a3408-102">Distribuzione di Survivable Branch Appliance o Survivable Branch Server con Lync Server 2013 - Attività presso il sito centrale</span><span class="sxs-lookup"><span data-stu-id="a3408-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3408-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a3408-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a3408-104">Completare le attività in questa sezione nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="a3408-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="a3408-105">Se si sta distribuendo un Survivable Branch Server, ignorare la prima attività.</span><span class="sxs-lookup"><span data-stu-id="a3408-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a3408-106">Prima di eseguire le attività in questa sezione, è necessario che siano presenti le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3408-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a3408-107">Lync Server deve essere configurato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="a3408-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="a3408-108">Il tecnico dell'installazione presso il sito della filiale deve essere aggiunto al gruppo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="a3408-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="a3408-109">Inoltre, è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3408-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="a3408-110">Distribuire un server DHCP in ogni sito di filiale per consentire ai client di ottenere indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="a3408-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="a3408-111">In alternativa alla distribuzione di un server DHCP in ogni sito di succursale, abilitare il protocollo DHCP di Lync Server nel Survivable Branch Appliance o Survivable Branch Server usando il cmdlet <STRONG>Set-CsRegistrarConfiguration-EnableDHCPServer $True</STRONG>di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a3408-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="a3408-112">Per informazioni dettagliate, vedere la sezione "requisiti hardware e software" dei <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza del sito filiale per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a3408-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a3408-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a3408-113">In This Section</span></span>

  - [<span data-ttu-id="a3408-114">Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3408-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="a3408-115">Aggiungere siti di succursale alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3408-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="a3408-116">Definire un Survivable Branch Appliance o un Survivable Branch Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3408-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

