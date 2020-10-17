---
title: 'Lync Server 2013: gestione dei Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00736a94cc383a362a3f952519acc603c5beefab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507193"
---
# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="e9555-102">Gestione dei Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9555-102">Managing response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9555-103">_**Ultimo argomento modificato:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="e9555-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="e9555-104">I Response Group sono una funzionalità di gestione delle chiamate che consente di accodare le chiamate effettuate a un'area specifica, ad esempio un helpdesk, e quindi di instradarle a un gruppo designato di persone, note come *agenti*.</span><span class="sxs-lookup"><span data-stu-id="e9555-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="e9555-105">Per gestire i Response Group, è possibile configurare i gruppi di agenti, le code e i flussi di lavoro, in modo da determinare cosa accade a una chiamata dal momento dell'effettuazione fino alla risposta di un agente.</span><span class="sxs-lookup"><span data-stu-id="e9555-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9555-106">Se si dispone di più di 300 flussi di lavoro in un singolo pool nella distribuzione di Response Group, è preferibile utilizzare i cmdlet di Lync Server Management Shell per creare i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e9555-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="e9555-107">Se si utilizza lo Strumento di configurazione dei Response Group per creare i flussi di lavoro per un pool che include più di 300 flussi di lavoro, il caricamento della pagina Web richiederà molto tempo.</span><span class="sxs-lookup"><span data-stu-id="e9555-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="e9555-108">Il numero di agenti indirettamente associati ai flussi di lavoro tramite le code ha anche un effetto proporzionale sul caricamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="e9555-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="e9555-109">Negli argomenti di questa sezione vengono fornite procedure dettagliate per le attività che è possibile eseguire per personalizzare e gestire l'applicazione Response Group nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e9555-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9555-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="e9555-110">In This Section</span></span>

  - [<span data-ttu-id="e9555-111">Gestione dei gruppi di agenti di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9555-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="e9555-112">Gestione delle code di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9555-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="e9555-113">Gestione dei flussi di lavoro di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9555-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="e9555-114">Gestione delle impostazioni dei Response Group a livello di applicazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9555-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="e9555-115">Spostamento di Response Group in un nuovo pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9555-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="e9555-116">Gestione dei Response Group in Lync Server 2013 durante un'emergenza</span><span class="sxs-lookup"><span data-stu-id="e9555-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

