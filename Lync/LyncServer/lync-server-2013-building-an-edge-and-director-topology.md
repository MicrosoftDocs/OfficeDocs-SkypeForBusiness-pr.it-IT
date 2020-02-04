---
title: 'Lync Server 2013: Creazione di una topologia di server perimetrali e server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f8a86d4f80b7fb4fc9990911908ef0c8a317c98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="13b35-102">Creazione di una topologia di server perimetrali e server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13b35-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b35-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="13b35-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="13b35-104">La compilazione della topologia prevede le attività di pianificazione e distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="13b35-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="13b35-105">**Pianificazione**   è necessario definire una topologia appropriata per l'organizzazione e identificare i componenti necessari per distribuirla.</span><span class="sxs-lookup"><span data-stu-id="13b35-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="13b35-106">Questi sono i passaggi standard nel processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="13b35-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="13b35-107">Microsoft Lync Server 2013, strumento di pianificazione fornito con Lync Server 2013, semplifica l'avvio del processo di pianificazione, oltre a includere la possibilità di apportare facilmente modifiche in modo che i requisiti e i piani vengano finalizzati.</span><span class="sxs-lookup"><span data-stu-id="13b35-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="13b35-108">**Distribuzione**   la topologia definita tramite Generatore di topologia è essenziale per la distribuzione di qualsiasi server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="13b35-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="13b35-109">Se non si termina la definizione e la pubblicazione della topologia con il generatore di topologie durante le attività di pianificazione, è necessario completarla e pubblicare la topologia prima di distribuire gli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="13b35-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="13b35-110">Non è possibile distribuire componenti di Edge Server fino a quando non è stato distribuito almeno un pool interno ed è necessario installare Generatore di topologie per distribuire un pool interno.</span><span class="sxs-lookup"><span data-stu-id="13b35-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="13b35-111">Questa sezione non include l'installazione di generatore di topologia perché fa parte del processo di installazione per il pool interno.</span><span class="sxs-lookup"><span data-stu-id="13b35-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="13b35-112">Per informazioni dettagliate su questi strumenti, vedere [elenco di controllo della distribuzione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="13b35-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13b35-113">Se in precedenza è stato usato generatore di topologie per definire una topologia completa, inclusa la topologia di Edge, è possibile ignorare la topologia <A href="lync-server-2013-define-your-edge-topology.md">Definisci il bordo in Lync server 2013</A> e <A href="lync-server-2013-publish-your-topology.md">pubblicare la topologia nelle attività di Lync Server 2013</A> in questa sezione, ma è necessario completare la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'</A> attività di installazione di Edge.</span><span class="sxs-lookup"><span data-stu-id="13b35-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13b35-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="13b35-114">In This Section</span></span>

  - [<span data-ttu-id="13b35-115">Definire la topologia perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13b35-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="13b35-116">Definire topologie con server Director facoltativi nella topologia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13b35-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="13b35-117">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13b35-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="13b35-118">Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</span><span class="sxs-lookup"><span data-stu-id="13b35-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

