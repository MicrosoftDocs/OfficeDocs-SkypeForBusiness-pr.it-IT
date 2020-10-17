---
title: 'Lync Server 2013: inizio del processo di pianificazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513040"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="cafc3-102">Inizio del processo di pianificazione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cafc3-102">Beginning the planning process for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cafc3-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="cafc3-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="cafc3-104">Durante la pianificazione di una distribuzione di Unified Communications locale può sembrare intimidatorio, Lync Server fornisce due strumenti utili per:</span><span class="sxs-lookup"><span data-stu-id="cafc3-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="cafc3-105">**Lo strumento di pianificazione** è una procedura guidata che presenta una serie di domande relative all'organizzazione, alle funzionalità di Lync Server che si desidera abilitare e alle esigenze di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="cafc3-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="cafc3-106">Viene quindi creata una topologia di distribuzione consigliata in base alle risposte fornite e viene generato un diagramma di Microsoft Visio della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="cafc3-107">**Generatore di topologie** è un componente di installazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cafc3-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="cafc3-108">Per creare, modificare e pubblicare la topologia pianificata, è possibile utilizzare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cafc3-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="cafc3-109">Convalida inoltre la topologia prima di iniziare le installazioni del server.</span><span class="sxs-lookup"><span data-stu-id="cafc3-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="cafc3-110">Quando si installa Lync Server nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il server viene distribuito come indicato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="cafc3-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="cafc3-111">Strumento di pianificazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cafc3-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="cafc3-112">Lo strumento di pianificazione accetta le risposte alle domande nello strumento e genera una topologia basata sulle linee guida e le procedure consigliate di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cafc3-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="cafc3-113">Fornisce inoltre diverse visualizzazioni di una distribuzione in base alle risposte fornite.</span><span class="sxs-lookup"><span data-stu-id="cafc3-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="cafc3-114">Mostra una visualizzazione globale dei siti, ossia con siti centrali e siti di succursale, e visualizzazioni dettagliate dei server e di altri componenti in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="cafc3-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="cafc3-115">L'esecuzione dello strumento di pianificazione non consente di eseguire una distribuzione specifica o di avviare eventuali processi.</span><span class="sxs-lookup"><span data-stu-id="cafc3-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="cafc3-116">In effetti, l'esecuzione dello strumento di pianificazione anche prima di avere un piano aziendale in mente può essere un modo molto istruttivo per comprendere i tipi di domande che è necessario considerare nel processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="cafc3-117">È possibile eseguire lo strumento di pianificazione più volte, rispondere a domande in modo diverso e confrontare i risultati.</span><span class="sxs-lookup"><span data-stu-id="cafc3-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="cafc3-118">Se si dispone di un progetto di cui si è soddisfatti per la maggior parte ma che è necessario apportare modifiche, è possibile tornare allo strumento di pianificazione, caricare la struttura e apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cafc3-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="cafc3-119">Il completamento dello strumento di pianificazione richiede circa 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="cafc3-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="cafc3-120">Una volta soddisfatti, è possibile utilizzare lo strumento di pianificazione per creare un diagramma della distribuzione pianificata.</span><span class="sxs-lookup"><span data-stu-id="cafc3-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="cafc3-121">È possibile utilizzare questo diagramma durante la creazione della distribuzione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cafc3-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cafc3-122">Lo strumento di pianificazione incluso con questa versione di Lync Server 2013 è una versione definitiva.</span><span class="sxs-lookup"><span data-stu-id="cafc3-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="cafc3-123">Si noti che i numeri relativi alla pianificazione della capacità nello strumento di pianificazione sono preliminari e non sono supportati per la versione finale.</span><span class="sxs-lookup"><span data-stu-id="cafc3-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="cafc3-124">Generatore di topologie di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cafc3-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="cafc3-125">Dopo aver deciso il piano di distribuzione, è possibile utilizzare Generatore di topologie per iniziare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="cafc3-126">Al termine, è possibile utilizzare il generatore di topologie per convalidare la topologia e quindi, se la si passa, si può pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="cafc3-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="cafc3-127">Quando si pubblica la topologia, Lync Server inserisce la topologia nell'archivio di gestione centrale, che viene creata in questo momento, se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="cafc3-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="cafc3-128">Quando si installa Lync Server in ogni server della distribuzione, il server legge la topologia dall'archivio di gestione centrale e si installa per adattarsi al proprio ruolo nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="cafc3-129">In alternativa, se si ha familiarità con Lync Server e si ha bisogno di linee guida meno prescrittivo, è possibile ignorare lo strumento di pianificazione e utilizzare le procedure guidate in Generatore di topologie per la progettazione iniziale della distribuzione e anche per la procedura di convalida e pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="cafc3-130">L'utilizzo di generatore di topologie per la pianificazione e la pubblicazione di una topologia è un passaggio obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cafc3-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="cafc3-131">Non è possibile ignorare il generatore di topologie e installare Lync Server singolarmente sui server della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="cafc3-132">Ogni server deve leggere la topologia da una topologia pubblicata convalidata nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="cafc3-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="cafc3-133">Processo generale di pianificazione</span><span class="sxs-lookup"><span data-stu-id="cafc3-133">High-Level Planning Process</span></span>

