---
title: 'Lync Server 2013: Inizio del processo di pianificazione'
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
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="6223e-102">Inizio del processo di pianificazione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6223e-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6223e-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6223e-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6223e-104">Durante la pianificazione di una distribuzione di Unified Communications locale può sembrare intimidatorio, Lync Server offre due strumenti utili per aiutarti:</span><span class="sxs-lookup"><span data-stu-id="6223e-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="6223e-105">**Lo strumento di pianificazione** è una procedura guidata che presenta una serie di domande sull'organizzazione, le caratteristiche di Lync Server che si desidera abilitare e le esigenze di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="6223e-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="6223e-106">Crea quindi una topologia di distribuzione consigliata in base alle risposte e produce un diagramma di Microsoft Visio della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6223e-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="6223e-107">**Generatore di topologia** è un componente di installazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6223e-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="6223e-108">Si usa generatore di topologie per creare, modificare e pubblicare la topologia pianificata.</span><span class="sxs-lookup"><span data-stu-id="6223e-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="6223e-109">Convalida anche la topologia prima di iniziare le installazioni del server.</span><span class="sxs-lookup"><span data-stu-id="6223e-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="6223e-110">Quando si installa Lync Server nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il programma di installazione distribuisce il server come indicato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="6223e-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="6223e-111">Strumento di pianificazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="6223e-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="6223e-112">Lo strumento di pianificazione prende le risposte alle domande nello strumento e genera una topologia basata sulle linee guida e le procedure consigliate di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6223e-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="6223e-113">Offre anche diverse visualizzazioni di una distribuzione in base alle risposte.</span><span class="sxs-lookup"><span data-stu-id="6223e-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="6223e-114">Mostra sia una visualizzazione globale di tutti i siti, sia i siti centrali che i siti di succursale, nonché visualizzazioni dettagliate che mostrano i server e altri componenti di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="6223e-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="6223e-115">L'uso dello strumento di pianificazione non consente di eseguire il commit di una specifica distribuzione o di avviare processi.</span><span class="sxs-lookup"><span data-stu-id="6223e-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="6223e-116">In realtà, l'esecuzione dello strumento di pianificazione anche prima di avere un piano fisso in mente può essere un modo molto istruttivo per comprendere i tipi di domande che è necessario considerare nel processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6223e-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="6223e-117">Puoi eseguire lo strumento di pianificazione più volte, rispondendo alle domande in modo diverso e confrontando i risultati.</span><span class="sxs-lookup"><span data-stu-id="6223e-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="6223e-118">Se si ha un progetto di cui si è soddisfatti per la maggior parte, ma è necessario apportare modifiche, è possibile tornare allo strumento di pianificazione, caricare la struttura e apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6223e-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="6223e-119">È necessario circa 15 minuti per completare lo strumento di pianificazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="6223e-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="6223e-120">Dopo aver soddisfatto, è possibile usare lo strumento pianificazione per creare un diagramma della distribuzione pianificata.</span><span class="sxs-lookup"><span data-stu-id="6223e-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="6223e-121">Puoi usare questo diagramma durante la creazione della distribuzione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6223e-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6223e-122">Lo strumento di pianificazione incluso in questo rilascio di Lync Server 2013 è una versione prerelease.</span><span class="sxs-lookup"><span data-stu-id="6223e-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="6223e-123">Tieni presente che i numeri di pianificazione della capacità nello strumento di pianificazione sono preliminari e non sono supportati per la versione finale.</span><span class="sxs-lookup"><span data-stu-id="6223e-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="6223e-124">Generatore di topologia di Lync Server</span><span class="sxs-lookup"><span data-stu-id="6223e-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="6223e-125">Dopo aver deciso il piano di distribuzione, è possibile usare generatore di topologia per iniziare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6223e-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="6223e-126">Al termine, puoi usare generatore di topologia per convalidare la topologia e quindi, se passa, puoi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="6223e-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="6223e-127">Quando si pubblica la topologia, Lync Server inserisce la topologia in Central Management store, che viene creata in questo momento, se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="6223e-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="6223e-128">Quando si installa Lync Server in ogni server della distribuzione, il server legge la topologia da Central Management store e si installa per adattarsi al proprio ruolo nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6223e-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="6223e-129">In alternativa, se si ha familiarità con Lync Server e si ha bisogno di indicazioni meno prescrittivi, è possibile ignorare lo strumento di pianificazione e usare le procedure guidate in Generatore di topologia per la progettazione iniziale della distribuzione e anche per la procedura di convalida e pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6223e-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="6223e-130">L'uso di generatore di topologia per pianificare e pubblicare una topologia è un passaggio obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6223e-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="6223e-131">Non è possibile ignorare il generatore di topologie e installare Lync Server singolarmente nei server della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6223e-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="6223e-132">Ogni server deve leggere la topologia da una topologia convalidata e pubblicata nell'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="6223e-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="6223e-133">Processo di pianificazione ad alto livello</span><span class="sxs-lookup"><span data-stu-id="6223e-133">High-Level Planning Process</span></span>

