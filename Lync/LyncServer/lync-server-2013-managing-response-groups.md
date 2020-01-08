---
title: 'Lync Server 2013: gestire i gruppi di risposte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c0d8ac0fbfa8464fd0cd078fc90784eb9fdd3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="a8ba8-102">Gestione dei gruppi di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ba8-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8ba8-103">_**Argomento Ultima modifica:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="a8ba8-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="a8ba8-104">I gruppi di risposta sono una caratteristica di gestione delle chiamate che consente di accodare le chiamate effettuate a un'area specifica, ad esempio un help desk, e quindi instradare le chiamate a un gruppo di persone designato, denominate *agenti*.</span><span class="sxs-lookup"><span data-stu-id="a8ba8-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="a8ba8-105">Per gestire i gruppi di risposte, configurare i gruppi di agenti, le code e i flussi di lavoro, che definiscono cosa succede a una chiamata dal momento in cui viene inserita fino a quando un agente non risponde.</span><span class="sxs-lookup"><span data-stu-id="a8ba8-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8ba8-106">Se si hanno più di 300 flussi di lavoro in un singolo pool nella distribuzione di Response Group, è preferibile usare i cmdlet di Lync Server Management Shell per creare i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8ba8-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="a8ba8-107">Se si usa lo strumento di configurazione di Response Group per creare flussi di lavoro per un pool con più di 300 flussi di lavoro, la pagina Web richiede molto tempo per il caricamento.</span><span class="sxs-lookup"><span data-stu-id="a8ba8-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="a8ba8-108">Il numero di agenti indirettamente associati ai flussi di lavoro tramite le code ha anche un effetto proporzionale sul caricamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="a8ba8-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="a8ba8-109">Gli argomenti di questa sezione includono procedure dettagliate per le attività che è possibile eseguire per personalizzare e gestire l'applicazione Response Group nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="a8ba8-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8ba8-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a8ba8-110">In This Section</span></span>

  - [<span data-ttu-id="a8ba8-111">Gestione dei gruppi di agenti di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ba8-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="a8ba8-112">Gestione delle code di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ba8-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="a8ba8-113">Gestione dei flussi di lavoro di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ba8-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="a8ba8-114">Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ba8-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="a8ba8-115">Spostamento di gruppi di risposte in un nuovo pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ba8-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="a8ba8-116">Gestione dei Response Group in Lync Server 2013 durante una situazione di emergenza</span><span class="sxs-lookup"><span data-stu-id="a8ba8-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

