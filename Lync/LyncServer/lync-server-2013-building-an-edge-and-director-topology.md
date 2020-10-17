---
title: 'Lync Server 2013: creazione di una topologia Edge e Director'
description: 'Lync Server 2013: creazione di una topologia Edge e Director.'
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
ms.openlocfilehash: bcb2d422136cf0a421c68ebc2adba50f03c5cc85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569272"
---
# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="0b1f1-103">Creazione di una topologia Edge e Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1f1-103">Building an edge and Director topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b1f1-104">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0b1f1-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0b1f1-105">La creazione della topologia prevede l'esecuzione delle attività di pianificazione e distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b1f1-105">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="0b1f1-106">**Pianificazione**     È necessario definire una topologia appropriata per l'organizzazione e identificare i componenti necessari per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-106">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="0b1f1-107">Questi sono passaggi standard del processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-107">These are standard steps in the planning process.</span></span> <span data-ttu-id="0b1f1-108">Microsoft Lync Server 2013, strumento di pianificazione fornito con Lync Server 2013, semplifica l'avvio del processo di pianificazione, nonché la possibilità di apportare facilmente modifiche man mano che i piani e i requisiti vengono finalizzati.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-108">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="0b1f1-109">**Distribuzione**     La topologia definita tramite Generatore di topologie è essenziale per la distribuzione di qualsiasi server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-109">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="0b1f1-110">Se non si termina la definizione e la pubblicazione della topologia tramite Generatore di topologie nell'ambito delle attività di pianificazione, è necessario completarla e pubblicare la topologia prima di distribuire i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-110">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="0b1f1-111">Non è possibile distribuire i componenti del server perimetrale finché non è stato distribuito almeno un pool interno ed è necessario installare il generatore di topologie per distribuire un pool interno.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-111">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="0b1f1-112">Questa sezione non riguarda l'installazione di generatore di topologie perché fa parte del processo di installazione per il pool interno.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-112">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="0b1f1-113">Per informazioni dettagliate su questi strumenti, vedere [elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0b1f1-113">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b1f1-114">Se in precedenza è stato utilizzato il generatore di topologie per definire una topologia completa, inclusa la topologia perimetrale, è possibile ignorare la topologia <A href="lync-server-2013-define-your-edge-topology.md">perimetrale define in Lync server 2013</A> e <A href="lync-server-2013-publish-your-topology.md">pubblicare la topologia nelle attività di Lync Server 2013</A> in questa sezione, ma è necessario completare la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topologia export your Lync Server 2013 e copiarla su supporto esterno per l'attività di installazione perimetrale</A> .</span><span class="sxs-lookup"><span data-stu-id="0b1f1-114">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b1f1-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="0b1f1-115">In This Section</span></span>

  - [<span data-ttu-id="0b1f1-116">Definire la topologia perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1f1-116">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="0b1f1-117">Definire topologie Director opzionali nella topologia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1f1-117">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="0b1f1-118">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1f1-118">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="0b1f1-119">Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</span><span class="sxs-lookup"><span data-stu-id="0b1f1-119">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