<span data-ttu-id="6223e-134">Per pianificare la distribuzione di Lync Server è consigliabile seguire la procedura generale seguente per l'uso della documentazione e dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6223e-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="6223e-135">Se si ha familiarità con le versioni precedenti di Lync Server, leggere le [nuove caratteristiche di Lync server 2013](lync-server-2013-new-features.md) per familiarizzare con le nuove caratteristiche e i requisiti di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6223e-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="6223e-136">Leggere gli altri argomenti in questa sezione della documentazione: [nozioni di base sulla topologia che è necessario conoscere prima di pianificare Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [fare riferimento a topologie in Lync Server 2013](lync-server-2013-reference-topologies.md), [decisioni di pianificazione iniziali per Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [client per Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6223e-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="6223e-137">Prendere nota delle decisioni di pianificazione rappresentate nelle [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="6223e-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="6223e-138">Ora che si ha familiarità con le caratteristiche di Lync Server e i tipi di domande a cui rispondere, eseguire lo strumento di pianificazione e visualizzare la topologia risultante e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="6223e-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="6223e-139">Verificare che la topologia corrisponda ai requisiti univoci per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6223e-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="6223e-140">Se sono presenti particolari carichi di lavoro o funzionalità di cui si è interessati o che è necessario conoscere, leggere le sezioni appropriate della [pianificazione per Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="6223e-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="6223e-141">Eseguire di nuovo lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6223e-141">Run the Planning Tool again.</span></span> <span data-ttu-id="6223e-142">È possibile iniziare con la distribuzione creata al passaggio 3 e modificare i risultati oppure ricominciare dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="6223e-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="6223e-143">Se necessario, eseguire la terza volta lo strumento di pianificazione e ripetere finché non si soddisfa l'output.</span><span class="sxs-lookup"><span data-stu-id="6223e-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="6223e-144">Dopo aver finalizzato il piano della topologia, usare lo strumento pianificazione per creare e stampare un diagramma di Visio della topologia.</span><span class="sxs-lookup"><span data-stu-id="6223e-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="6223e-145">È possibile usare questa stampa mentre si lavora con generatore di topologie per immettere la topologia.</span><span class="sxs-lookup"><span data-stu-id="6223e-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="6223e-146">Prima di iniziare la distribuzione, leggere [determinare i requisiti di sistema per Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinare i requisiti di infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) per familiarizzare con i prerequisiti e l'infrastruttura necessaria per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6223e-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="6223e-147">Assicurarsi inoltre di aver letto tutte le sezioni della [pianificazione per Lync Server 2013](lync-server-2013-planning.md) che si applicano ai carichi di lavoro e alle caratteristiche che si prevede di distribuire.</span><span class="sxs-lookup"><span data-stu-id="6223e-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="6223e-148">Migrazione da versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="6223e-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="6223e-149">Se si esegue la migrazione a Lync Server da una versione precedente, vedere la documentazione relativa alla [migrazione](migration.md) per istruzioni specifiche per la migrazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6223e-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

