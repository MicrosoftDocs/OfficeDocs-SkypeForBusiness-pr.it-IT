---
title: 'Lync Server 2013: creare flussi di lavoro di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe0ca786aea0f3c6fab0da95700bd6fa9bb5f21e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504723"
---
# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="cf7a9-102">Creare flussi di lavoro di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7a9-102">Create Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf7a9-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cf7a9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cf7a9-p101">Un flusso di lavoro definisce il comportamento di una chiamata dal momento in cui il telefono squilla al momento in cui un qualcuno risponde. Il flusso di lavoro specifica la coda da utilizzare per lasciare in attesa la chiamata e il metodo di routing da utilizzare per i gruppi di risposta oppure le domande e le risposte da utilizzare per i Response Group interattivi. Un flusso di lavoro inoltre definisce impostazioni quali il messaggio di benvenuto, la musica di attesa, l'orario di ufficio e le festività.</span><span class="sxs-lookup"><span data-stu-id="cf7a9-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="cf7a9-107">È possibile utilizzare lo strumento di configurazione di Response Group per creare flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf7a9-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="cf7a9-108">È possibile accedere allo strumento di configurazione di Response Group dalla pagina Response Group del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf7a9-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf7a9-109">È necessario creare i gruppi di agenti e le code prima di creare il flusso di lavoro che li utilizza.</span><span class="sxs-lookup"><span data-stu-id="cf7a9-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cf7a9-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="cf7a9-110">In This Section</span></span>

  - [<span data-ttu-id="cf7a9-111">Creare o modificare un flusso di lavoro di un gruppo di risposta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7a9-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="cf7a9-112">Progettare flussi di chiamate di risposta vocale interattivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7a9-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="cf7a9-113">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7a9-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="cf7a9-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cf7a9-114">Related Sections</span></span>

  - [<span data-ttu-id="cf7a9-115">Creare gruppi di agenti di Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7a9-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="cf7a9-116">Creare code di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7a9-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

