---
title: 'Lync Server 2013: Creare flussi di lavoro per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba7d989d1733645c7055fb64d6b790212e15e16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="bc68e-102">Creare flussi di lavoro per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc68e-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc68e-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bc68e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bc68e-104">Un flusso di lavoro definisce il comportamento di una chiamata dall'ora in cui il telefono squilla per l'ora in cui qualcuno risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="bc68e-104">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="bc68e-105">Il flusso di lavoro specifica la coda da usare per la chiamata e specifica il metodo di routing da usare per i gruppi di ricerca o le domande e le risposte da usare per i gruppi di risposta interattivi.</span><span class="sxs-lookup"><span data-stu-id="bc68e-105">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups.</span></span> <span data-ttu-id="bc68e-106">Un flusso di lavoro definisce anche le impostazioni, ad esempio un messaggio di benvenuto, la musica in attesa, le ore lavorative e le festività.</span><span class="sxs-lookup"><span data-stu-id="bc68e-106">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="bc68e-107">Puoi usare lo strumento di configurazione di Response Group per creare flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bc68e-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="bc68e-108">È possibile accedere allo strumento di configurazione di Response Group dalla pagina Response Group del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc68e-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc68e-109">È necessario creare gruppi di agenti e code prima di creare un flusso di lavoro che li usa.</span><span class="sxs-lookup"><span data-stu-id="bc68e-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc68e-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bc68e-110">In This Section</span></span>

  - [<span data-ttu-id="bc68e-111">Creare o modificare un flusso di lavoro di gruppo di ricerca in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc68e-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="bc68e-112">Progettare i flussi di chiamate del sistema IVR (Interactive Voice Response) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc68e-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="bc68e-113">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc68e-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="bc68e-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="bc68e-114">Related Sections</span></span>

  - [<span data-ttu-id="bc68e-115">Creare gruppi di agenti per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc68e-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="bc68e-116">Creare code di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc68e-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