<span data-ttu-id="cafc3-134">Per pianificare la distribuzione di Lync Server, è consigliabile eseguire la procedura generale seguente per l'utilizzo sia della documentazione sia dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="cafc3-135">Se si ha familiarità con le versioni precedenti di Lync Server, leggere le [nuove funzionalità in Lync server 2013](lync-server-2013-new-features.md) per acquisire familiarità con le nuove funzionalità e i requisiti di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cafc3-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="cafc3-136">Leggere gli altri argomenti in questa sezione della documentazione: [nozioni di base sulla topologia che è necessario conoscere prima di pianificare Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), le [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md), [le decisioni di pianificazione iniziali per Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [i client per Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="cafc3-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="cafc3-137">Prendere nota delle decisioni di pianificazione rappresentate nelle [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="cafc3-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="cafc3-138">Dopo aver acquisito familiarità con le funzionalità di Lync Server e i tipi di domande che devono essere risolte, eseguire lo strumento di pianificazione e visualizzare la topologia risultante e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="cafc3-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="cafc3-139">Assicurarsi che la topologia sia adatta ai requisiti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="cafc3-140">Se sono presenti particolari carichi di lavoro o funzionalità che sono interessati o che è necessario conoscere, leggere le sezioni appropriate di [pianificazione per Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="cafc3-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="cafc3-141">Eseguire di nuovo lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-141">Run the Planning Tool again.</span></span> <span data-ttu-id="cafc3-142">È possibile iniziare con la distribuzione creata nel passaggio 3 e modificare i risultati oppure ricominciare daccapo.</span><span class="sxs-lookup"><span data-stu-id="cafc3-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="cafc3-143">Se necessario, eseguire lo strumento di pianificazione una terza volta e ripetere fino a quando non si è soddisfatti dell'output.</span><span class="sxs-lookup"><span data-stu-id="cafc3-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="cafc3-144">Dopo aver completato il piano di topologia, utilizzare lo strumento di pianificazione per creare e stampare un diagramma di Visio della topologia.</span><span class="sxs-lookup"><span data-stu-id="cafc3-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="cafc3-145">È possibile utilizzare questa stampa durante l'utilizzo di generatore di topologie per immettere la topologia.</span><span class="sxs-lookup"><span data-stu-id="cafc3-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="cafc3-146">Prima di iniziare la distribuzione, leggere [determinare i requisiti di sistema per Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinare i requisiti dell'infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) per acquisire familiarità con i prerequisiti e l'infrastruttura necessaria per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cafc3-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="cafc3-147">È inoltre necessario leggere tutte le sezioni di [pianificazione per Lync Server 2013](lync-server-2013-planning.md) che si applicano ai carichi di lavoro e alle caratteristiche che si intende distribuire.</span><span class="sxs-lookup"><span data-stu-id="cafc3-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="cafc3-148">Migrazione da versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="cafc3-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="cafc3-149">Se si esegue la migrazione a Lync Server da una versione precedente, vedere la documentazione relativa alla [migrazione](migration.md) per istruzioni specifiche per la migrazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cafc3-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

